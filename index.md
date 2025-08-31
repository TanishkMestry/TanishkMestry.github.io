---
layout: default
title: Tanishk Manoj Mestry - Portfolio
---

<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;700&display=swap');

  :root {
    --color-1: #d33a3a;
    --color-2: #8a2be2;
    --color-3: #26abe7;
    --bg-color: #101015;
    --text-color: #f0f0f0;
    --text-muted: #a0a0a0;
    --border-color: rgba(255, 255, 255, 0.1);
    --primary-gradient: linear-gradient(90deg, var(--color-1), var(--color-2), var(--color-3));
  }
  body.light-theme {
    --bg-color: #f5f5fa;
    --text-color: #1c1c1c;
    --text-muted: #555;
    --border-color: rgba(0, 0, 0, 0.1);
  }
  
  html { scroll-behavior: smooth; }
  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0; padding: 0;
    transition: background-color 0.5s;
    overflow-x: hidden;
  }

  .cursor-spotlight {
    position: fixed;
    top: 0; left: 0;
    width: 400px; height: 400px;
    background: radial-gradient(circle, var(--color-2) 0%, transparent 70%);
    border-radius: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
    z-index: -1;
    filter: blur(100px);
    opacity: 0.2;
    transition: transform 0.1s ease-out;
  }
  body.light-theme .cursor-spotlight { opacity: 0.4; }

  .main-header {
    position: fixed;
    top: 0;
    right: 0;
    padding: 1.5rem 2rem;
    z-index: 1000;
  }
  .theme-switch { display: inline-block; cursor: pointer; }
  .theme-switch input { display:none; }
  .toggle-icon-svg {
    width: 32px; height: 32px;
    transition: transform 0.4s ease, filter 0.4s ease;
  }
  body:not(.light-theme) .toggle-icon-svg {
    transform: rotate(-90deg);
    filter: grayscale(1) brightness(0.8) contrast(5) invert(1);
  }

  .content-wrapper { max-width: 1200px; margin: 0 auto; padding: 0 2rem; }
  .section { padding: 8rem 0; border-bottom: 1px solid var(--border-color); }
  .section-title { font-size: clamp(2.5rem, 5vw, 4rem); margin-bottom: 4rem; text-align: center; background: var(--primary-gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
  
  #welcome {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  #welcome h1 { font-size: clamp(2.5rem, 7vw, 5.5rem); margin: 0; line-height: 1.1; white-space: nowrap; }
  #welcome .typing-effect { border-right: 4px solid var(--text-color); animation: blink-caret .75s step-end infinite; padding-right: 2px; }
  @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--text-color); } }
  #welcome h3 { font-size: clamp(1.2rem, 3vw, 1.5rem); font-weight: 300; margin: 1.5rem 0 2.5rem 0; max-width: 600px; color: var(--text-muted); }
  #welcome .social-links a { font-size: 2rem; margin-right: 1.5rem; color: var(--text-muted); transition: color 0.3s; }
  #welcome .social-links a:hover { color: var(--color-2); }
  
  .skills-container { display: flex; flex-wrap: wrap; justify-content: center; align-items: center; gap: 2rem 3rem; }
  .skill-item { text-align: center; transition: transform 0.3s ease; }
  .skill-item:hover { transform: scale(1.1); }
  .skill-item .skill-icon { height: 60px; width: 60px; margin-bottom: 1rem; }
  .skill-item span { font-weight: bold; }

  .carousel { position: relative; padding: 2rem 0; }
  .carousel-viewport { overflow: hidden; -webkit-mask-image: linear-gradient(to right, transparent, white 10%, white 90%, transparent); mask-image: linear-gradient(to right, transparent, white 10%, white 90%, transparent); }
  .carousel-track { display: flex; }
  .carousel-slide { min-width: 50%; margin: 0 2%; box-sizing: border-box; transition: transform 0.5s, opacity 0.5s; opacity: 0.4; transform: scale(0.8); cursor: pointer; }
  .carousel-slide.is-selected { opacity: 1; transform: scale(1); }
  .carousel-button { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(128,128,128,0.2); border: 1px solid var(--border-color); color: var(--text-color); border-radius: 50%; width: 50px; height: 50px; cursor: pointer; z-index: 10; font-size: 24px; display: flex; align-items: center; justify-content: center; }
  .carousel-button:hover { background: rgba(128,128,128,0.4); }
  .carousel-button--left { left: 0; }
  .carousel-button--right { right: 0; }
  
  .project-slide { position: relative; border-radius: 16px; overflow: hidden; min-height: 450px; background-size: cover; background-position: center; color: #fff; }
  .project-slide::after { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: linear-gradient(to top, rgba(0,0,0,0.9) 0%, rgba(0,0,0,0) 60%); }
  .project-content { position: absolute; bottom: 0; left: 0; padding: 2rem; z-index: 2; }
  .project-content h3 { margin: 0 0 0.5rem 0; font-size: 1.8rem; }
  
  #certifications.section { padding: 8rem 0; width: 100%; }
  .marquee { width: 100vw; max-width: 100%; overflow: hidden; position: relative; }
  .marquee-track { display: flex; width: fit-content; animation: marquee 40s linear infinite; }
  .marquee:hover .marquee-track { animation-play-state: paused; }
  @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }
  .cert-item { flex-shrink: 0; width: 300px; padding: 2rem; text-align: center; cursor: pointer; transition: transform 0.3s ease; }
  .cert-item:hover { transform: scale(1.1); }
  .cert-item i { font-size: 60px; margin-bottom: 1rem; background: var(--primary-gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
  
  .hidden { opacity: 0; transform: translateY(30px); transition: opacity 0.8s ease-out, transform 0.8s ease-out; }
  .show { opacity: 1; transform: translateY(0); }
  .modal { display: none; position: fixed; z-index: 2000; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.8); backdrop-filter: blur(5px); }
  .modal-content { background-color: var(--bg-color); border: 1px solid var(--border-color); margin: 5% auto; padding: 2rem; width: 80%; max-width: 900px; position: relative; border-radius: 8px; }
  .modal-content img { width: 100%; }
  .close-button { color: #aaaaaa; position: absolute; top: 1rem; right: 1.5rem; font-size: 2.5rem; font-weight: bold; cursor: pointer; }
</style>

<div class="cursor-spotlight"></div>

<header class="main-header">
  <label class="theme-switch" for="checkbox">
    <input type="checkbox" id="checkbox" />
    <svg class="toggle-icon-svg" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48">
      <rect width="8.1" height="4" x="31.3" y="10.7" fill="#f5bc00" transform="rotate(-45.001 35.315 12.655)"></rect><rect width="4" height="8.1" x="22" y="3.9" fill="#f5bc00"></rect><rect width="8.1" height="4" x="36" y="22" fill="#f5bc00"></rect><rect width="4" height="8.1" x="33.3" y="31.2" fill="#f5bc00" transform="rotate(-45.001 35.315 35.283)"></rect><rect width="4" height="8.1" x="22" y="35.9" fill="#f5bc00"></rect><rect width="8.1" height="4" x="8.7" y="33.3" fill="#f5bc00" transform="rotate(-45.001 12.686 35.283)"></rect><rect width="8.1" height="4" x="4" y="22" fill="#f5bc00"></rect><rect width="4" height="8.1" x="10.7" y="8.6" fill="#f5bc00" transform="rotate(-45.001 12.686 12.655)"></rect><circle cx="24" cy="24" r="15" fill="#f5bc00"></circle><path fill="#eb7900" d="M36,26h2.9c0.1-0.6,0.1-1.3,0.1-2c0-0.7-0.1-1.4-0.2-2H36V26z"></path><path fill="#eb7900" d="M33.1,12.1l-2,2l2.8,2.8l2-2C35.1,13.8,34.1,12.9,33.1,12.1z"></path><path fill="#eb7900" d="M26,9.1C25.3,9.1,24.7,9,24,9s-1.3,0.1-2,0.1V12h4V9.1z"></path><path fill="#eb7900" d="M33.9,31L31,33.8l2.1,2.1c1.1-0.8,2-1.8,2.8-2.8L33.9,31z"></path><path fill="#eb7900" d="M22,38.9c0.7,0.1,1.3,0.1,2,0.1s1.3-0.1,2-0.1v-2.9h-4V38.9z"></path><path fill="#eb7900" d="M12.1,33.1c0.8,1.1,1.8,2,2.8,2.8l2.1-2.1L14.1,31L12.1,33.1z"></path><path fill="#eb7900" d="M9.1,26H12v-4H9.2C9.1,22.6,9,23.3,9,24C9,24.7,9.1,25.3,9.1,26z"></path><path fill="#eb7900" d="M12.1,14.9l2,2l2.8-2.8l-2-2C13.9,12.9,12.9,13.8,12.1,14.9z"></path>
    </svg>
  </label>
</header>

<main>
  <section id="welcome" class="section">
    <div class="content-wrapper">
      <h1 class="typing-effect hidden" id="typing-text"></h1>
      <h3 class="hidden">Applied Statistics and Data Analytics student with strong skills in data analysis, statistical modelling, and visualization.</h3>
      <div class="social-links hidden">
        <a href="mailto:tanishkmestry4183@gmail.com" target="_blank" title="Email"><i class='bx bx-envelope'></i></a>
        <a href="https://www.linkedin.com/in/YOUR_LINKEDIN_URL" target="_blank" title="LinkedIn"><i class='bx bxl-linkedin-square'></i></a>
        <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" title="GitHub"><i class='bx bxl-github'></i></a>
      </div>
    </div>
  </section>

  <section id="skills" class="section">
    <div class="content-wrapper">
      <h2 class="section-title hidden">Technical Skills</h2>
      <div class="skills-container hidden">
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

  <section id="projects" class="section">
    <div class="content-wrapper"><h2 class="section-title hidden">Projects</h2></div>
    <div class="carousel hidden" id="projects-carousel">
        <div class="carousel-viewport"><div class="carousel-track"></div></div>
        <button class="carousel-button carousel-button--left"><i class='bx bx-chevron-left'></i></button>
        <button class="carousel-button carousel-button--right"><i class='bx bx-chevron-right'></i></button>
    </div>
  </section>

  <section id="certifications" class="section">
    <div class="content-wrapper"><h2 class="section-title hidden">Certifications</h2></div>
    <div class="marquee hidden">
        <div class="marquee-track">
            <div class="cert-item" onclick="openModal('ibm-python-modal')"><i class='bx bxl-python'></i><span>IBM: Python for Data Science</span></div>
            <div class="cert-item" onclick="openModal('ibm-ml-modal')"><i class='bx bx-brain'></i><span>IBM: Machine Learning</span></div>
            <div class="cert-item" onclick="openModal('itvedant-sql-modal')"><i class='bx bx-data'></i><span>ITVEDANT: SQL</span></div>
            <div class="cert-item" onclick="openModal('itvedant-powerbi-modal')"><i class='bx bxs-bar-chart-alt-2'></i><span>ITVEDANT: Power BI</span></div>
            <div class="cert-item" aria-hidden="true" onclick="openModal('ibm-python-modal')"><i class='bx bxl-python'></i><span>IBM: Python for Data Science</span></div>
            <div class="cert-item" aria-hidden="true" onclick="openModal('ibm-ml-modal')"><i class='bx bx-brain'></i><span>IBM: Machine Learning</span></div>
            <div class="cert-item" aria-hidden="true" onclick="openModal('itvedant-sql-modal')"><i class='bx bx-data'></i><span>ITVEDANT: SQL</span></div>
            <div class="cert-item" aria-hidden="true" onclick="openModal('itvedant-powerbi-modal')"><i class='bx bxs-bar-chart-alt-2'></i><span>ITVEDANT: Power BI</span></div>
        </div>
    </div>
  </section>

  <section id="experience" class="section">
    <div class="content-wrapper">
        <h2 class="section-title hidden">Work Experience</h2>
        <div class="hidden">
            <h3>Bhoir & Patil Associates, Tax Consultants <span style="color: var(--text-muted);">(Apr 2024 - Mar 2025)</span></h3>
            <p><strong>Accounts Assistant:</strong> Managed and entered client financial data, including balance sheets, purchase and sales records, using Tally. Prepared and analysed financial statements and maintained detailed creditor and debtor records in Excel. Ensured tax compliance by generating accurate reports through GST software.</p>
        </div>
    </div>
  </section>

  <section id="education" class="section">
    <div class="content-wrapper">
        <h2 class="section-title hidden">Education</h2>
        <div class="hidden">
            <h3>SVKM's Mithibai College <span style="color: var(--text-muted);">(Expected: April 2026)</span></h3>
            <p>B.Sc. in Applied Statistics & Data Analytics</p>
            <h3 style="margin-top: 2rem;">ITVEDANT <span style="color: var(--text-muted);">(Jan 2025)</span></h3>
            <p>Master in Data Science & Analytics with Artificial Intelligence</p>
        </div>
    </div>
  </section>
</main>

<div id="youtube-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('youtube-modal')">&times;</span><h2>Global YouTube Statistics</h2><img src="images/placeholder.png" alt="YouTube Project Screenshot"><p>Here you can add a more detailed description of the project.</p></div></div>
<div id="sales-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('sales-modal')">&times;</span><h2>Product Sales Analysis</h2><img src="images/placeholder.png" alt="Sales Project Screenshot"></div></div>
<div id="game-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('game-modal')">&times;</span><h2>Video Game Sales Analysis</h2><img src="images/placeholder.png" alt="Game Project Screenshot"></div></div>
<div id="library-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('library-modal')">&times;</span><h2>Library Management System</h2><img src="images/placeholder.png" alt="Library Project Screenshot"></div></div>
<div id="ibm-python-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('ibm-python-modal')">&times;</span><img src="images/placeholder.png" alt="IBM Python Certificate"></div></div>
<div id="ibm-ml-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('ibm-ml-modal')">&times;</span><img src="images/placeholder.png" alt="IBM Machine Learning Certificate"></div></div>
<div id="itvedant-sql-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('itvedant-sql-modal')">&times;</span><img src="images/placeholder.png" alt="ITVEDANT SQL Certificate"></div></div>
<div id="itvedant-powerbi-modal" class="modal"><div class="modal-content"><span class="close-button" onclick="closeModal('itvedant-powerbi-modal')">&times;</span><img src="images/placeholder.png" alt="ITVEDANT Power BI Certificate"></div></div>

<script>
document.addEventListener('DOMContentLoaded', () => {
    // --- Cursor Spotlight ---
    const spotlight = document.querySelector('.cursor-spotlight');
    if (spotlight) {
        document.addEventListener('mousemove', (e) => {
            spotlight.style.transform = `translate(${e.clientX}px, ${e.clientY}px)`;
        });
    }

    // --- Theme Toggle ---
    const toggleCheckbox = document.getElementById('checkbox');
    function setTheme(isLight) {
        document.body.classList.toggle('light-theme', isLight);
        localStorage.setItem('theme', isLight ? 'light' : 'dark');
        if(toggleCheckbox) toggleCheckbox.checked = isLight;
    }
    if(toggleCheckbox) {
        toggleCheckbox.addEventListener('change', () => setTheme(toggleCheckbox.checked));
        const savedTheme = localStorage.getItem('theme');
        setTheme(savedTheme === 'light');
    }

    // --- Typing Effect ---
    const typingElement = document.getElementById('typing-text');
    const textToType = "TANISHK MANOJ MESTRY";
    let i = 0;
    function typeWriter() {
        if (!typingElement) return;
        if (i < textToType.length) {
            typingElement.innerHTML += textToType.charAt(i);
            i++;
            setTimeout(typeWriter, 120);
        }
    }
    setTimeout(typeWriter, 500);

    // --- Scroll Animations ---
    const observer = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
            if (entry.isIntersecting) {
                entry.target.classList.add('show');
            }
        });
    }, { threshold: 0.15 });
    const hiddenElements = document.querySelectorAll('.hidden');
    hiddenElements.forEach((el) => observer.observe(el));

    // --- Carousel Class ---
    class Carousel {
        constructor(carouselElement, data, slideGenerator) {
            if (!carouselElement) return;
            this.track = carouselElement.querySelector('.carousel-track');
            this.prevButton = carouselElement.querySelector('.carousel-button--left');
            this.nextButton = carouselElement.querySelector('.carousel-button--right');
            this.slides = [];
            this.data = data;
            this.slideGenerator = slideGenerator;
            this.currentIndex = 0;
            this.slideWidth = 0;
            this.init();
        }
        init() {
            const extendedData = [...this.data, ...this.data, ...this.data];
            this.track.innerHTML = extendedData.map(this.slideGenerator).join('');
            this.slides = Array.from(this.track.children);
            this.currentIndex = this.data.length;
            this.resizeObserver = new ResizeObserver(() => this.calculatePositions());
            this.resizeObserver.observe(document.body);
            this.attachEventListeners();
        }
        calculatePositions() {
            if (this.slides.length === 0) return;
            this.slideWidth = this.slides[0].getBoundingClientRect().width + (parseFloat(getComputedStyle(this.slides[0]).marginLeft) + parseFloat(getComputedStyle(this.slides[0]).marginRight));
            this.track.style.transition = 'none';
            this.track.style.transform = `translateX(-${this.currentIndex * this.slideWidth}px)`;
            setTimeout(() => { this.updateClasses(); }, 50);
        }
        moveTo(index) {
            if (this.track.clientWidth <= this.track.parentElement.clientWidth) return;
            this.track.style.transition = 'transform 0.5s ease';
            this.track.style.transform = `translateX(-${index * this.slideWidth}px)`;
            this.currentIndex = index;
            this.updateClasses();
        }
        updateClasses() {
            this.slides.forEach((slide, i) => {
                slide.classList.toggle('is-selected', i === this.currentIndex);
            });
        }
        attachEventListeners() {
            this.prevButton.addEventListener('click', () => this.moveTo(this.currentIndex - 1));
            this.nextButton.addEventListener('click', () => this.moveTo(this.currentIndex + 1));
            this.track.addEventListener('transitionend', () => {
                if (this.currentIndex < this.data.length) {
                    this.currentIndex += this.data.length;
                    this.track.style.transition = 'none';
                    this.track.style.transform = `translateX(-${this.currentIndex * this.slideWidth}px)`;
                }
                if (this.currentIndex >= this.data.length * 2) {
                    this.currentIndex -= this.data.length;
                    this.track.style.transition = 'none';
                    this.track.style.transform = `translateX(-${this.currentIndex * this.slideWidth}px)`;
                }
            });
        }
    }

    // --- Data and Initialization ---
    const projectData = [
        { id: 'youtube-modal', bg: 'images/placeholder.png', title: 'Global YouTube Statistics'},
        { id: 'sales-modal', bg: 'images/placeholder.png', title: 'Product Sales Analysis'},
        { id: 'game-modal', bg: 'images/placeholder.png', title: 'Video Game Sales Analysis'},
        { id: 'library-modal', bg: 'images/placeholder.png', title: 'Library Management System'}
    ];

    const projectsCarouselEl = document.getElementById('projects-carousel');
    const projectSlideGenerator = item => `<div class="carousel-slide project-slide" style="background-image: url('${item.bg}');" onclick="openModal('${item.id}')"><div class="project-content"><h3>${item.title}</h3></div></div>`;
    new Carousel(projectsCarouselEl, projectData, projectSlideGenerator);
});
  
function openModal(modalId) { 
  const modal = document.getElementById(modalId);
  if (modal) modal.style.display = "block";
}
function closeModal(modalId) {
  const modal = document.getElementById(modalId);
  if (modal) modal.style.display = "none";
}
window.onclick = function(event) { 
  if (event.target.classList.contains('modal')) {
    event.target.style.display = "none";
  }
}
</script>
