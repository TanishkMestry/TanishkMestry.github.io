---
layout: default
title: Tanishk Manoj Mestry - Portfolio
---

<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap');

  :root {
    --bg-color: #101015;
    --card-bg: #1a1a2e;
    --text-color: #f0f0f0;
    --text-muted: #a0a0a0;
    --border-color: rgba(255, 255, 255, 0.1);
    --primary: #8a2be2;
  }
  body.light-theme {
    --bg-color: #f5f5fa;
    --card-bg: #ffffff;
    --text-color: #1c1c1c;
    --text-muted: #555;
    --border-color: rgba(0, 0, 0, 0.1);
  }
  
  html { scroll-behavior: smooth; }
  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0;
    padding: 0;
    line-height: 1.6;
    transition: background-color 0.3s, color 0.3s;
  }
  .wrapper { max-width: 1100px; margin: 0 auto; padding: 4rem 2rem; }
  
  header { text-align: center; margin-bottom: 6rem; }
  h1 { font-size: 2.5rem; margin-bottom: 0.5rem; }
  h2 { font-size: 2rem; margin-bottom: 3rem; color: var(--primary); }
  p.subtitle { color: var(--text-muted); max-width: 600px; margin: 1rem auto 2rem auto; }
  
  .social-links a { color: var(--text-muted); text-decoration: none; font-size: 1.5rem; margin: 0 0.75rem; transition: color 0.3s; }
  .social-links a:hover { color: var(--primary); }
  
  section { margin-bottom: 6rem; }
  
  .grid {
    display: grid;
    gap: 1.5rem;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  }
  
  .project-card, .cert-card {
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 8px;
    padding: 1.5rem;
    transition: transform 0.3s, box-shadow 0.3s;
    cursor: pointer;
  }
  .project-card:hover, .cert-card:hover { transform: translateY(-5px); box-shadow: 0 10px 20px rgba(0,0,0,0.2); }
  .project-card h3 { margin: 0 0 0.5rem 0; }
  .cert-card { text-align: center; }
  .cert-card i { font-size: 2.5rem; color: var(--primary); margin-bottom: 1rem; }
  
  .theme-switch { position: fixed; top: 1rem; right: 1rem; cursor: pointer; }
  .theme-switch svg { width: 24px; height: 24px; fill: var(--text-muted); }

  .modal { display: none; position: fixed; z-index: 1000; left: 0; top: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.8); }
  .modal-content { background-color: var(--card-bg); margin: 10% auto; padding: 20px; border-radius: 8px; width: 80%; max-width: 700px; position: relative; }
  .modal-content img { width: 100%; }
  .close-button { color: #aaa; position: absolute; top: 10px; right: 25px; font-size: 35px; cursor: pointer; }
</style>

<div class="wrapper">

  <label class="theme-switch" for="checkbox">
    <input type="checkbox" id="checkbox" style="display:none;" />
    <svg id="theme-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 9a3 3 0 1 0 0 6a3 3 0 0 0 0-6m0-2a5 5 0 1 1 0 10a5 5 0 0 1 0-10m0-5a1 1 0 0 1 1 1v2a1 1 0 0 1-2 0V3a1 1 0 0 1 1-1m0 20a1 1 0 0 1-1-1v-2a1 1 0 0 1 2 0v2a1 1 0 0 1-1 1M5.6 7.05a1 1 0 0 1 1.41-1.41l1.42 1.41a1 1 0 1 1-1.42 1.42L5.6 7.05m12.73 9.9a1 1 0 0 1 1.41-1.41l1.42 1.41a1 1 0 1 1-1.42 1.42l-1.41-1.42M19.07 7.05a1 1 0 0 1-1.41 1.41l-1.42-1.41a1 1 0 1 1 1.42-1.42l1.41 1.41M7.01 18.36a1 1 0 0 1-1.41 1.41l-1.42-1.41a1 1 0 1 1 1.42-1.42l1.41 1.41M2 13a1 1 0 0 1-1-1h-2a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1m20 0a1 1 0 0 1-1-1h-2a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1"/></svg>
  </label>
  
  <header>
    <h1>Tanishk Manoj Mestry</h1>
    <p class="subtitle">Applied Statistics and Data Analytics student with strong skills in data analysis, statistical modelling, and visualization.</p>
    <div class="social-links">
      <a href="mailto:tanishkmestry4183@gmail.com" target="_blank" title="Email"><i class='bx bx-envelope'></i></a>
      <a href="#" target="_blank" title="LinkedIn"><i class='bx bxl-linkedin-square'></i></a>
      <a href="#" target="_blank" title="GitHub"><i class='bx bxl-github'></i></a>
    </div>
  </header>

  <section id="projects">
    <h2>Projects</h2>
    <div class="grid">
      <div class="project-card" onclick="openModal('youtube-modal')"><h3>Global YouTube Statistics</h3><p>Power BI</p></div>
      <div class="project-card" onclick="openModal('sales-modal')"><h3>Product Sales Analysis</h3><p>Excel</p></div>
      <div class="project-card" onclick="openModal('game-modal')"><h3>Video Game Sales Analysis</h3><p>Tableau</p></div>
      <div class="project-card" onclick="openModal('library-modal')"><h3>Library Management System</h3><p>SQL</p></div>
    </div>
  </section>

  <section id="certifications">
    <h2>Certifications</h2>
    <div class="grid">
      <div class="cert-card" onclick="openModal('ibm-python-modal')"><i class='bx bxl-python'></i><span>IBM: Python for Data Science</span></div>
      <div class="cert-card" onclick="openModal('ibm-ml-modal')"><i class='bx bx-brain'></i><span>IBM: Machine Learning</span></div>
      <div class="cert-card" onclick="openModal('itvedant-sql-modal')"><i class='bx bx-data'></i><span>ITVEDANT: SQL</span></div>
      <div class="cert-card" onclick="openModal('itvedant-powerbi-modal')"><i class='bx bxs-bar-chart-alt-2'></i><span>ITVEDANT: Power BI</span></div>
    </div>
  </section>

</div>

<div id="youtube-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('youtube-modal')">&times;</span><img src="images/placeholder.png" alt="Project Screenshot"></div></div>
<div id="sales-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('sales-modal')">&times;</span><img src="images/placeholder.png" alt="Project Screenshot"></div></div>
<div id="game-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('game-modal')">&times;</span><img src="images/placeholder.png" alt="Project Screenshot"></div></div>
<div id="library-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('library-modal')">&times;</span><img src="images/placeholder.png" alt="Project Screenshot"></div></div>
<div id="ibm-python-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('ibm-python-modal')">&times;</span><img src="images/placeholder.png" alt="Certificate"></div></div>
<div id="ibm-ml-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('ibm-ml-modal')">&times;</span><img src="images/placeholder.png" alt="Certificate"></div></div>
<div id="itvedant-sql-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('itvedant-sql-modal')">&times;</span><img src="images/placeholder.png" alt="Certificate"></div></div>
<div id="itvedant-powerbi-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('itvedant-powerbi-modal')">&times;</span><img src="images/placeholder.png" alt="Certificate"></div></div>

<script>
  const toggleCheckbox = document.getElementById('checkbox');
  const themeIcon = document.getElementById('theme-icon');
  const sunIconPath = "M12 9a3 3 0 1 0 0 6a3 3 0 0 0 0-6m0-2a5 5 0 1 1 0 10a5 5 0 0 1 0-10m0-5a1 1 0 0 1 1 1v2a1 1 0 0 1-2 0V3a1 1 0 0 1 1-1m0 20a1 1 0 0 1-1-1v-2a1 1 0 0 1 2 0v2a1 1 0 0 1-1 1M5.6 7.05a1 1 0 0 1 1.41-1.41l1.42 1.41a1 1 0 1 1-1.42 1.42L5.6 7.05m12.73 9.9a1 1 0 0 1 1.41-1.41l1.42 1.41a1 1 0 1 1-1.42 1.42l-1.41-1.42M19.07 7.05a1 1 0 0 1-1.41 1.41l-1.42-1.41a1 1 0 1 1 1.42-1.42l1.41 1.41M7.01 18.36a1 1 0 0 1-1.41 1.41l-1.42-1.41a1 1 0 1 1 1.42-1.42l1.41 1.41M2 13a1 1 0 0 1-1-1h-2a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1m20 0a1 1 0 0 1-1-1h-2a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1";
  const moonIconPath = "M12 2a10 10 0 1 1 0 20a10 10 0 0 1 0-20m0 2a8 8 0 0 0 0 16a8 8 0 0 0 0-16m-4 8a4 4 0 1 1 8 0a4 4 0 0 1-8 0";

  function setTheme(isLight) {
    document.body.classList.toggle('light-theme', isLight);
    themeIcon.querySelector('path').setAttribute('d', isLight ? moonIconPath : sunIconPath);
    localStorage.setItem('theme', isLight ? 'light' : 'dark');
    toggleCheckbox.checked = isLight;
  }

  toggleCheckbox.addEventListener('change', () => setTheme(toggleCheckbox.checked));
  const savedTheme = localStorage.getItem('theme');
  setTheme(savedTheme === 'light');

  function openModal(modalId) { document.getElementById(modalId).style.display = "block"; }
  function closeModal(modalId) { document.getElementById(modalId).style.display = "none"; }
</script>
