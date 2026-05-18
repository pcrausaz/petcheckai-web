# Fix Google Search Console URL issues

## Context

Google Search Console is reporting three issues for petcheckai.com:

1. **404 on `http://petcheckai.com/fr-FR/faq`** — and almost certainly the other French pages too (`/fr-FR/support`, `/fr-FR/privacy`, `/fr-FR/eula`).
2. **noindex on `http://petcheckai.com/en-us/`** — Google sees a `<meta name="robots" content="noindex">` redirect there.
3. **Crawled — currently not indexed** — a generic "Google chose not to index" signal that is often a symptom of #1 and #2.

Root causes from investigation:

- **#1 (404):** The French menu entries in `hugo.toml` (lines 181, 194, 207, 219, 231) hard-code uppercase paths like `/fr-FR/faq`. Hugo lowercases all generated URLs, so the actual files live at `/fr-fr/faq`. GitHub Pages is case-sensitive — so every internal link to `/fr-FR/...` in the rendered site returns 404, and Google followed those.
- **#2 (noindex):** No `defaultContentLanguage` is set in `hugo.toml`. Hugo falls back to its built-in default of `"en"`, which doesn't match either configured language (`en-US`/`fr-FR`). Hugo then emits an alias redirect file at `/en-us/index.html` (containing `<meta robots="noindex">` and a refresh to `/`) to canonicalize duplicate URLs. The noindex itself is technically *correct* — `/` is the real English home and is what should be indexed — but the cleanest fix is to make Hugo stop emitting `/en-us/` at all.
- **#3 (not indexed):** Largely a consequence of #1/#2. Also worth noting: the committed `public/sitemap.xml` is a stale `hugo server` artifact full of `http://localhost:1313/` URLs. CI rebuilds `public/` fresh on each push (`.github/workflows/hugo.yaml` line 68), so production is fine — but the committed copy is misleading and should be deleted to avoid confusion.

Intended outcome: clean Hugo build with no 404s from internal links, no stray noindex pages, and clearer signals to Google.

## Changes

### 1. Fix French menu URLs in `hugo.toml`

Lower-case all five French menu URLs so they match the actual generated paths.

| Line | Old | New |
|------|-----|-----|
| 181 | `url = "/fr-FR"` | `url = "/fr-fr"` |
| 194 | `url = "/fr-FR/faq"` | `url = "/fr-fr/faq"` |
| 207 | `url = "/fr-FR/support"` | `url = "/fr-fr/support"` |
| 219 | `url = "/fr-FR/privacy"` | `url = "/fr-fr/privacy"` |
| 231 | `url = "/fr-FR/eula"` | `url = "/fr-fr/eula"` |

Note: we do **not** rename the `content/fr-FR/` directory or the `[languages.fr-FR]` config key. Hugo's standard convention is to use the canonical IETF language tag (`fr-FR`) in config and content, while emitting lowercase URLs. Only the menu URLs were inconsistent.

### 2. Set `defaultContentLanguage` explicitly in `hugo.toml`

Add near the top of `hugo.toml` (before the `[languages]` block at line 156):

```toml
defaultContentLanguage = "en-US"
defaultContentLanguageInSubdir = false
```

This tells Hugo:
- en-US is the canonical default → rendered at `/`.
- The default language is NOT placed in a subdirectory → no `/en-us/` URL emitted.

Result: the noindex redirect file at `/en-us/index.html` stops being generated. Google will eventually drop `/en-us/` from its index (it'll start returning 404, which is fine — there's no inbound link to it anyway).

### 3. Delete the stale committed `public/` directory and add a `.gitignore`

The repo currently has no `.gitignore`, and `public/` is committed but is regenerated fresh by CI. The committed copy contains `hugo server` artifacts (livereload scripts, `localhost:1313` URLs in the sitemap, the noindex stub). It is never deployed, but it pollutes diffs and confuses investigation.

Create `/Users/pascal/Documents/Sources/petcheckai-web/.gitignore`:

```
public/
resources/
.hugo_build.lock
.DS_Store
```

Then `git rm -r --cached public/` to untrack the directory without deleting local files.

### 4. Optional but recommended: post-deploy actions in Google Search Console

Once the above is deployed:
- Submit the sitemap `https://petcheckai.com/sitemap.xml` (or resubmit it) so Google re-discovers canonical URLs.
- Use the URL Inspection tool to "Request indexing" for `/`, `/fr-fr/`, `/faq`, `/fr-fr/faq`, `/support`, `/fr-fr/support`, `/privacy`, `/fr-fr/privacy`, `/eula`, `/fr-fr/eula`.
- The `/fr-FR/...` 404s and the `/en-us/` noindex entry will drop out of the report over the following weeks (Google needs to re-crawl and observe the new state).

This is a one-time manual step in the GSC UI — no code change needed.

## Files modified

- `/Users/pascal/Documents/Sources/petcheckai-web/hugo.toml` — menu URLs + `defaultContentLanguage` settings.
- `/Users/pascal/Documents/Sources/petcheckai-web/.gitignore` — new file.
- `git rm -r --cached public/` — untrack stale build output.

## What we deliberately do NOT do

- **Don't add HTML aliases at `/fr-FR/...`** to make the bad URLs work. Hugo's `aliases` front matter also gets lowercased on output, so this can't reliably create case-sensitive redirects on GitHub Pages. Letting the old URLs 404 is the standard SEO approach — Google drops them after repeated 404s.
- **Don't rename `content/fr-FR/` to `content/fr-fr/`.** The language tag `fr-FR` is the correct IETF form; only the URL representation needs to be lowercase, and Hugo already handles that.
- **Don't set `disablePathToLower = true`.** It would preserve case in URLs but would also change every other URL on the site and create new canonicalization problems.

## Verification

After applying the changes:

1. **Local clean build:**
   ```bash
   rm -rf public/ resources/
   hugo --minify
   ```
2. **Confirm `/en-us/` is gone:**
   ```bash
   test ! -e public/en-us && echo OK
   ```
   (Should print `OK`.)
3. **Confirm French URLs are lowercase:**
   ```bash
   ls public/fr-fr/faq/index.html && ls public/fr-fr/support/index.html
   ```
4. **Confirm sitemap is clean:**
   ```bash
   grep -c "localhost" public/sitemap.xml public/fr-fr/sitemap.xml public/en-us/sitemap.xml 2>/dev/null
   ```
   Should return 0 for any file that exists. Production URLs only.
5. **Spot-check generated HTML for the French menu:**
   ```bash
   grep -o 'href="/fr-[A-Za-z]*' public/index.html | sort -u
   ```
   Should only show `href="/fr-fr"` — no `/fr-FR` references.
6. **Push to `main` → CI deploys** via `.github/workflows/hugo.yaml`. Visit `https://petcheckai.com/fr-fr/faq` and confirm 200. Visit `https://petcheckai.com/en-us/` and confirm 404 (the redirect stub should no longer exist).
7. **In Google Search Console**, request re-indexing as described in §4, then check the Coverage report over the next 2–4 weeks for the bad URLs to drop off.
