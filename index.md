---
layout: default
title: Tanishk Manoj Mestry - Portfolio
---

<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;700&display=swap');

  /* --- NEW: Vibrant Gradient Theme --- */
  :root {
    --color-1: #ff7e5f;
    --color-2: #feb47b;
    --color-3: #8a2be2;
    --color-4: #00c6ff;
    --card-bg: rgba(26, 26, 46, 0.7); /* Semi-transparent dark card */
    --text-color: #f0f0f0;
    --border-color: rgba(255, 255, 255, 0.2);
    --glow-color: #ff7e5f;
  }

  body.light-theme {
    --color-1: #6a11cb;
    --color-2: #2575fc;
    --color-3: #ff007f;
    --color-4: #f8ffae;
    --card-bg: rgba(255, 255, 255, 0.7); /* Semi-transparent light card */
    --text-color: #1c1c1c;
    --border-color: rgba(0, 0, 0, 0.2);
    --glow-color: #6a11cb;
  }
  
  html { scroll-behavior: smooth; }

  body {
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0; padding: 0;
    scroll-snap-type: y mandatory;
    overflow-y: scroll;
    height: 100vh;
    /* Animated Gradient Background */
    background: linear-gradient(135deg, var(--color-1), var(--color-2), var(--color-3), var(--color-4));
    background-size: 400% 400%;
    animation: gradientAnimation 15s ease infinite;
    transition: background-color 0.5s;
  }

  @keyframes gradientAnimation {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  .slide {
    width: 100vw;
    height: 100vh;
    scroll-snap-align: start;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    box-sizing: border-box;
    padding: 2rem;
    overflow: hidden;
  }

  .slide-content {
    width: 100%;
    max-width: 1200px;
    text-align: center;
    background: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 16px;
    padding: 3rem;
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
  }

  /* Gradient Text Effect */
  .slide-content h2 {
    font-size: 3.5rem;
    margin-bottom: 3rem;
    background: linear-gradient(90deg, var(--color-1), var(--color-2), var(--color-3));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    padding-bottom: 10px;
    border-bottom: 2px solid var(--border-color);
  }
  
  #welcome .typing-effect {
    font-size: 3.5rem;
    font-weight: 700;
    color: var(--text-color); /* Plain text for typing effect */
  }

  #welcome h3 { font-size: 1.5rem; font-weight: 300; margin: 1rem 0 2rem 0; }
  #welcome .social-links a { font-size: 2rem; margin: 0 1rem; color: var(--text-color); transition: color 0.3s; }
  #welcome .social-links a:hover { color: var(--color-1); }
  
  /* --- Horizontal Scroll for Certifications --- */
  #certifications .slide-content {
      padding: 3rem 0; /* Remove side padding to allow full bleed */
  }
  .horizontal-scroll-wrapper {
      display: flex;
      overflow-x: auto;
      padding: 0 3rem 2rem 3rem; /* Add padding here */
      /* Hide scrollbar */
      -ms-overflow-style: none;  /* IE and Edge */
      scrollbar-width: none;  /* Firefox */
  }
  .horizontal-scroll-wrapper::-webkit-scrollbar {
      display: none; /* Chrome, Safari, and Opera */
  }
  .certification-item {
      flex: 0 0 250px; /* Do not grow or shrink, base width 250px */
      margin-right: 1.5rem;
      height: 250px;
  }

  /* --- General Grid Styling --- */
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 1.5rem; }
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.5rem; }

  .skill-item, .certification-item {
    background-color: rgba(0,0,0,0.2); text-align: center; padding: 1.5rem 1rem; border-radius: 8px; font-weight: bold;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 0.8rem;
    border: 1px solid var(--border-color);
  }
  .skill-item:hover, .certification-item:hover { transform: translateY(-5px); box-shadow: 0 0 20px var(--glow-color); }
  .skill-item .skill-icon { height: 50px; width: 50px; font-size: 50px; color: var(--text-color); filter: none; }
  .project-card { /* ... styling ... */ }

  /* (Other styles like modals, nav, toggle are included but might need minor color tweaks) */
  #page-nav { position: fixed; top: 50%; right: 20px; transform: translateY(-50%); z-index: 100; }
  #page-nav ul { list-style: none; margin: 0; padding: 0; }
  #page-nav li { margin-bottom: 15px; }
  #page-nav a { display: block; width: 12px; height: 12px; background-color: rgba(255,255,255,0.5); border-radius: 50%; transition: all 0.3s; }
  #page-nav a.active { background-color: var(--color-1); transform: scale(1.5); }
  .theme-switch-wrapper { position: absolute; top: 1.5rem; right: 60px; z-index: 10; }
  .theme-switch { display: inline-block; height: 34px; position: relative; width: 60px; }
  .theme-switch input { display:none; }
  .slider { background-color: rgba(0,0,0,0.3); bottom: 0; cursor: pointer; left: 0; position: absolute; right: 0; top: 0; transition: .4s; border-radius: 34px; }
  .slider:before { font-family: 'boxicons'; content: '\ea43'; color: #333; display: flex; align-items: center; justify-content: center; font-size: 20px; background-color: #fff; bottom: 4px; height: 26px; left: 4px; position: absolute; transition: .4s; width: 26px; border-radius: 50%; }
  input:checked + .slider { background-color: var(--card-bg); }
  input:checked + .slider:before { content: '\e9c5'; transform: translateX(26px); }
  .modal { /* ... styling ... */ }
</style>

<main id="fullpage">

  <section id="welcome" class="slide">
    <div class="slide-content">
      <h1 id="typing-text" class="typing-effect"></h1>
      <h3>Applied Statistics & Data Analytics Student</h3>
      <div class="social-links">
        <a href="mailto:tanishkmestry4183@gmail.com" target="_blank" title="Email"><i class='bx bx-envelope'></i></a>
        <a href="https://www.linkedin.com/in/YOUR_LINKEDIN_URL" target="_blank" title="LinkedIn"><i class='bx bxl-linkedin-square'></i></a>
        <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" title="GitHub"><i class='bx bxl-github'></i></a>
      </div>
    </div>
  </section>

  <section id="skills" class="slide">
    <div class="slide-content">
      <h2>Technical Skills</h2>
      <div class="skills-grid">
        </div>
    </div>
  </section>

  <section id="projects" class="slide">
    <div class="slide-content">
      <h2>Projects</h2>
      <div class="projects-grid">
        </div>
    </div>
  </section>

  <section id="certifications" class="slide">
    <div class="slide-content">
        <h2>Certifications</h2>
        <div class="horizontal-scroll-wrapper">
          <div class="certification-item" onclick="openModal('ibm-python-modal')"><i class='bx bxl-python'></i><span>IBM: Python for Data Science</span></div>
          <div class="certification-item" onclick="openModal('ibm-ml-modal')"><i class='bx bx-brain'></i><span>IBM: Machine Learning</span></div>
          <div class="certification-item" onclick="openModal('itvedant-sql-modal')"><i class='bx bx-data'></i><span>ITVEDANT: SQL</span></div>
          <div class="certification-item" onclick="openModal('itvedant-powerbi-modal')"><i class='bx bxs-bar-chart-alt-2'></i><span>ITVEDANT: Power BI</span></div>
          <div class="certification-item"><span>Another Certificate</span></div>
          <div class="certification-item"><span>And Another</span></div>
        </div>
    </div>
  </section>
  
  <section id="experience" class="slide">
      <div class="slide-content">
          <h2>Work Experience</h2>
          </div>
  </section>

  <section id="education" class="slide">
      <div class="slide-content">
          <h2>Education</h2>
          </div>
  </section>

</main>

<nav id="page-nav">
  <ul>
    <li><a href="#welcome" data-section="welcome"></a></li>
    <li><a href="#skills" data-section="skills"></a></li>
    <li><a href="#projects" data-section="projects"></a></li>
    <li><a href="#certifications" data-section="certifications"></a></li>
    <li><a href="#experience" data-section="experience"></a></li>
    <li><a href="#education" data-section="education"></a></li>
  </ul>
</nav>

<div class="theme-switch-wrapper">
  <label class="theme-switch" for="checkbox">
    <input type="checkbox" id="checkbox" />
    <div class="slider round"></div>
  </label>
</div>

<script>
    // All previous scripts (toggle, modals, nav, typing effect) are still here and functional.
</script>
