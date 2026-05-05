<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Brian Alexander Mejia Parra | Web Developer Portfolio</title>
  <!-- Google Fonts for clean typography -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free icons) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: #f5f2ea;  /* greige base (beige-grey) */
      color: #1e1e1e;             /* black / near black for contrast */
      scroll-behavior: smooth;
      line-height: 1.5;
    }

    /* dark green accents */
    :root {
      --dark-green: #1a4d3e;
      --greige-light: #f5f2ea;
      --greige-dark: #e2dbcf;
      --shadow-sm: 0 8px 20px rgba(0,0,0,0.03), 0 2px 4px rgba(0,0,0,0.05);
    }

    /* container utility */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    /* Header (sticky but elegant) */
    .header {
      position: sticky;
      top: 0;
      z-index: 100;
      background-color: rgba(245, 242, 234, 0.92);
      backdrop-filter: blur(8px);
      border-bottom: 1px solid rgba(26, 77, 62, 0.2);
      padding: 1rem 0;
      transition: all 0.2s ease;
    }

    .header-content {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .name-title h1 {
      font-size: 1.7rem;
      font-weight: 700;
      letter-spacing: -0.3px;
      color: #000;
    }

    .name-title p {
      font-size: 0.85rem;
      color: #1a4d3e;
      font-weight: 500;
      margin-top: 4px;
    }

    .nav-links {
      display: flex;
      gap: 2rem;
    }

    .nav-links a {
      color: #1e1e1e;
      text-decoration: none;
      font-weight: 500;
      font-size: 0.95rem;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: #1a4d3e;
    }

    /* profile section with round image */
    .profile {
      padding: 3rem 0 2rem 0;
      text-align: center;
    }

    .avatar {
      width: 160px;
      height: 160px;
      margin: 0 auto 1rem;
      border-radius: 50%;
      overflow: hidden;
      border: 4px solid #1a4d3e;
      box-shadow: 0 12px 24px rgba(0,0,0,0.08);
      background: #e2dbcf;
      transition: transform 0.3s ease;
    }

    .avatar img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    .avatar:hover {
      transform: scale(1.01);
    }

    .profile h2 {
      font-size: 2rem;
      font-weight: 600;
      letter-spacing: -0.5px;
      margin-top: 0.5rem;
      color: #000;
    }

    .profile .tagline {
      color: #1a4d3e;
      font-weight: 500;
      margin-top: 0.25rem;
      font-size: 1.1rem;
    }

    /* Section styles */
    section {
      padding: 4rem 0;
      border-bottom: 1px solid rgba(26, 77, 62, 0.15);
    }

    .section-title {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 2rem;
      position: relative;
      display: inline-block;
      color: #000;
    }

    .section-title:after {
      content: '';
      position: absolute;
      bottom: -8px;
      left: 0;
      width: 60px;
      height: 4px;
      background-color: #1a4d3e;
      border-radius: 2px;
    }

    /* Skills grid */
    .skills-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 1rem;
    }

    .skill-badge {
      background-color: white;
      border-radius: 60px;
      padding: 0.6rem 1.2rem;
      font-weight: 500;
      color: #000;
      box-shadow: var(--shadow-sm);
      border-left: 4px solid #1a4d3e;
      transition: transform 0.2s, background 0.2s;
      font-size: 0.95rem;
    }

    .skill-badge:hover {
      transform: translateY(-3px);
      background-color: #eef4f1;
    }

    /* Projects cards */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 2rem;
      margin-top: 1rem;
    }

    .project-card {
      background-color: white;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 6px 14px rgba(0,0,0,0.04);
      transition: all 0.3s ease;
      border: 1px solid #e2dbcf;
    }

    .project-card:hover {
      transform: translateY(-6px);
      box-shadow: 0 16px 28px rgba(0,0,0,0.08);
    }

    .project-img {
      background-color: #e2dbcf;
      height: 170px;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
    }

    .project-img img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.3s;
    }

    /* dual image container for pc + mobile mockup (customizable) */
    .dual-device {
      display: flex;
      gap: 0.8rem;
      align-items: center;
      justify-content: center;
      background: #e9e2d6;
      height: 100%;
      padding: 1rem;
    }

    .dual-device .device-icon {
      background: white;
      width: 70px;
      height: 70px;
      border-radius: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2rem;
      color: #1a4d3e;
      box-shadow: 0 4px 8px rgba(0,0,0,0.05);
    }

    .dual-device img {
      max-width: 100%;
      max-height: 100%;
      object-fit: contain;
      border-radius: 8px;
    }

    .project-info {
      padding: 1.5rem;
    }

    .project-info h3 {
      font-size: 1.3rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
      color: #000;
    }

    .project-info p {
      color: #2c2c2c;
      font-size: 0.9rem;
      margin-bottom: 1rem;
    }

    .tech-stack {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 1rem;
    }

    .tech-stack span {
      background: #f0ede7;
      padding: 0.2rem 0.7rem;
      border-radius: 20px;
      font-size: 0.7rem;
      font-weight: 500;
      color: #1a4d3e;
    }

    /* Footer */
    .footer {
      text-align: center;
      padding: 2rem 0;
      color: #1e1e1e;
      font-size: 0.85rem;
      background-color: #ece5db;
      margin-top: 1rem;
    }

    /* Scroll animation (fade-in on scroll) */
    .fade-up {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .fade-up.appear {
      opacity: 1;
      transform: translateY(0);
    }

    /* responsive */
    @media (max-width: 700px) {
      .container {
        padding: 0 1.5rem;
      }
      .header-content {
        flex-direction: column;
        align-items: center;
        text-align: center;
      }
      .nav-links {
        gap: 1.2rem;
        flex-wrap: wrap;
        justify-content: center;
      }
      .section-title {
        font-size: 1.7rem;
      }
    }

    /* extra green detail */
    .btn-outline {
      display: inline-block;
      margin-top: 0.5rem;
      background: transparent;
      border: 1px solid #1a4d3e;
      color: #1a4d3e;
      padding: 0.4rem 1rem;
      border-radius: 30px;
      font-weight: 500;
      font-size: 0.8rem;
      transition: 0.2s;
      text-decoration: none;
    }

    .btn-outline:hover {
      background: #1a4d3e;
      color: white;
    }

    /* custom file input for image update (simple) */
    .edit-image-label {
      cursor: pointer;
      background: rgba(26, 77, 62, 0.8);
      color: white;
      font-size: 0.7rem;
      border-radius: 20px;
      padding: 0.2rem 0.7rem;
      margin-top: 8px;
      display: inline-block;
      transition: 0.2s;
    }

    .edit-image-label:hover {
      background: #1a4d3e;
    }

    input[type="file"] {
      display: none;
    }

    .image-edit-wrapper {
      text-align: center;
      margin-bottom: 0.2rem;
    }
  </style>
</head>
<body>

<header class="header">
  <div class="container header-content">
    <div class="name-title">
      <h1>BRIAN ALEXANDER MEJIA PARRA</h1>
      <p><i class="fas fa-code"></i> full-stack developer & creative coder</p>
    </div>
    <div class="nav-links">
      <a href="#skills">SKILLS</a>
      <a href="#projects">PROJECTS</a>
      <a href="#contact">CONTACT</a>
    </div>
  </div>
</header>

<main>
  <!-- Profile Section with round avatar -->
  <div class="container profile">
    <div class="avatar" id="avatarContainer">
      <img id="profileImage" src="https://randomuser.me/api/portraits/men/32.jpg" alt="Brian Alexander Mejia Parra">
    </div>
    <div class="image-edit-wrapper">
      <label for="avatarUpload" class="edit-image-label"><i class="fas fa-camera"></i> Change photo</label>
      <input type="file" id="avatarUpload" accept="image/jpeg,image/png,image/jpg">
    </div>
    <h2>Brian Alexander Mejia Parra</h2>
    <div class="tagline">crafting robust web solutions | backend • frontend • databases</div>
  </div>

  <!-- SKILLS Section (en ingles) -->
  <section id="skills">
    <div class="container fade-up">
      <h2 class="section-title">SKILLS / HABILIDADES</h2>
      <div class="skills-grid">
        <span class="skill-badge"><i class="fab fa-php"></i> PHP</span>
        <span class="skill-badge"><i class="fab fa-js"></i> JavaScript (ES6+)</span>
        <span class="skill-badge"><i class="fab fa-python"></i> Python</span>
        <span class="skill-badge"><i class="fab fa-css3-alt"></i> CSS3</span>
        <span class="skill-badge"><i class="fab fa-html5"></i> HTML5</span>
        <span class="skill-badge"><i class="fas fa-database"></i> SQL (MySQL, PostgreSQL)</span>
      </div>
      <p style="margin-top: 1.2rem; font-weight: 400;"><i class="fas fa-laptop-code"></i> + version control (Git) & responsive design</p>
    </div>
  </section>

  <!-- PROJECTS Section with customizable images for PC + mobile -->
  <section id="projects">
    <div class="container fade-up">
      <h2 class="section-title">PROJECTS</h2>
      <div class="projects-grid">
        
        <!-- Project 1: dual image (pc + mobile side by side) with replaceable images -->
        <div class="project-card">
          <div class="project-img" id="project1ImgArea">
            <div class="dual-device" id="dualDevice1">
              <!-- PC icon with image slot (first image) -->
              <div class="device-icon" style="flex-direction: column; background: transparent; box-shadow: none; width: auto;">
                <i class="fas fa-desktop" style="font-size: 2rem; color:#1a4d3e;"></i>
                <img id="project1PcImg" src="https://placehold.co/400x200/1a4d3e/white?text=PC+Preview" alt="PC preview" style="width: 100px; height: auto; border-radius: 6px; margin-top: 5px;">
              </div>
              <!-- Mobile icon with image slot -->
              <div class="device-icon" style="flex-direction: column; background: transparent; box-shadow: none; width: auto;">
                <i class="fas fa-mobile-alt" style="font-size: 2rem; color:#1a4d3e;"></i>
                <img id="project1MobileImg" src="https://placehold.co/200x300/1a4d3e/white?text=Mobile+UI" alt="Mobile preview" style="width: 70px; height: auto; border-radius: 6px; margin-top: 5px;">
              </div>
            </div>
            <!-- hidden file inputs strictly for project 1 images -->
            <div style="position: absolute; bottom: 5px; right: 5px; background: rgba(0,0,0,0.5); border-radius: 20px; padding: 2px 8px;">
              <label for="pcImgUpload" style="color: white; font-size: 10px; cursor: pointer;"><i class="fas fa-edit"></i> PC</label>
              <input type="file" id="pcImgUpload" accept="image/*" style="display: none;">
              <label for="mobileImgUpload" style="color: white; font-size: 10px; margin-left: 8px; cursor: pointer;"><i class="fas fa-edit"></i> Mobile</label>
              <input type="file" id="mobileImgUpload" accept="image/*" style="display: none;">
            </div>
          </div>
          <div class="project-info">
            <h3>Dual-device dashboard</h3>
            <p>Responsive web app with real-time sync between desktop & mobile views. Built with PHP backend, SQL database, and vanilla JS.</p>
            <div class="tech-stack">
              <span>PHP</span><span>JS</span><span>SQL</span><span>CSS</span>
            </div>
            <a href="#" class="btn-outline">Live demo →</a>
          </div>
        </div>

        <!-- Project 2: extra project with placeholder image (but you can still change) but using image of pc/mobile? second project normal image (customizable) but to give flexibility, we add both regular project and optional preview -->
        <div class="project-card">
          <div class="project-img" style="position: relative;">
            <img id="project2Img" src="https://placehold.co/600x400/1a4d3e/white?text=E-Commerce+Backend" alt="Project screenshot" style="width:100%; height:100%; object-fit:cover;">
            <div style="position: absolute; bottom: 8px; right: 8px; background: rgba(0,0,0,0.6); border-radius: 20px; padding: 2px 8px;">
              <label for="project2Upload" style="color: white; font-size: 10px; cursor: pointer;"><i class="fas fa-pen"></i> change img</label>
              <input type="file" id="project2Upload" accept="image/*" style="display: none;">
            </div>
          </div>
          <div class="project-info">
            <h3>Inventory Manager System</h3>
            <p>Full-stack CRUD using Python (Flask) + MySQL, featuring JWT authentication and modern dashboard.</p>
            <div class="tech-stack">
              <span>Python</span><span>Flask</span><span>SQL</span><span>HTML/CSS</span>
            </div>
            <a href="#" class="btn-outline">Case study →</a>
          </div>
        </div>

        <!-- Project 3: another example with also image update -->
        <div class="project-card">
          <div class="project-img" style="position: relative;">
            <img id="project3Img" src="https://placehold.co/600x400/1a4d3e/white?text=JS+Task+Flow" alt="JS project">
            <div style="position: absolute; bottom: 8px; right: 8px; background: rgba(0,0,0,0.6); border-radius: 20px; padding: 2px 8px;">
              <label for="project3Upload" style="color: white; font-size: 10px; cursor: pointer;"><i class="fas fa-pen"></i> change img</label>
              <input type="file" id="project3Upload" accept="image/*" style="display: none;">
            </div>
          </div>
          <div class="project-info">
            <h3>TaskFlow SPA</h3>
            <p>JavaScript frontend with PHP REST API and PostgreSQL. Includes drag & drop and realtime notifications.</p>
            <div class="tech-stack">
              <span>JS</span><span>PHP</span><span>PostgreSQL</span><span>CSS</span>
            </div>
            <a href="#" class="btn-outline">Explore →</a>
          </div>
        </div>
      </div>
      <p style="margin-top: 2rem; text-align: center; font-size: 0.9rem;"><i class="fas fa-image"></i> Tip: click <strong>"PC" / "Mobile"</strong> buttons on first project to replace images. For other projects, use "change img" button.</p>
    </div>
  </section>

  <!-- Contact / extra section -->
  <section id="contact" style="border-bottom: none;">
    <div class="container fade-up">
      <h2 class="section-title">CONTACT</h2>
      <p style="margin-bottom: 1rem;">📧 brian.mejia@webdeveloper.com &nbsp;|&nbsp; <i class="fab fa-github"></i> github.com/brianmejia &nbsp;|&nbsp; <i class="fab fa-linkedin"></i> linkedin.com/in/brian-alexander</p>
      <p style="color:#1a4d3e;">⚡ Open for freelance & collaborations — Let's bring ideas to life.</p>
    </div>
  </section>
</main>

<footer class="footer">
  <div class="container">
    <p>© 2026 BRIAN ALEXANDER MEJIA PARRA — built with greige & dark green details</p>
  </div>
</footer>

<script>
  // Scroll animation: Intersection Observer for .fade-up elements
  const fadeElements = document.querySelectorAll('.fade-up');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('appear');
        observer.unobserve(entry.target); // optional: keep visible
      }
    });
  }, { threshold: 0.15, rootMargin: "0px 0px -10px 0px" });
  
  fadeElements.forEach(el => observer.observe(el));
  
  // Force initial check for any already visible
  window.addEventListener('load', () => {
    fadeElements.forEach(el => {
      const rect = el.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100) {
        el.classList.add('appear');
      }
    });
  });

  // 1) Profile picture upload (round)
  const avatarUpload = document.getElementById('avatarUpload');
  const profileImage = document.getElementById('profileImage');
  avatarUpload.addEventListener('change', function(e) {
    const file = e.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onload = function(event) {
        profileImage.src = event.target.result;
      };
      reader.readAsDataURL(file);
    }
  });

  // 2) PROJECT 1: PC and Mobile image replace logic (dual image)
  const pcUpload = document.getElementById('pcImgUpload');
  const mobileUpload = document.getElementById('mobileImgUpload');
  const project1PcImg = document.getElementById('project1PcImg');
  const project1MobileImg = document.getElementById('project1MobileImg');
  
  if (pcUpload) {
    pcUpload.addEventListener('change', function(e) {
      const file = e.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(ev) {
          project1PcImg.src = ev.target.result;
        };
        reader.readAsDataURL(file);
      }
    });
  }
  if (mobileUpload) {
    mobileUpload.addEventListener('change', function(e) {
      const file = e.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(ev) {
          project1MobileImg.src = ev.target.result;
        };
        reader.readAsDataURL(file);
      }
    });
  }

  // 3) Project 2 image change
  const proj2Upload = document.getElementById('project2Upload');
  const proj2Img = document.getElementById('project2Img');
  if (proj2Upload) {
    proj2Upload.addEventListener('change', (e) => {
      const file = e.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = (ev) => { proj2Img.src = ev.target.result; };
        reader.readAsDataURL(file);
      }
    });
  }

  // 4) Project 3 image change
  const proj3Upload = document.getElementById('project3Upload');
  const proj3Img = document.getElementById('project3Img');
  if (proj3Upload) {
    proj3Upload.addEventListener('change', (e) => {
      const file = e.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = (ev) => { proj3Img.src = ev.target.result; };
        reader.readAsDataURL(file);
      }
    });
  }

  // Extra styling: smooth scroll for anchor links
  document.querySelectorAll('.nav-links a').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
      e.preventDefault();
      const targetId = this.getAttribute('href').substring(1);
      const targetElement = document.getElementById(targetId);
      if (targetElement) {
        targetElement.scrollIntoView({ behavior: 'smooth', block: 'start' });
      }
    });
  });
  
  // Also for any other links if needed (project demo buttons are "#", but they don't cause issues)
  // small optional: ensure header does not overlap on scroll (sticky already handles)
  // also ensure that any images that fail to load have fallback (already placeholders)
  
  // additional dynamic: apply hover effect on tech badges as wanted, plus dark green details on border etc.
  
  // Optional: preload some nice custom demo for mobile and pc images: keep placeholder style.
  console.log('Portfolio ready: greige background, dark green accents, animations on scroll');
</script>

<!-- small note: all labels/buttons in english, skills and project descriptions in english, header shows full legal name -->
</body>
</html>
