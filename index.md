---
layout: default
title: Tanishk Manoj Mestry - Portfolio
---

<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;700&display=swap');

  /* Global Theme Variables */
  :root {
    --primary-color: #8a2be2;
    --glow-color: #8a2be2;
    --bg-color: #11111a;
    --card-bg: #1a1a2e;
    --text-color: #e0e0e0;
    --border-color: #444455;
    --grid-line-color: #2a2a4a;
    --glow-color-rgb: 138, 43, 226;
  }

  body.light-theme {
    --primary-color: #483d8b;
    --glow-color: #483d8b;
    --bg-color: #f5f5f5;
    --card-bg: #ffffff;
    --text-color: #1c1c1c;
    --border-color: #dddddd;
    --grid-line-color: #cccccc;
    --glow-color-rgb: 72, 61, 139;
  }
  
  html {
    scroll-behavior: smooth;
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0; padding: 0;
    scroll-snap-type: y mandatory;
    overflow-y: scroll;
    height: 100vh;
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
    background-image: linear-gradient(0deg, var(--grid-line-color) 1px, transparent 1px), 
                      linear-gradient(90deg, var(--grid-line-color) 1px, transparent 1px);
    background-size: 30px 30px;
    background-color: var(--bg-color);
  }

  .slide:nth-of-type(2n) {
      background-color: var(--card-bg);
      background-image: none;
  }

  .slide-content {
    width: 100%;
    max-width: 1200px;
    text-align: center;
  }

  .slide-content h2 {
    font-size: 3rem;
    color: var(--primary-color);
    margin-bottom: 3rem;
  }
  
  #welcome .typing-effect {
    font-size: 3.5rem;
    font-weight: 700;
    color: var(--primary-color);
    border-right: 2px solid var(--primary-color);
    white-space: nowrap;
    overflow: hidden;
    margin: 0 auto;
    animation: typing 3s steps(30, end), blink-caret .75s step-end infinite;
  }
  @keyframes typing { from { width: 0 } to { width: 100% } }
  @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--primary-color); } }

  #welcome h3 { font-size: 1.5rem; font-weight: 300; margin: 1rem 0 2rem 0; }
  #welcome .social-links a { font-size: 2rem; margin: 0 1rem; color: var(--text-color); }
  #welcome .social-links a:hover { color: var(--primary-color); }
  
  .skills-grid, .certifications-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 1.5rem; }
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.5rem; }

  .skill-item, .certification-item {
    background-color: var(--bg-color); text-align: center; padding: 1.5rem 1rem; border-radius: 8px; font-weight: bold;
    transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
    display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 0.8rem;
    border: 1px solid var(--border-color); box-shadow: 0 0 5px rgba(0,0,0,0.5);
  }
  .skill-item:hover, .certification-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 0 25px rgba(var(--glow-color-rgb), 0.7), 0 0 10px var(--glow-color);
    border-color: var(--glow-color);
  }

  .skill-item .skill-icon {
    height: 50px;
    width: 50px;
    font-size: 50px;
    color: #ffffff;
    filter: drop-shadow(0 0 3px var(--glow-color)) drop-shadow(0 0 8px rgba(138, 43, 226, 0.6)) drop-shadow(0 0 15px rgba(138, 43, 226, 0.4));
    transition: filter 0.3s ease;
  }

  .skill-item:hover .skill-icon {
    filter: drop-shadow(0 0 5px var(--glow-color)) drop-shadow(0 0 12px rgba(138, 43, 226, 0.8)) drop-shadow(0 0 20px rgba(138, 43, 226, 0.6));
  }
  
  .certification-item { cursor: pointer; }
  .certification-item i { font-size: 50px; color: var(--primary-color); margin-bottom: 0.5rem; }
  .project-card { background-color: var(--bg-color); border: 1px solid var(--border-color); border-radius: 8px; padding: 1.5rem; transition: transform 0.3s ease, border-color 0.3s ease; box-shadow: 0 0 5px rgba(0,0,0,0.5); cursor: pointer; }
  .project-card:hover { transform: scale(1.03); border-color: var(--primary-color); }
  .project-card h3 { margin-top: 0; color: var(--primary-color); }
  .project-card .tech-tag { background-color: var(--primary-color); color: var(--bg-color); padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.8rem; font-weight: bold; }
  details { margin-bottom: 1rem; border-left: 3px solid var(--primary-color); padding-left: 15px; text-align: left; }
  summary { cursor: pointer; font-weight: bold; font-size: 1.1rem; outline: none; color: var(--text-color); }
  summary:hover { color: var(--primary-color); }
  .job-title, .degree-title { font-style: italic; color: var(--text-color); opacity: 0.7; }
  
  #page-nav { position: fixed; top: 50%; right: 20px; transform: translateY(-50%); z-index: 100; }
  #page-nav ul { list-style: none; margin: 0; padding: 0; }
  #page-nav li { margin-bottom: 15px; }
  #page-nav a { display: block; width: 12px; height: 12px; background-color: var(--border-color); border-radius: 50%; transition: background-color 0.3s, transform 0.3s; }
  #page-nav a.active { background-color: var(--primary-color); transform: scale(1.5); }

  .theme-switch-wrapper { position: absolute; top: 1.5rem; right: 60px; z-index: 10; }
  .theme-switch { display: inline-block; height: 34px; position: relative; width: 60px; }
  .theme-switch input { display:none; }
  .slider { background-color: #555; bottom: 0; cursor: pointer; left: 0; position: absolute; right: 0; top: 0; transition: .4s; border-radius: 34px; }
  .slider:before { font-family: 'boxicons'; content: '\ea43'; color: var(--bg-color); display: flex; align-items: center; justify-content: center; font-size: 20px; background-color: #fff; bottom: 4px; height: 26px; left: 4px; position: absolute; transition: .4s; width: 26px; border-radius: 50%; }
  input:checked + .slider { background-color: var(--primary-color); }
  input:checked + .slider:before { content: '\e9c5'; transform: translateX(26px); }
  .modal { display: none; position: fixed; z-index: 1000; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.8); backdrop-filter: blur(5px); }
  .modal-content { background-color: var(--card-bg); margin: 5% auto; padding: 20px; border: 1px solid var(--border-color); width: 80%; max-width: 900px; position: relative; border-radius: 8px; animation: fadeIn 0.5s; }
  @keyframes fadeIn { from {opacity: 0; transform: scale(0.9);} to {opacity: 1; transform: scale(1);} }
  .modal-content img { width: 100%; border-radius: 4px; }
  .close-button { color: #aaaaaa; position: absolute; top: 10px; right: 25px; font-size: 35px; font-weight: bold; cursor: pointer; }
  .close-button:hover, .close-button:focus { color: var(--primary-color); }
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
        <div class="skill-item"><i class='bx bxl-python skill-icon'></i><span>Python</span></div>
        <div class="skill-item"><i class='bx bx-data skill-icon'></i><span>SQL</span></div>
        <div class="skill-item"><i class='bx bxs-bar-chart-alt-2 skill-icon'></i><span>Power BI</span></div>
        <div class="skill-item">
          <svg class="skill-icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48">
            <rect width="1.5" height="9" x="22.75" y="1" fill="#78909c"></rect><rect width="9" height="1.5" x="19" y="4.75" fill="#78909c"></rect><rect width="1.5" height="9" x="40.75" y="19" fill="#5c6bc0"></rect><rect width="9" height="1.5" x="37" y="22.75" fill="#5c6bc0"></rect><rect width="1.5" height="9" x="4.75" y="19" fill="#78909c"></rect><rect width="9" height="1.5" x="1" y="22.75" fill="#78909c"></rect><rect width="1.5" height="9" x="22.75" y="37" fill="#5c6bc0"></rect><rect width="9" height="1.5" x="19" y="40.75" fill="#5c6bc0"></rect><rect width="17" height="3" x="15" y="22" fill="#e8762d"></rect><rect width="3" height="17" x="22" y="15" fill="#e8762d"></rect><rect width="2" height="14" x="11" y="6" fill="#ffa000"></rect><rect width="14" height="2" x="5" y="12" fill="#ffa000"></rect><rect width="2" height="14" x="34" y="6" fill="#607d8b"></rect><rect width="14" height="2" x="28" y="12" fill="#607d8b"></rect><rect width="2" height="14" x="11" y="27" fill="#c62828"></rect><rect width="14" height="2" x="5" y="33" fill="#c62828"></rect><rect width="2" height="14" x="34" y="27" fill="#0d47a1"></rect><rect width="14" height="2" x="28" y="33" fill="#0d47a1"></rect>
          </svg>
          <span>Tableau</span>
        </div>
        <div class="skill-item"><i class='bx bx-math skill-icon'></i><span>R</span></div>
        <div class="skill-item">
          <svg class="skill-icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48">
            <path fill="#169154" d="M29,6H15.744C14.781,6,14,6.781,14,7.744v7.259h15V6z"></path><path fill="#18482a" d="M14,33.054v7.202C14,41.219,14.781,42,15.743,42H29v-8.946H14z"></path><path fill="#0c8045" d="M14 15.003H29V24.005000000000003H14z"></path><path fill="#17472a" d="M14 24.005H29V33.055H14z"></path><g><path fill="#29c27f" d="M42.256,6H29v9.003h15V7.744C44,6.781,43.219,6,42.256,6z"></path><path fill="#27663f" d="M29,33.054V42h13.257C43.219,42,44,41.219,44,40.257v-7.202H29z"></path><path fill="#19ac65" d="M29 15.003H44V24.005000000000003H29z"></path><path fill="#129652" d="M29 24.005H44V33.055H29z"></path></g><path fill="#0c7238" d="M22.319,34H5.681C4.753,34,4,33.247,4,32.319V15.681C4,14.753,4.753,14,5.681,14h16.638 C23.247,14,24,14.753,24,15.681v16.638C24,33.247,23.247,34,22.319,34z"></path><path fill="#fff" d="M9.807 19L12.193 19 14.129 22.754 16.175 19 18.404 19 15.333 24 18.474 29 16.123 29 14.013 25.07 11.912 29 9.526 29 12.719 23.982z"></path>
          </svg>
          <span>Advanced Excel</span>
        </div>
        <div class="skill-item"><i class='bx bxs-chip skill-icon'></i><span>MATLAB</span></div>
        <div class="skill-item"><i class='bx bx-brain skill-icon'></i><span>Machine Learning</span></div>
      </div>
    </div>
  </section>

  <section id="projects" class="slide">
    <div class="slide-content">
      <h2>Projects</h2>
      <div class="projects-grid">
        <div class="project-card" onclick="openModal('youtube-modal')"><span class="tech-tag">Power BI</span><h3>Global YouTube Statistics</h3><p>Developed an interactive dashboard to evaluate channel performance, video views, and earnings.</p></div>
        <div class="project-card" onclick="openModal('sales-modal')"><span class="tech-tag">Excel</span><h3>Product Sales Analysis</h3><p>Designed an interactive dashboard to analyse product sales trends for performance tracking.</p></div>
        <div class="project-card" onclick="openModal('game-modal')"><span class="tech-tag">Tableau</span><h3>Video Game Sales Analysis</h3><p>Built a dynamic dashboard to analyze regional video game sales and identify key trends.</p></div>
        <div class="project-card" onclick="openModal('library-modal')"><span class="tech-tag">SQL</span><h3>Library Management System</h3><p>Created a comprehensive system for managing book inventory and tracking member activities.</p></div>
      </div>
    </div>
  </section>

  <section id="certifications" class="slide">
    <div class="slide-content">
      <h2>Certifications</h2>
      <div class="certifications-grid">
        <div class="certification-item" onclick="openModal('ibm-python-modal')"><i class='bx bxl-python'></i><span>IBM: Python for Data Science</span></div>
        <div class="certification-item" onclick="openModal('ibm-ml-modal')"><i class='bx bx-brain'></i><span>IBM: Machine Learning</span></div>
        <div class="certification-item" onclick="openModal('itvedant-sql-modal')"><i class='bx bx-data'></i><span>ITVEDANT: SQL</span></div>
        <div class="certification-item" onclick="openModal('itvedant-powerbi-modal')"><i class='bx bxs-bar-chart-alt-2'></i><span>ITVEDANT: Power BI</span></div>
      </div>
    </div>
  </section>
  
  <section id="experience" class="slide">
      <div class="slide-content">
          <h2>Work Experience</h2>
          <details><summary>Bhoir & Patil Associates, Tax Consultants (Apr 2024 - Mar 2025)</summary><p class="job-title">Accounts Assistant</p><ul><li>Managed and entered client financial data using Tally.</li><li>Prepared and analysed financial statements in Excel.</li><li>Ensured tax compliance by generating accurate reports through GST software.</li></ul></details>
      </div>
  </section>

  <section id="education" class="slide">
      <div class="slide-content">
          <h2>Education</h2>
          <details><summary>SVKM's Mithibai College (Expected: April 2026)</summary><p class="job-title">B.Sc. in Applied Statistics & Data Analytics</p></details>
          <details><summary>ITVEDANT (Jan 2025)</summary><p class="job-title">Master in Data Science & Analytics with Artificial Intelligence</p></details>
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

<div id="youtube-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('youtube-modal')">&times;</span><h2>Global YouTube Statistics</h2><img src="images/placeholder.png" alt="YouTube Project Screenshot"><p>Here you can add a more detailed description of the project.</p></div></div>
<div id="sales-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('sales-modal')">&times;</span><h2>Product Sales Analysis</h2><img src="images/placeholder.png" alt="Sales Project Screenshot"></div></div>
<div id="game-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('game-modal')">&times;</span><h2>Video Game Sales Analysis</h2><img src="images/placeholder.png" alt="Game Project Screenshot"></div></div>
<div id="library-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('library-modal')">&times;</span><h2>Library Management System</h2><img src="images/placeholder.png" alt="Library Project Screenshot"></div></div>
<div id="ibm-python-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('ibm-python-modal')">&times;</span><img src="images/placeholder.png" alt="IBM Python Certificate"></div></div>
<div id="ibm-ml-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('ibm-ml-modal')">&times;</span><img src="images/placeholder.png" alt="IBM Machine Learning Certificate"></div></div>
<div id="itvedant-sql-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('itvedant-sql-modal')">&times;</span><img src="images/placeholder.png" alt="ITVEDANT SQL Certificate"></div></div>
<div id="itvedant-powerbi-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('itvedant-powerbi-modal')">&times;</span><img src="images/placeholder.png" alt="ITVEDANT Power BI Certificate"></div></div>

<script>
  // Theme Toggle Script
  const toggleSwitch = document.querySelector('.theme-switch input[type="checkbox"]');
  const currentTheme = localStorage.getItem('theme');
  if (currentTheme) { document.body.classList.add(currentTheme); if (currentTheme === 'light-theme') { toggleSwitch.checked = true; } }
  function switchTheme(e) { if (e.target.checked) { document.body.classList.add('light-theme'); localStorage.setItem('theme', 'light-theme'); } else { document.body.classList.remove('light-theme'); localStorage.setItem('theme', 'dark-theme'); } }
  toggleSwitch.addEventListener('change', switchTheme, false);

  // Modal Control Script
  function openModal(modalId) { document.getElementById(modalId).style.display = "block"; }
  function closeModal(modalId) { document.getElementById(modalId).style.display = "none"; }
  window.onclick = function(event) { if (event.target.classList.contains('modal')) { event.target.style.display = "none"; } }

  // Typing Effect Script
  const textToType = "TANISHK MANOJ MESTRY";
  const typingElement = document.getElementById('typing-text');
  function typeEffect() {
    typingElement.style.width = '0';
    typingElement.textContent = textToType;
    typingElement.style.animation = 'none';
    setTimeout(() => { typingElement.style.animation = ''; }, 10);
  }
  typeEffect();
  setInterval(typeEffect, 10000);

  // Side Navigation Active State Script
  const sections = document.querySelectorAll('.slide');
  const navLi = document.querySelectorAll("#page-nav ul li a");
  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const sectionId = entry.target.id;
        navLi.forEach(a => {
          a.classList.remove("active");
          if (a.dataset.section === sectionId) {
            a.classList.add("active");
          }
        });
      }
    });
  }, { threshold: 0.7 });

  sections.forEach(section => {
    observer.observe(section);
  });
</script>
