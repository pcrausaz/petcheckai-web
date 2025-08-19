---
####################### Banner #########################
banner:
  title : "Votre compagnon de confiance pour <br> les décisions de santé de votre animal"
  content : "Pet Check AI permet aux propriétaires d'animaux de compagnie de bénéficier d'évaluations de santé instantanées, basées sur l'IA, lorsque vous vous inquiétez pour votre compagnon à quatre pattes. Qu'il soit 3 heures du matin et que votre chat se comporte bizarrement, ou que vous ayez des doutes quant à la nécessité d'une visite chez le vétérinaire, Pet Check AI est là pour vous aider."
  image : "/PetCheck-Web.png"
  button:
    enable : false
    label : "Télécharger"
    link : "#download"
  download_section : true

##################### Feature ##########################
feature:
  enable : true
  title : "Pourquoi les propriétaires d'animaux font confiance à Pet Check AI"
  feature_item:
    # feature item loop
    - name : "Évaluations de Santé Intelligentes"
      icon : "fas fa-stethoscope"
      content : "Obtenez des évaluations de santé personnalisées grâce à notre outil intelligent de vérification des symptômes, optimisé par l'expertise vétérinaire et une IA avancée"
      
    # feature item loop
    - name : "Disponible 24h/24 7j/7"
      icon : "fas fa-clock"
      content : "Accédez à des conseils de santé instantanés à tout moment, n'importe où - parfait pour ces inquiétudes nocturnes concernant votre animal"
      
    # feature item loop
    - name : "Interface Facile à Utiliser"
      icon : "fas fa-mobile-alt"
      content : "Design intuitif qui simplifie la saisie des symptômes et fournit des conseils de santé clairs et exploitables"
      
    # feature item loop
    - name : "Axé sur la Confidentialité"
      icon : "fas fa-shield-alt"
      content : "Les données de santé de votre animal sont cryptées et sécurisées - nous ne partageons jamais d'informations personnelles"
      
    # feature item loop
    - name : "Visites Vétérinaires Éclairées"
      icon : "fas fa-user-md"
      content : "Préparez les consultations vétérinaires avec des informations de santé organisées et un suivi des symptômes"
      
    # feature item loop
    - name : "Suivi de l'Historique de Santé"
      icon : "fas fa-history"
      content : "Conservez des dossiers détaillés du parcours de santé de votre animal pour identifier les tendances et suivre les améliorations"

######################### Service #####################
service:
  enable : true
  service_item:
    # service item loop
    - title : "Parfait pour les Nouveaux Propriétaires d'Animaux"
      content : "Vous apprenez à reconnaître les problèmes de santé chez votre nouveau compagnon à quatre pattes ? Pet Check AI vous aide à comprendre ce qui est normal et ce qui nécessite une attention, renforçant votre confiance en tant que propriétaire d'animal."
      images : [""]
      button:
        enable : true
        label : "En Savoir Plus"
        link : "/fr-FR/faq"
        
    # service item loop
    - title : "Conseils Rapides pour les Propriétaires Expérimentés"
      content : "Même les propriétaires d'animaux expérimentés rencontrent de nouvelles situations. Obtenez des conseils instantanés et fiables sur les symptômes et comportements inhabituels pour prendre des décisions éclairées concernant les soins de votre animal."
      images : [""]
      button:
        enable : true
        label : "En Savoir Plus"
        link : "/fr-FR/faq"
        
    # service item loop
    - title : "Conseils de Santé Immédiats pour les Familles Occupées"
      content : "Quand la vie devient trépidante, Pet Check AI s'assure que vous ne manquez jamais les signaux de santé importants. Obtenez des évaluations rapides qui vous aident à prioriser les besoins de votre animal dans votre emploi du temps chargé."
      images : [""]
      button:
        enable : true
        label : "En Savoir Plus"
        link : "/fr-FR/faq"

##################### Call to action #####################
call_to_action:
  enable : true
  title : "Prêt à devenir un défenseur plus informé de votre animal ?"
  content : "Rejoignez des milliers de propriétaires d'animaux qui font confiance à Pet Check AI pour des conseils de santé fiables. Téléchargez maintenant et donnez à votre compagnon à quatre pattes les soins qu'il mérite."
  button:
    enable : false
---

<!-- Banner Download Section -->
<div class="text-center mt-4">
  <div class="d-flex justify-content-center align-items-center gap-3 mb-4 flex-wrap">
    {{< downloadapp >}}
  </div>
</div>

<!-- Call to Action Download Section -->
<div class="container my-5">
  <div class="row justify-content-center text-center">
    <div class="col-lg-8">
      <h2 class="mb-4">Prêt à devenir un défenseur plus informé de votre animal ?</h2>
      <p class="lead mb-4">Rejoignez des milliers de propriétaires d'animaux qui font confiance à PetCheck AI pour des conseils de santé fiables. Téléchargez maintenant et donnez à votre compagnon à quatre pattes les soins qu'il mérite.</p>
      <div class="d-flex justify-content-center align-items-center gap-3 mb-4 flex-wrap">
        {{< downloadapp >}}
      </div>
    </div>
  </div>
