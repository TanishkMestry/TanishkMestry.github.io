---
layout: default
title: Tanishk Mestry - Portfolio
---

<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>

<style>
  @import url('https://fonts.googleapis.comcom/css2?family=Roboto+Mono:wght@300;400;700&display=swap');

  /* --- Vibrant Gradient Theme --- */
  :root {
    --color-1: #ff7e5f;
    --color-2: #feb47b;
    --color-3: #8a2be2;
    --color-4: #00c6ff;
    --card-bg: rgba(26, 26, 46, 0.7);
    --text-color: #f0f0f0;
    --border-color: rgba(255, 255, 255, 0.2);
    --glow-color: #ff7e5f;
  }

  body.light-theme {
    --color-1: #6a11cb;
    --color-2: #2575fc;
    --color-3: #ff007f;
    --color-4: #f8ffae;
    --card-bg: rgba(255, 255, 255, 0.7);
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
    color: var(--text-color);
  }

  #welcome h3 { font-size: 1.5rem; font-weight: 300; margin: 1rem 0 2rem 0; }
  #welcome .social-links a { font-size: 2rem; margin: 0 1rem; color: var(--text-color); transition: color 0.3s; }
  #welcome .social-links a:hover { color: var(--color-1); }
  
  #certifications .slide-content {
      padding: 3rem 0;
  }
  .horizontal-scroll-wrapper {
      display: flex;
      overflow-x: auto;
      padding: 0 3rem 2rem 3rem;
      -ms-overflow-style: none;
      scrollbar-width: none;
  }
  .horizontal-scroll-wrapper::-webkit-scrollbar {
      display: none;
  }
  .certification-item {
      flex: 0 0 250px;
      margin-right: 1.5rem;
      height: 250px;
  }

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
  .certification-item i { font-size: 50px; color: var(--text-color); transition: color 0.3s; }
  .certification-item:hover i { color: var(--color-1); }
  .project-card { background-color: rgba(0,0,0,0.2); border: 1px solid var(--border-color); border-radius: 8px; padding: 1.5rem; transition: transform 0.3s ease, border-color 0.3s ease; cursor: pointer; text-align: left; }
  .project-card:hover { transform: scale(1.03); border-color: var(--color-1); }
  .project-card h3 { margin-top: 0; color: var(--text-color); }
  .project-card .tech-tag { background: linear-gradient(90deg, var(--color-1), var(--color-2)); color: #fff; padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.8rem; font-weight: bold; display: inline-block; margin-bottom: 1rem;}
  details { margin-bottom: 1rem; border-left: 3px solid var(--color-1); padding-left: 15px; text-align: left; }
  summary { cursor: pointer; font-weight: bold; font-size: 1.1rem; outline: none; color: var(--text-color); }
  
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
  .modal { display: none; position: fixed; z-index: 1000; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.8); backdrop-filter: blur(5px); }
  .modal-content { background-color: var(--card-bg); margin: 5% auto; padding: 20px; border: 1px solid var(--border-color); width: 80%; max-width: 900px; position: relative; border-radius: 8px; animation: fadeIn 0.5s; }
  @keyframes fadeIn { from {opacity: 0; transform: scale(0.9);} to {opacity: 1; transform: scale(1);} }
  .modal-content img { width: 100%; border-radius: 4px; }
  .close-button { color: #aaaaaa; position: absolute; top: 10px; right: 25px; font-size: 35px; font-weight: bold; cursor: pointer; }
  .close-button:hover, .close-button:focus { color: var(--color-1); }
</style>

<main id="fullpage">

  <section id="welcome" class="slide">
    <div class="slide-content">
      <h1 id="typing-text" class="typing-effect">TANISHK MANOJ MESTRY</h1>
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
        <div class="skill-item"><svg class="skill-icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48"><linearGradient id="python-gr1" x1="10.458" x2="26.314" y1="12.972" y2="26.277" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#26abe7"></stop><stop offset="1" stop-color="#086dbf"></stop></linearGradient><path fill="url(#python-gr1)" d="M24.047,5c-1.555,0.005-2.633,0.142-3.936,0.367c-3.848,0.67-4.549,2.077-4.549,4.67V14h9v2 H15.22h-4.35c-2.636,0-4.943,1.242-5.674,4.219c-0.826,3.417-0.863,5.557,0,9.125C5.851,32.005,7.294,34,9.931,34h3.632v-5.104 c0-2.966,2.686-5.896,5.764-5.896h7.236c2.523,0,5-1.862,5-4.377v-8.586c0-2.439-1.759-4.263-4.218-4.672 C27.406,5.359,25.589,4.994,24.047,5z M19.063,9c0.821,0,1.5,0.677,1.5,1.502c0,0.833-0.679,1.498-1.5,1.498 c-0.837,0-1.5-0.664-1.5-1.498C17.563,9.68,18.226,9,19.063,9z"></path><linearGradient id="python-gr2" x1="35.334" x2="23.517" y1="37.911" y2="21.034" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#feb705"></stop><stop offset="1" stop-color="#ffda1c"></stop></linearGradient><path fill="url(#python-gr2)" d="M23.078,43c1.555-0.005,2.633-0.142,3.936-0.367c3.848-0.67,4.549-2.077,4.549-4.67V34h-9v-2 h9.343h4.35c2.636,0,4.943-1.242,5.674-4.219c0.826-3.417,0.863-5.557,0-9.125C41.274,15.995,39.831,14,37.194,14h-3.632v5.104 c0,2.966-2.686,5.896-5.764,5.896h-7.236c-2.523,0-5,1.862-5,4.377v8.586c0,2.439,1.759,4.263,4.218,4.672 C19.719,42.641,21.536,43.006,23.078,43z M28.063,39c-0.821,0-1.5-0.677-1.5-1.502c0-0.833,0.679-1.498,1.5,1.498 c0.837,0,1.5,0.664,1.5,1.498C29.563,38.32,28.899,39,28.063,39z"></path></svg><span>Python</span></div>
        <div class="skill-item"><i class='bx bx-data skill-icon'></i><span>SQL</span></div>
        <div class="skill-item"><svg class="skill-icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48"><linearGradient id="powerbi-gr1" x1="32" x2="32" y1="3.947" y2="44.751" gradientUnits="userSpaceOnUse"><stop offset=".006" stop-color="#ebb112"></stop><stop offset="1" stop-color="#bb5c17"></stop></linearGradient><path fill="url(#powerbi-gr1)" d="M27,44h10c1.105,0,2-0.895,2-2V6c0-1.105-0.895-2-2-2H27c-1.105,0-2,0.895-2,2v36 C25,43.105,25.895,44,27,44z"></path><linearGradient id="powerbi-gr2" x1="22.089" x2="26.009" y1="13.14" y2="45.672" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#fed35d"></stop><stop offset=".281" stop-color="#f6c648"></stop><stop offset=".857" stop-color="#e3a513"></stop><stop offset=".989" stop-color="#de9d06"></stop></linearGradient><path fill="url(#powerbi-gr2)" d="M19,44h10c1.105,0,2-0.895,2-2V16c0-1.105-0.895-2-2-2H19c-1.105,0-2,0.895-2,2v26 C17,43.105,17.895,44,19,44z"></path><linearGradient id="powerbi-gr3" x1="9.803" x2="21.335" y1="22.781" y2="43.658" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#ffd869"></stop><stop offset=".983" stop-color="#ffdf26"></stop></linearGradient><path fill="url(#powerbi-gr3)" d="M11,44h10c1.105,0,2-0.895,2-2V26c0-1.105-0.895-2-2-2H11c-1.105,0-2,0.895-2,2v16 C9,43.105,9.895,44,11,44z"></path></svg><span>Power BI</span></div>
        <div class="skill-item"><svg class="skill-icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48"><rect width="1.5" height="9" x="22.75" y="1" fill="#78909c"></rect><rect width="9" height="1.5" x="19" y="4.75" fill="#78909c"></rect><rect width="1.5" height="9" x="40.75" y="19" fill="#5c6bc0"></rect><rect width="9" height="1.5" x="37" y="22.75" fill="#5c6bc0"></rect><rect width="1.5" height="9" x="4.75" y="19" fill="#78909c"></rect><rect width="9" height="1.5" x="1" y="22.75" fill="#78909c"></rect><rect width="1.5" height="9" x="22.75" y="37" fill="#5c6bc0"></rect><rect width="9" height="1.5" x="19" y="40.75" fill="#5c6bc0"></rect><rect width="17" height="3" x="15" y="22" fill="#e8762d"></rect><rect width="3" height="17" x="22" y="15" fill="#e8762d"></rect><rect width="2" height="14" x="11" y="6" fill="#ffa000"></rect><rect width="14" height="2" x="5" y="12" fill="#ffa000"></rect><rect width="2" height="14" x="34" y="6" fill="#607d8b"></rect><rect width="14" height="2" x="28" y="12" fill="#607d8b"></rect><rect width="2" height="14" x="11" y="27" fill="#c62828"></rect><rect width="14" height="2" x="5" y="33" fill="#c62828"></rect><rect width="2" height="14" x="34" y="27" fill="#0d47a1"></rect><rect width="14" height="2" x="28" y="33" fill="#0d47a1"></rect></svg><span>Tableau</span></div>
        <div class="skill-item"><i class='bx bx-math skill-icon'></i><span>R</span></div>
        <div class="skill-item"><svg class="skill-icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48"><path fill="#169154" d="M29,6H15.744C14.781,6,14,6.781,14,7.744v7.259h15V6z"></path><path fill="#18482a" d="M14,33.054v7.202C14,41.219,14.781,42,15.743,42H29v-8.946H14z"></path><path fill="#0c8045" d="M14 15.003H29V24.005000000000003H14z"></path><path fill="#17472a" d="M14 24.005H29V33.055H14z"></path><g><path fill="#29c27f" d="M42.256,6H29v9.003h15V7.744C44,6.781,43.219,6,42.256,6z"></path><path fill="#27663f" d="M29,33.054V42h13.257C43.219,42,44,41.219,44,40.257v-7.202H29z"></path><path fill="#19ac65" d="M29 15.003H44V24.005000000000003H29z"></path><path fill="#129652" d="M29 24.005H44V33.055H29z"></path></g><path fill="#0c7238" d="M22.319,34H5.681C4.753,34,4,33.247,4,32.319V15.681C4,14.753,4.753,14,5.681,14h16.638 C23.247,14,24,14.753,24,15.681v16.638C24,33.247,23.247,34,22.319,34z"></path><path fill="#fff" d="M9.807 19L12.193 19 14.129 22.754 16.175 19 18.404 19 15.333 24 18.474 29 16.123 29 14.013 25.07 11.912 29 9.526 29 12.719 23.982z"></path></svg><span>Advanced Excel</span></div>
        <div class="skill-item"><svg class="skill-icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48"><linearGradient id="matlab-gr1" x1="22.645" x2="26.757" y1="10.881" y2="23.854" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#4adddf"></stop><stop offset=".699" stop-color="#3f5352"></stop><stop offset=".863" stop-color="#442729"></stop></linearGradient><path fill="url(#matlab-gr1)" d="M21,27l-7-6c0,0,1-1.5,2.5-3s2.736-1.852,4.5-3c3.511-2.284,6.5-12,11-12L21,27z"></path><linearGradient id="matlab-gr2" x1="1" x2="37.775" y1="27.033" y2="27.033" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#4adddf"></stop><stop offset=".792" stop-color="#3f5352"></stop><stop offset="1" stop-color="#442729"></stop></linearGradient><polygon fill="url(#matlab-gr2)" points="11,33.066 1,26 14,21 21.277,26.465 14,32.066"></polygon><linearGradient id="matlab-gr3" x1="11" x2="47" y1="24" y2="24" gradientUnits="userSpaceOnUse"><stop offset=".206" stop-color="#53140f"></stop><stop offset=".3" stop-color="#84360f"></stop><stop offset=".413" stop-color="#b85b10"></stop><stop offset=".511" stop-color="#df7610"></stop><stop offset=".59" stop-color="#f68710"></stop><stop offset=".639" stop-color="#ff8d10"></stop><stop offset=".729" stop-color="#fd8a10"></stop><stop offset=".8" stop-color="#f58010"></stop><stop offset=".865" stop-color="#e86f10"></stop><stop offset=".925" stop-color="#d65811"></stop><stop offset=".982" stop-color="#c03a11"></stop><stop offset="1" stop-color="#b72f11"></stop></linearGradient><path fill="url(#matlab-gr3)" d="M32,3c5,0,13,27,15,34c0,0-7.017-6.63-11-6s-5.47,6.548-9.725,10.756C23.5,44.5,21,45,21,45	s-0.206-8.124-5-11c-2.5-1.5-5-1-5-1s6.049-2.901,9.474-8.174S28.5,3,32,3z"></path></svg><span>MATLAB</span></div>
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
        <div class="horizontal-scroll-wrapper">
          <div class="certification-item" onclick="openModal('ibm-python-modal')"><i class='bx bxl-python'></i><span>IBM: Python for Data Science</span></div>
          <div class="certification-item" onclick="openModal('ibm-ml-modal')"><i class='bx bx-brain'></i><span>IBM: Machine Learning</span></div>
          <div class="certification-item" onclick="openModal('itvedant-sql-modal')"><i class='bx bx-data'></i><span>ITVEDANT: SQL</span></div>
          <div class="certification-item" onclick="openModal('itvedant-powerbi-modal')"><i class='bx bxs-bar-chart-alt-2'></i><span>ITVEDANT: Power BI</span></div>
          <div class="certification-item" onclick="openModal('placeholder-modal')"><span>Add Certificate</span></div>
          <div class="certification-item" onclick="openModal('placeholder-modal')"><span>Add Certificate</span></div>
        </div>
    </div>
  </section>
  
  <section id="experience" class="slide">
      <div class="slide-content">
          <h2>Work Experience</h2>
          <details><summary>Bhoir & Patil Associates, Tax Consultants (Apr 2024 - Mar 2025)</summary><p>Accounts Assistant</p><ul><li>Managed and entered client financial data using Tally.</li><li>Prepared and analysed financial statements in Excel.</li><li>Ensured tax compliance by generating accurate reports through GST software.</li></ul></details>
      </div>
  </section>

  <section id="education" class="slide">
      <div class="slide-content">
          <h2>Education</h2>
          <details><summary>SVKM's Mithibai College (Expected: April 2026)</summary><p>B.Sc. in Applied Statistics & Data Analytics</p></details>
          <details><summary>ITVEDANT (Jan 2025)</summary><p>Master in Data Science & Analytics with Artificial Intelligence</p></details>
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
<div id="placeholder-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('placeholder-modal')">&times;</span><img src="images/placeholder.png" alt="Certificate Placeholder"></div></div>

<script>
  // All scripts from before are placed here
  const toggleSwitch = document.querySelector('.theme-switch input[type="checkbox"]');
  const currentTheme = localStorage.getItem('theme');
  if (currentTheme) { document.body.classList.add(currentTheme); if (currentTheme === 'light-theme') { toggleSwitch.checked = true; } }
  function switchTheme(e) { if (e.target.checked) { document.body.classList.add('light-theme'); localStorage.setItem('theme', 'light-theme'); } else { document.body.classList.remove('light-theme'); localStorage.setItem('theme', 'dark-theme'); } }
  toggleSwitch.addEventListener('change', switchTheme, false);
  function openModal(modalId) { document.getElementById(modalId).style.display = "block"; }
  function closeModal(modalId) { document.getElementById(modalId).style.display = "none"; }
  window.onclick = function(event) { if (event.target.classList.contains('modal')) { event.target.style.display = "none"; } }
  const textToType = "TANISHK MANOJ MESTRY";
  const typingElement = document.getElementById('typing-text');
  function typeEffect() { typingElement.style.width = '0'; typingElement.textContent = textToType; typingElement.style.animation = 'none'; setTimeout(() => { typingElement.style.animation = ''; }, 10); }
  typeEffect(); setInterval(typeEffect, 10000);
  const sections = document.querySelectorAll('.slide');
  const navLi = document.querySelectorAll("#page-nav ul li a");
  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const sectionId = entry.target.id;
        navLi.forEach(a => {
          a.classList.remove("active");
          if (a.dataset.section === sectionId) { a.classList.add("active"); }
        });
      }
    });
  }, { threshold: 0.7 });
  sections.forEach(section => { observer.observe(section); });
</script>
