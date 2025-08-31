---
layout: default
title: Tanishk Manoj Mestry - Portfolio
---

<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;700&display=swap');

  /* --- Vibrant Gradient Theme --- */
  :root {
    --color-1: #ff7e5f;
    --color-2: #feb47b;
    --color-3: #8a2be2;
    --color-4: #00c6ff;
    --bg-color: #11111a;
    --card-bg: rgba(26, 26, 46, 0.7);
    --text-color: #f0f0f0;
    --border-color: rgba(255, 255, 255, 0.2);
    --primary-gradient: linear-gradient(90deg, var(--color-1), var(--color-3));
  }

  body.light-theme {
    --color-1: #6a11cb;
    --color-2: #2575fc;
    --color-3: #ff007f;
    --color-4: #f8ffae;
    --bg-color: #f5f5f5;
    --card-bg: rgba(255, 255, 255, 0.7);
    --text-color: #1c1c1c;
    --border-color: rgba(0, 0, 0, 0.2);
  }
  
  html { scroll-behavior: smooth; }

  body {
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0; padding: 0;
    background: var(--bg-color);
    transition: background-color 0.5s, color 0.5s;
  }

  /* --- Fixed Header & Theme Toggle --- */
  .main-header {
    position: fixed;
    top: 0;
    right: 0;
    padding: 1.5rem 2rem;
    z-index: 1000;
    display: flex;
    align-items: center;
    gap: 1.5rem;
  }
  .main-nav a {
      color: var(--text-color);
      text-decoration: none;
      font-weight: bold;
      padding: 0.5rem;
      position: relative;
  }
  .main-nav a::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--primary-gradient);
      transition: width 0.3s ease;
  }
  .main-nav a:hover::after { width: 100%; }
  
  .theme-switch { display: inline-block; height: 24px; position: relative; width: 50px; }
  .theme-switch input { display:none; }
  .slider { background-color: var(--card-bg); border: 1px solid var(--border-color); bottom: 0; cursor: pointer; left: 0; position: absolute; right: 0; top: 0; transition: .4s; border-radius: 34px; }
  .slider:before { font-family: 'boxicons'; content: '\ea43'; color: var(--text-color); display: flex; align-items: center; justify-content: center; font-size: 16px; background-color: transparent; bottom: 3px; height: 18px; left: 4px; position: absolute; transition: .4s; width: 18px; border-radius: 50%; }
  input:checked + .slider { background-color: var(--card-bg); }
  input:checked + .slider:before { content: '\e9c5'; transform: translateX(24px); }

  /* --- Layout & Sections --- */
  .content-wrapper {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 2rem;
  }
  .section {
    padding: 6rem 0;
    border-bottom: 1px solid var(--border-color);
  }
  
  .section h2 {
    font-size: clamp(2.5rem, 5vw, 4rem);
    margin-bottom: 3rem;
    background: var(--primary-gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  
  /* --- Welcome/Hero Section --- */
  #welcome {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    border-bottom: 1px solid var(--border-color);
  }
  #welcome h1 { font-size: clamp(3rem, 8vw, 6rem); margin: 0; line-height: 1.1; }
  #welcome h3 { font-size: clamp(1.2rem, 3vw, 1.8rem); font-weight: 300; margin: 1.5rem 0 2.5rem 0; max-width: 600px; }
  #welcome .social-links a { font-size: 2rem; margin-right: 1.5rem; color: var(--text-color); transition: color 0.3s; }
  #welcome .social-links a:hover { color: var(--color-1); }
  
  /* --- Grids --- */
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1.5rem; }
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 2rem; }
  .certifications-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1.5rem; }
  
  /* --- Cards & Items (Non-blocky feel) --- */
  .skill-item {
    background: transparent;
    border: 1px solid var(--border-color);
    padding: 1.5rem;
    border-radius: 8px;
    text-align: center;
    transition: background 0.3s, transform 0.3s;
  }
  .skill-item:hover { background: var(--card-bg); transform: translateY(-5px); }
  .skill-item .skill-icon { height: 50px; width: 50px; margin-bottom: 1rem; }
  .project-card {
      background: var(--card-bg);
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 2rem;
      cursor: pointer;
      transition: transform 0.3s, box-shadow 0.3s;
  }
  .project-card:hover { transform: translateY(-10px); box-shadow: 0 20px 40px rgba(0,0,0,0.2); }
  .project-card h3 { margin: 0 0 0.5rem 0; font-size: 1.5rem; }
  .project-card .tech-tag { background: var(--primary-gradient); color: #fff; /* ... */ }

  /* --- Animation on Scroll --- */
  .hidden { opacity: 0; transform: translateY(20px); transition: opacity 0.6s ease-out, transform 0.6s ease-out; }
  .show { opacity: 1; transform: translateY(0); }
  
  /* (Modal styles are the same, they overlay everything) */
  .modal { display: none; position: fixed; z-index: 2000; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.8); backdrop-filter: blur(5px); }
  .modal-content { background-color: var(--bg-color); border: 1px solid var(--border-color); margin: 5% auto; padding: 2rem; width: 80%; max-width: 900px; position: relative; border-radius: 8px; }
  .modal-content img { width: 100%; }
  .close-button { color: #aaaaaa; position: absolute; top: 1rem; right: 1.5rem; font-size: 2.5rem; font-weight: bold; cursor: pointer; }
</style>

<header class="main-header">
  <nav class="main-nav">
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#experience">Experience</a>
  </nav>
  <div class="theme-switch-wrapper">
    <label class="theme-switch" for="checkbox">
      <input type="checkbox" id="checkbox" />
      <div class="slider round"></div>
    </label>
  </div>
</header>

<main>
  <div class="content-wrapper">

    <section id="welcome">
      <h1 class="hidden">TANISHK MANOJ MESTRY</h1>
      <h3 class="hidden">Applied Statistics and Data Analytics student with strong skills in data analysis, statistical modelling, and visualization.</h3>
      <div class="social-links hidden">
        <a href="mailto:tanishkmestry4183@gmail.com" target="_blank" title="Email"><i class='bx bx-envelope'></i></a>
        <a href="https://www.linkedin.com/in/YOUR_LINKEDIN_URL" target="_blank" title="LinkedIn"><i class='bx bxl-linkedin-square'></i></a>
        <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" title="GitHub"><i class='bx bxl-github'></i></a>
      </div>
    </section>

    <section id="skills" class="section hidden">
      <h2>Technical Skills</h2>
      <div class="skills-grid">
        <div class="skill-item hidden">...</div>
        <div class="skill-item hidden">...</div>
        </div>
    </section>

    <section id="projects" class="section hidden">
      <h2>Projects</h2>
      <div class="projects-grid">
        </div>
    </section>

    <section id="certifications" class="section hidden">
      <h2>Certifications</h2>
      <div class="certifications-grid">
        </div>
    </section>

    <section id="experience" class="section hidden">
      <h2>Work Experience</h2>
      </section>

    <section id="education" class="section hidden">
      <h2>Education</h2>
      </section>

  </div>
</main>

<script>
  // --- Theme Toggle Script (Corrected) ---
  const toggleSwitch = document.querySelector('.theme-switch input[type="checkbox"]');
  const currentTheme = localStorage.getItem('theme');
  if (currentTheme) {
    document.body.classList.add(currentTheme);
    if (currentTheme === 'light-theme') { toggleSwitch.checked = true; }
  }
  function switchTheme(e) {
    if (e.target.checked) {
      document.body.classList.add('light-theme');
      localStorage.setItem('theme', 'light-theme');
    } else {
      document.body.classList.remove('light-theme');
      localStorage.setItem('theme', 'dark-theme');
    }    
  }
  toggleSwitch.addEventListener('change', switchTheme, false);

  // --- Animation on Scroll Script ---
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('show');
      }
    });
  });
  const hiddenElements = document.querySelectorAll('.hidden');
  hiddenElements.forEach((el) => observer.observe(el));

  // --- Modal Script ---
  function openModal(modalId) { document.getElementById(modalId).style.display = "block"; }
  function closeModal(modalId) { document.getElementById(modalId).style.display = "none"; }
  window.onclick = function(event) { if (event.target.classList.contains('modal')) { event.target.style.display = "none"; } }

</script>
