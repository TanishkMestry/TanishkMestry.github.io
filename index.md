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
    --sidebar-bg: #1a1a2e;
    --content-bg: #11111a;
    --card-bg: #222233;
    --text-color: #e0e0e0;
    --border-color: #444455;
    --grid-line-color: #2a2a4a;
  }

  body.light-theme {
    --primary-color: #483d8b;
    --glow-color: #483d8b;
    --bg-color: #f5f5f5;
    --sidebar-bg: #e0e0eb;
    --content-bg: #f5f5f5;
    --card-bg: #ffffff;
    --text-color: #1c1c1c;
    --border-color: #dddddd;
    --grid-line-color: #cccccc;
  }
  
  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0; padding: 0;
    display: flex;
    transition: background-color 0.3s, color 0.3s;
  }

  /* --- Sidebar Styling --- */
  .sidebar {
    width: 380px;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    background-color: var(--sidebar-bg);
    border-right: 1px solid var(--border-color);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    box-sizing: border-box;
    z-index: 10;
  }
  .sidebar h1 { font-size: 2.2rem; color: var(--primary-color); margin: 0; }
  .sidebar h2 { font-size: 1rem; font-weight: 300; margin: 0.5rem 0 2rem 0; }
  .sidebar .social-links a { font-size: 1.8rem; margin: 0 1rem; color: var(--text-color); }
  .sidebar .social-links a:hover { color: var(--primary-color); }

  /* --- Main Content Area Styling --- */
  .main-content {
    margin-left: 380px;
    width: calc(100% - 380px);
    padding: 4rem;
    box-sizing: border-box;
    background-image: linear-gradient(0deg, var(--grid-line-color) 1px, transparent 1px), 
                      linear-gradient(90deg, var(--grid-line-color) 1px, transparent 1px);
    background-size: 30px 30px;
    background-color: var(--content-bg);
  }

  .section { margin-bottom: 4rem; }
  .section h2 { color: var(--primary-color); border-bottom: 2px solid var(--primary-color); padding-bottom: 10px; margin-top: 0; margin-bottom: 2rem; text-align: left; }

  /* --- Theme Toggle Styling --- */
  .theme-switch-wrapper { position: absolute; top: 1.5rem; right: 1.5rem; }
  .theme-switch { display: inline-block; height: 34px; position: relative; width: 60px; }
  .theme-switch input { display:none; }
  .slider { background-color: #555; bottom: 0; cursor: pointer; left: 0; position: absolute; right: 0; top: 0; transition: .4s; border-radius: 34px; }

  .slider:before {
    font-family: 'boxicons';
    content: '\e9c5'; /* Moon icon */
    color: var(--sidebar-bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    background-color: #fff;
    bottom: 4px;
    height: 26px;
    left: 4px;
    position: absolute;
    transition: .4s;
    width: 26px;
    border-radius: 50%;
  }
  
  input:checked + .slider { background-color: var(--primary-color); }
  input:checked + .slider:before {
    content: '\ea43'; /* Sun icon */
    transform: translateX(26px);
  }

  /* (Other styles) */
  :root { --glow-color-rgb: 138, 43, 226; }
  body.light-theme { --glow-color-rgb: 72, 61, 139; }
  .skills-grid, .certifications-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 1.5rem; }
  .skill-item, .certification-item { background-color: var(--card-bg); text-align: center; padding: 1.5rem 1rem; border-radius: 8px; font-weight: bold; transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 0.8rem; border: 1px solid var(--border-color); box-shadow: 0 0 5px rgba(0,0,0,0.5); }
  .skill-item:hover, .certification-item:hover { transform: translateY(-5px); box-shadow: 0 0 25px rgba(var(--glow-color-rgb), 0.7), 0 0 10px var(--glow-color); border-color: var(--glow-color); }
  .skill-item .skill-icon { font-size: 50px; color: #ffffff; filter: drop-shadow(0 0 3px var(--glow-color)) drop-shadow(0 0 8px rgba(138, 43, 226, 0.6)) drop-shadow(0 0 15px rgba(138, 43, 226, 0.4)); transition: filter 0.3s ease; }
  .skill-item:hover .skill-icon { filter: drop-shadow(0 0 5px var(--glow-color)) drop-shadow(0 0 12px rgba(138, 43, 226, 0.8)) drop-shadow(0 0 20px rgba(138, 43, 226, 0.6)); }
  .certification-item { cursor: pointer; }
  .certification-item i { font-size: 50px; color: var(--primary-color); margin-bottom: 0.5rem; }
  .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.5rem; }
  .project-card { background-color: var(--card-bg); border: 1px solid var(--border-color); border-radius: 8px; padding: 1.5rem; transition: transform 0.3s ease, border-color 0.3s ease; box-shadow: 0 0 5px rgba(0,0,0,0.5); cursor: pointer; }
  .project-card:hover { transform: scale(1.03); border-color: var(--primary-color); }
  .project-card h3 { margin-top: 0; color: var(--primary-color); }
  .project-card .tech-tag { background-color: var(--primary-color); color: var(--sidebar-bg); padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.8rem; font-weight: bold; }
  details { margin-bottom: 1rem; border-left: 3px solid var(--primary-color); padding-left: 15px; }
  summary { cursor: pointer; font-weight: bold; font-size: 1.1rem; outline: none; color: var(--text-color); }
  summary:hover { color: var(--primary-color); }
  .job-title, .degree-title { font-style: italic; color: var(--text-color); opacity: 0.7; }
  .modal { display: none; position: fixed; z-index: 1000; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.8); backdrop-filter: blur(5px); }
  .modal-content { background-color: var(--card-bg); margin: 5% auto; padding: 20px; border: 1px solid var(--border-color); width: 80%; max-width: 900px; position: relative; border-radius: 8px; animation: fadeIn 0.5s; }
  @keyframes fadeIn { from {opacity: 0; transform: scale(0.9);} to {opacity: 1; transform: scale(1);} }
  .modal-content img { width: 100%; border-radius: 4px; }
  .close-button { color: #aaaaaa; position: absolute; top: 10px; right: 25px; font-size: 35px; font-weight: bold; cursor: pointer; }
  .close-button:hover, .close-button:focus { color: var(--primary-color); }
  @media (max-width: 1024px) { body { flex-direction: column; } .sidebar { position: relative; width: 100%; height: auto; border-right: none; border-bottom: 1px solid var(--border-color); } .main-content { margin-left: 0; width: 100%; padding: 2rem; } }
</style>

<div class="sidebar">
  <div class="theme-switch-wrapper">
    <label class="theme-switch" for="checkbox">
      <input type="checkbox" id="checkbox" />
      <div class="slider round"></div>
    </label>
  </div>
  
  <h1>TANISHK MANOJ MESTRY</h1>
  <h2>Applied Statistics & Data Analytics Student</h2>
  
  <div class="social-links">
    <a href="mailto:tanishkmestry4183@gmail.com" target="_blank" title="Email"><i class='bx bx-envelope'></i></a>
    <a href="https://www.linkedin.com/in/YOUR_LINKEDIN_URL" target="_blank" title="LinkedIn"><i class='bx bxl-linkedin-square'></i></a>
    <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" title="GitHub"><i class='bx bxl-github'></i></a>
  </div>
</div>

<div class="main-content">

  <section id="skills" class="section">
    <h2>Technical Skills</h2>
    <div class="skills-grid">
      <div class="skill-item"><i class='bx bxl-python skill-icon'></i><span>Python</span></div>
      <div class="skill-item"><i class='bx bx-data skill-icon'></i><span>SQL</span></div>
      <div class="skill-item"><i class='bx bxs-bar-chart-alt-2 skill-icon'></i><span>Power BI</span></div>
      <div class="skill-item"><i class='bx bxs-pie-chart-alt-2 skill-icon'></i><span>Tableau</span></div>
      <div class="skill-item"><i class='bx bx-math skill-icon'></i><span>R</span></div>
      <div class="skill-item"><i class='bx bxs-file-spreadsheet skill-icon'></i><span>Advanced Excel</span></div>
      <div class="skill-item"><i class='bx bxs-chip skill-icon'></i><span>MATLAB</span></div>
      <div class="skill-item"><i class='bx bx-brain skill-icon'></i><span>Machine Learning</span></div>
    </div>
  </section>

  <section id="projects" class="section">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card" onclick="openModal('youtube-modal')">
        <span class="tech-tag">Power BI</span><h3>Global YouTube Statistics</h3>
        <p>Developed an interactive dashboard to evaluate channel performance, video views, and earnings.</p>
      </div>
      <div class="project-card" onclick="openModal('sales-modal')">
        <span class="tech-tag">Excel</span><h3>Product Sales Analysis</h3>
        <p>Designed an interactive dashboard to analyse product sales trends for performance tracking.</p>
      </div>
      <div class="project-card" onclick="openModal('game-modal')">
        <span class="tech-tag">Tableau</span><h3>Video Game Sales Analysis</h3>
        <p>Built a dynamic dashboard to analyze regional video game sales and identify key trends.</p>
      </div>
      <div class="project-card" onclick="openModal('library-modal')">
        <span class="tech-tag">SQL</span><h3>Library Management System</h3>
        <p>Created a comprehensive system for managing book inventory and tracking member activities.</p>
      </div>
    </div>
  </section>

  <section id="certifications" class="section">
    <h2>Certifications</h2>
    <div class="certifications-grid">
      <div class="certification-item" onclick="openModal('ibm-python-modal')"><i class='bx bxl-python'></i><span>IBM: Python for Data Science</span></div>
      <div class="certification-item" onclick="openModal('ibm-ml-modal')"><i class='bx bx-brain'></i><span>IBM: Machine Learning</span></div>
      <div class="certification-item" onclick="openModal('itvedant-sql-modal')"><i class='bx bx-data'></i><span>ITVEDANT: SQL</span></div>
      <div class="certification-item" onclick="openModal('itvedant-powerbi-modal')"><i class='bx bxs-bar-chart-alt-2'></i><span>ITVEDANT: Power BI</span></div>
    </div>
  </section>

  <section id="experience" class="section">
    <h2>Work Experience</h2>
    <details>
      <summary>Bhoir & Patil Associates, Tax Consultants (Apr 2024 - Mar 2025)</summary>
      <p class="job-title">Accounts Assistant</p>
      <ul>
        <li>Managed and entered client financial data using Tally.</li>
        <li>Prepared and analysed financial statements in Excel.</li>
        <li>Ensured tax compliance by generating accurate reports through GST software.</li>
      </ul>
    </details>
  </section>

  <section id="education" class="section">
    <h2>Education</h2>
    <details>
      <summary>SVKM's Mithibai College (Expected: April 2026)</summary>
      <p class="job-title">B.Sc. in Applied Statistics & Data Analytics</p>
    </details>
    <details>
      <summary>ITVEDANT (Jan 2025)</summary>
      <p class="job-title">Master in Data Science & Analytics with Artificial Intelligence</p>
    </details>
  </section>

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

  // Modal Control Script
  function openModal(modalId) {
    document.getElementById(modalId).style.display = "block";
  }
  function closeModal(modalId) {
    document.getElementById(modalId).style.display = "none";
  }
  window.onclick = function(event) {
    if (event.target.classList.contains('modal')) {
      event.target.style.display = "none";
    }
  }
</script>
