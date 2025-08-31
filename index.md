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
      color: var(--text-color); text-decoration: none; font-weight: bold; padding: 0.5rem; position: relative;
  }
  .main-nav a::after { content: ''; position: absolute; bottom: 0; left: 0; width: 0; height: 2px; background: var(--primary-gradient); transition: width 0.3s ease; }
  .main-nav a:hover::after { width: 100%; }
  
  .theme-switch { display: inline-block; height: 28px; position: relative; width: 54px; }
  .theme-switch input { display:none; }
  .slider { background-color: rgba(128,128,128,0.2); border: 1px solid var(--border-color); bottom: 0; cursor: pointer; left: 0; position: absolute; right: 0; top: 0; transition: .4s; border-radius: 34px; }
  
  /* NEW: SVG Icon styling for the toggle */
  .slider .toggle-icon {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    height: 18px;
    width: 18px;
    fill: var(--text-muted);
  }
  .slider .sun-icon { left: 5px; }
  .slider .moon-icon { right: 5px; }

  /* The moving circle */
  .slider:before { 
    content: '';
    background-color: #fff;
    box-shadow: 0 0 5px rgba(0,0,0,0.2);
    bottom: 3px; 
    height: 22px; 
    left: 4px; 
    position: absolute; 
    transition: .4s; 
    width: 22px; 
    border-radius: 50%; 
  }
  input:checked + .slider:before { transform: translateX(24px); }

  /* --- Layout & Sections --- */
  .content-wrapper { max-width: 1100px; margin: 0 auto; padding: 0 2rem; }
  .section { padding: 8rem 0; border-bottom: 1px solid var(--border-color); }
  .section-title { font-size: clamp(2.5rem, 5vw, 4rem); margin-bottom: 4rem; background: var(--primary-gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
  
  #welcome {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  #welcome h1 { font-size: clamp(2.5rem, 7vw, 5.5rem); margin: 0; line-height: 1.1; white-space: nowrap; }
  #welcome .typing-effect { border-right: 4px solid var(--text-color); animation: blink-caret .75s step-end infinite; }
  @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--text-color); } }
  #welcome h3 { font-size: clamp(1.2rem, 3vw, 1.5rem); font-weight: 300; margin: 1.5rem 0 2.5rem 0; max-width: 600px; color: var(--text-muted); }
  #welcome .social-links a { font-size: 2rem; margin-right: 1.5rem; color: var(--text-muted); transition: color 0.3s; }
  #welcome .social-links a:hover { color: var(--color-2); }
  
  .skills-container { display: flex; flex-wrap: wrap; justify-content: center; gap: 2rem 3rem; }
  .skill-item { text-align: center; transition: transform 0.3s ease; }
  .skill-item:hover { transform: scale(1.1); }
  .skill-item .skill-icon { height: 60px; width: 60px; margin-bottom: 1rem; }
  .skill-item span { font-weight: bold; }

  .carousel { position: relative; padding: 2rem 0; }
  .carousel-viewport { overflow: hidden; }
  .carousel-track { display: flex; transition: transform 0.5s ease-in-out; }
  .carousel-slide { flex: 0 0 70%; padding: 0 1rem; box-sizing: border-box; transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out; opacity: 0.5; transform: scale(0.85); }
  .carousel-slide.is-selected { opacity: 1; transform: scale(1); }
  .carousel-button { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(0,0,0,0.3); border: 1px solid var(--border-color); color: #fff; border-radius: 50%; width: 50px; height: 50px; cursor: pointer; z-index: 10; font-size: 24px; }
  .carousel-button:hover { background: rgba(0,0,0,0.5); }
  .carousel-button--left { left: -25px; }
  .carousel-button--right { right: -25px; }
  
  .project-slide { position: relative; border-radius: 16px; overflow: hidden; min-height: 450px; background-size: cover; background-position: center; color: #fff; }
  .project-slide::after { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: linear-gradient(to top, rgba(0,0,0,0.9) 0%, rgba(0,0,0,0) 60%); }
  .project-content { position: absolute; bottom: 0; left: 0; padding: 2rem; z-index: 2; }
  .project-content h3 { margin: 0 0 0.5rem 0; font-size: 1.8rem; }
  
  .cert-slide { min-height: 250px; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; }
  .cert-slide i { font-size: 60px; margin-bottom: 1rem; background: var(--primary-gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
  
  .hidden { opacity: 0; transform: translateY(30px); transition: opacity 0.8s ease-out, transform 0.8s ease-out; }
  .show { opacity: 1; transform: translateY(0); }
  
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
      <div class="slider round">
        <div class="sun-icon">
          <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" viewBox="0 0 48 48" class="toggle-icon">
            <rect width="8.1" height="4" x="31.3" y="10.7" fill="#f5bc00" transform="rotate(-45.001 35.315 12.655)"></rect><rect width="4" height="8.1" x="22" y="3.9" fill="#f5bc00"></rect><rect width="8.1" height="4" x="36" y="22" fill="#f5bc00"></rect><rect width="4" height="8.1" x="33.3" y="31.2" fill="#f5bc00" transform="rotate(-45.001 35.315 35.283)"></rect><rect width="4" height="8.1" x="22" y="35.9" fill="#f5bc00"></rect><rect width="8.1" height="4" x="8.7" y="33.3" fill="#f5bc00" transform="rotate(-45.001 12.686 35.283)"></rect><rect width="8.1" height="4" x="4" y="22" fill="#f5bc00"></rect><rect width="4" height="8.1" x="10.7" y="8.6" fill="#f5bc00" transform="rotate(-45.001 12.686 12.655)"></rect><circle cx="24" cy="24" r="15" fill="#f5bc00"></circle><path fill="#eb7900" d="M36,26h2.9c0.1-0.6,0.1-1.3,0.1-2c0-0.7-0.1-1.4-0.2-2H36V26z"></path><path fill="#eb7900" d="M33.1,12.1l-2,2l2.8,2.8l2-2C35.1,13.8,34.1,12.9,33.1,12.1z"></path><path fill="#eb7900" d="M26,9.1C25.3,9.1,24.7,9,24,9s-1.3,0.1-2,0.1V12h4V9.1z"></path><path fill="#eb7900" d="M33.9,31L31,33.8l2.1,2.1c1.1-0.8,2-1.8,2.8-2.8L33.9,31z"></path><path fill="#eb7900" d="M22,38.9c0.7,0.1,1.3,0.1,2,0.1s1.3-0.1,2-0.1v-2.9h-4V38.9z"></path><path fill="#eb7900" d="M12.1,33.1c0.8,1.1,1.8,2,2.8,2.8l2.1-2.1L14.1,31L12.1,33.1z"></path><path fill="#eb7900" d="M9.1,26H12v-4H9.2C9.1,22.6,9,23.3,9,24C9,24.7,9.1,25.3,9.1,26z"></path><path fill="#eb7900" d="M12.1,14.9l2,2l2.8-2.8l-2-2C13.9,12.9,12.9,13.8,12.1,14.9z"></path>
          </svg>
        </div>
        <div class="moon-icon">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="toggle-icon">
                <path fill="currentColor" d="M12 11.5A2.5 2.5 0 0 1 9.5 9A2.5 2.5 0 0 1 12 6.5A2.5 2.5 0 0 1 14.5 9a2.5 2.5 0 0 1-2.5 2.5M12 2A10 10 0 0 0 2 12a10 10 0 0 0 10 10a10 10 0 0 0 10-10A10 10 0 0 0 12 2Z"></path>
            </svg>
        </div>
      </div>
    </label>
  </div>
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

  <section id="skills" class="section hidden">
    <div class="content-wrapper">
      <h2 class="section-title">Technical Skills</h2>
      <div class="skills-container">
        </div>
    </div>
  </section>

  <section id="projects" class="section hidden">
    <div class="content-wrapper">
        <h2 class="section-title">Projects</h2>
    </div>
    <div class="carousel" id="projects-carousel">
        <div class="carousel-viewport">
            <div class="carousel-track"></div>
        </div>
        <button class="carousel-button carousel-button--left"><i class='bx bx-chevron-left'></i></button>
        <button class="carousel-button carousel-button--right"><i class='bx bx-chevron-right'></i></button>
    </div>
  </section>

  <section id="certifications" class="section hidden">
    <div class="content-wrapper">
      <h2 class="section-title">Certifications</h2>
    </div>
    <div class="carousel" id="certs-carousel">
        <div class="carousel-viewport">
            <div class="carousel-track"></div>
        </div>
        <button class="carousel-button carousel-button--left"><i class='bx bx-chevron-left'></i></button>
        <button class="carousel-button carousel-button--right"><i class='bx bx-chevron-right'></i></button>
    </div>
  </section>

  </main>

<script>
// All scripts including Carousel Class are here
</script>