</div>

<div id="download" class="text-center my-5">
  <h2>Télécharger Pet Check AI</h2>
  <p class="lead">Obtenez des évaluations de santé instantanées optimisées par l'IA pour vos compagnons à quatre pattes</p>
  <div class="d-flex justify-content-center align-items-center gap-3 mb-4">
    {{< downloadapp >}}
  </div>
  
  <div class="mt-4">
    {{< buymeacoffee >}}
  </div>
</div>

<div class="container my-5">
  <div class="row">
    <div class="col-lg-8 mx-auto">
      <div class="card border-warning">
        <div class="card-header bg-warning text-dark">
          <h3 class="mb-0"><i class="fas fa-exclamation-triangle"></i> Avis de Non-responsabilité Médicale Important</h3>
        </div>
        <div class="card-body">
          <p class="lead">Veuillez lire et reconnaître ces informations importantes avant d'utiliser Pet Check AI.</p>
          
          <h5><strong>Ne Remplace Pas les Soins Vétérinaires</strong></h5>
          <p>Cette évaluation est fournie à titre informatif uniquement et ne remplace pas les soins vétérinaires professionnels. Consultez toujours un vétérinaire agréé pour un diagnostic et un traitement précis.</p>
          
          <h5><strong>Situations d'Urgence</strong></h5>
          <p>Si votre animal présente une urgence médicale, contactez immédiatement votre vétérinaire ou une clinique vétérinaire d'urgence. Ne vous fiez pas uniquement à cette évaluation pour prendre des décisions médicales urgentes.</p>
          
          <h5><strong>Limitations de l'IA</strong></h5>
          <p>Cette évaluation est générée par l'intelligence artificielle et peut ne pas prendre en compte tous les aspects de l'état de santé de votre animal. Les systèmes d'IA peuvent commettre des erreurs et ne doivent pas être considérés comme infaillibles.</p>
          
          <h5><strong>Responsabilité Professionnelle</strong></h5>
          <p>Seuls les vétérinaires agréés peuvent fournir des diagnostics médicaux officiels et des recommandations de traitement. Utilisez cet outil en complément, et non en remplacement, d'une consultation vétérinaire professionnelle.</p>
          
          <h5><strong>Votre Responsabilité</strong></h5>
          <p>Vous êtes responsable de prendre des décisions éclairées concernant les soins de santé de votre animal. En cas de doute, privilégiez la prudence et consultez un vétérinaire professionnel.</p>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="container my-5">
  <h2 class="text-center mb-4">Fonctionnalités de l'Application</h2>
  <div class="row">
    <div class="col-md-6">
      <h4><i class="fas fa-users"></i> Gestion des Utilisateurs</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Différents niveaux d'utilisateur avec des limites variables</li>
        <li><i class="fas fa-check text-success"></i> Les utilisateurs anonymes peuvent devenir des utilisateurs enregistrés</li>
        <li><i class="fas fa-check text-success"></i> Gestion de profil sécurisée</li>
      </ul>
    </div>
    <div class="col-md-6">
      <h4><i class="fas fa-paw"></i> Mes Animaux</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Gérer plusieurs animaux avec des profils détaillés</li>
        <li><i class="fas fa-check text-success"></i> Photos d'animaux, race, poids, historique médical</li>
        <li><i class="fas fa-check text-success"></i> Suivi des allergies et des médicaments</li>
      </ul>
    </div>
  </div>
  <div class="row mt-4">
    <div class="col-md-6">
      <h4><i class="fas fa-search"></i> Vérificateur de Symptômes</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Système d'évaluation en forme libre</li>
        <li><i class="fas fa-check text-success"></i> Questions guidées pour plus de précision</li>
        <li><i class="fas fa-check text-success"></i> Intégration d'informations contextuelles sur l'animal</li>
      </ul>
    </div>
    <div class="col-md-6">
      <h4><i class="fas fa-history"></i> Historique de Santé</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Sessions d'évaluation passées</li>
        <li><i class="fas fa-check text-success"></i> Suivi des symptômes dans le temps</li>
        <li><i class="fas fa-check text-success"></i> Export des données pour les visites vétérinaires</li>
      </ul>
    </div>
  </div>
</div>

<div class="container my-5 text-center">
  <h2>Besoin d'Aide ou Avez-vous une Suggestion ?</h2>
  <p class="lead">Nous sommes là pour vous aider ! Consultez notre <a href="/fr-FR/support" class="text-decoration-none">page de support</a> pour obtenir nos coordonnées.</p>
</div>