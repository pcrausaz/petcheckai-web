---
####################### Banner #########################
banner:
  title : "Your trusted companion for <br> pet health decisions"
  content : "Pet Check AI empowers pet parents with instant, AI-driven health assessments when you're concerned about your furry family member. Whether it's 3 AM and your cat is acting strange, or you're unsure if that new behavior warrants a vet visit, Pet Check AI is here to help."
  image : "/PetCheck-Web.png"
  button:
    enable : false
    label : "Download Beta Now"
    link : "#download"
  download_section : true

##################### Feature ##########################
feature:
  enable : true
  title : "Why Pet Parents Trust Pet Check AI"
  feature_item:
    # feature item loop
    - name : "Smart Health Assessments"
      icon : "fas fa-stethoscope"
      content : "Get personalized health evaluations through our intelligent symptom checker, powered by veterinary expertise and advanced AI"
      
    # feature item loop
    - name : "Available 24/7"
      icon : "fas fa-clock"
      content : "Access instant health guidance anytime, anywhere - perfect for those late-night concerns about your pet"
      
    # feature item loop
    - name : "Easy-to-Use Interface"
      icon : "fas fa-mobile-alt"
      content : "Intuitive design makes it simple to input symptoms and get clear, actionable health insights"
      
    # feature item loop
    - name : "Privacy Focused"
      icon : "fas fa-shield-alt"
      content : "Your pet's health data is encrypted and secure - we never share personal information"
      
    # feature item loop
    - name : "Informed Vet Visits"
      icon : "fas fa-user-md"
      content : "Prepare for veterinary consultations with organized health information and symptom tracking"
      
    # feature item loop
    - name : "Health History Tracking"
      icon : "fas fa-history"
      content : "Keep detailed records of your pet's health journey to spot patterns and track improvements"

######################### Service #####################
service:
  enable : true
  service_item:
    # service item loop
    - title : "Perfect for New Pet Parents"
      content : "Learning to recognize health concerns in your new furry family member? Pet Check AI helps you understand what's normal and what needs attention, building your confidence as a pet parent."
      images : [""]
      button:
        enable : true
        label : "Learn More"
        link : "/faq"
        
    # service item loop
    - title : "Quick Guidance for Experienced Owners"
      content : "Even experienced pet owners encounter new situations. Get instant, reliable guidance on unusual symptoms and behaviors to make informed decisions about your pet's care."
      images : [""]
      button:
        enable : true
        label : "Learn More"
        link : "/faq"
        
    # service item loop
    - title : "Immediate Health Insights for Busy Families"
      content : "When life gets hectic, Pet Check AI ensures you never miss important health signals. Get quick assessments that help you prioritize your pet's needs in your busy schedule."
      images : [""]
      button:
        enable : true
        label : "Learn More"
        link : "/faq"

##################### Call to action #####################
call_to_action:
  enable : true
  title : "Ready to become a more informed pet advocate?"
  content : "Join thousands of pet parents who trust Pet Check AI for reliable health guidance. Download now and give your furry family member the care they deserve."
  button:
    enable : false
---

<!-- Banner Download Section -->
<div class="text-center mt-4">
  <div class="d-flex justify-content-center align-items-center gap-3 mb-4 flex-wrap">
    {{< downloadappbeta >}}
    {{< betastamp >}}
  </div>
</div>

<!-- Call to Action Download Section -->
<div class="container my-5">
  <div class="row justify-content-center text-center">
    <div class="col-lg-8">
      <h2 class="mb-4">Ready to become a more informed pet advocate?</h2>
      <p class="lead mb-4">Join thousands of pet parents who trust Pet Check AI for reliable health guidance. Download now and give your furry family member the care they deserve.</p>
      <div class="d-flex justify-content-center align-items-center gap-3 mb-4 flex-wrap">
        {{< downloadappbeta >}}
        {{< betastamp >}}
      </div>
    </div>
  </div>
</div>

<div id="download" class="text-center my-5">
  <h2>Download Pet Check AI Beta</h2>
  <p class="lead">Get early access to new features and help shape the future of pet health technology</p>
  <div class="d-flex justify-content-center align-items-center gap-3 mb-4">
    {{< downloadappbeta >}}
    {{< betastamp >}}
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
          <h3 class="mb-0"><i class="fas fa-exclamation-triangle"></i> Important Medical Disclaimer</h3>
        </div>
        <div class="card-body">
          <p class="lead">Please read and acknowledge this important information before using Pet Check AI.</p>
          
          <h5><strong>Not a Substitute for Veterinary Care</strong></h5>
          <p>This assessment is for informational purposes only and does not replace professional veterinary care. Always consult with a licensed veterinarian for accurate diagnosis and treatment.</p>
          
          <h5><strong>Emergency Situations</strong></h5>
          <p>If your pet is experiencing a medical emergency, contact your veterinarian or emergency animal hospital immediately. Do not rely solely on this assessment for urgent medical decisions.</p>
          
          <h5><strong>AI Limitations</strong></h5>
          <p>This assessment is generated by artificial intelligence and may not capture all aspects of your pet's condition. AI systems can make errors and should not be considered infallible.</p>
          
          <h5><strong>Professional Responsibility</strong></h5>
          <p>Only licensed veterinarians can provide official medical diagnoses and treatment recommendations. Use this tool as a supplement to, not a replacement for, professional veterinary consultation.</p>
          
          <h5><strong>Your Responsibility</strong></h5>
          <p>You are responsible for making informed decisions about your pet's health care. When in doubt, always err on the side of caution and seek professional veterinary advice.</p>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="container my-5">
  <h2 class="text-center mb-4">App Features</h2>
  <div class="row">
    <div class="col-md-6">
      <h4><i class="fas fa-users"></i> User Management</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Different user tiers with varying limits</li>
        <li><i class="fas fa-check text-success"></i> Anonymous users can convert to registered users</li>
        <li><i class="fas fa-check text-success"></i> Secure profile management</li>
      </ul>
    </div>
    <div class="col-md-6">
      <h4><i class="fas fa-paw"></i> My Pets</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Manage multiple pets with detailed profiles</li>
        <li><i class="fas fa-check text-success"></i> Pet photos, breed, weight, medical history</li>
        <li><i class="fas fa-check text-success"></i> Track allergies and medications</li>
      </ul>
    </div>
  </div>
  <div class="row mt-4">
    <div class="col-md-6">
      <h4><i class="fas fa-search"></i> Symptom Checker</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Free-form assessment system</li>
        <li><i class="fas fa-check text-success"></i> Guided questioning for accuracy</li>
        <li><i class="fas fa-check text-success"></i> Contextual pet information integration</li>
      </ul>
    </div>
    <div class="col-md-6">
      <h4><i class="fas fa-history"></i> Health History</h4>
      <ul class="list-unstyled">
        <li><i class="fas fa-check text-success"></i> Past assessment sessions</li>
        <li><i class="fas fa-check text-success"></i> Track symptoms over time</li>
        <li><i class="fas fa-check text-success"></i> Export data for vet visits</li>
      </ul>
    </div>
  </div>
</div>

<div class="container my-5 text-center">
  <h2>Need Help or Have a Suggestion?</h2>
  <p class="lead">We're here to help! Check our <a href="/support" class="text-decoration-none">support page</a> for contact information.</p>
</div>

