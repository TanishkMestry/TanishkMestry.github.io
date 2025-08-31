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
  
  html, body {
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    line-height: 1.6;
    transition: background-color 0.3s, color 0.3s;
    background-image: linear-gradient(0deg, var(--grid-line-color) 1px, transparent 1px), 
                      linear-gradient(90deg, var(--grid-line-color) 1px, transparent 1px);
    background-size: 30px 30px;
    background-color: var(--bg-color);
  }

  /* Main container to hold all content */
  .wrapper {
    width: 100%;
    padding: 2rem;
    box-sizing: border-box;
  }
  
  .header {
    text-align: center;
    padding: 3rem 0;
    position: relative;
  }
  
  .typing-effect {
    font-size: 2.5rem;
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

  .header h2 { font-size: 1.2rem; color: var(--text-color); margin-top: 0.5rem; font-weight: 300; }
  .social-links a { color: var(--primary-color); text-decoration: none; margin: 0 15px; font-size: 1.5rem; transition: color 0.3s ease, text-shadow 0.3s ease; }
  .social-links a:hover { text-shadow: 0 0 10px var(--glow-color), 0 0 20px var(--glow-color); }
  
  .section {
    margin-bottom: 4rem;
    background-color: rgba(var(--card-bg-rgb), 0.5);
    border: 1px solid var(--border-color);
    border-radius: 8px;
    padding: 2rem;
    backdrop-filter: blur(5px);
  }
  :root { --card-bg-rgb: 26, 26, 46; } /* for rgba */
  body.light-theme { --card-bg-rgb: 255, 255, 255; }
  
  .section h2 {
    color: var(--primary-color);
    border-bottom: 2px solid var(--primary-color);
    padding-bottom: 10px;
    margin-top: 0;
    margin-bottom: 2rem;
    text-align: left;
  }

  /* Grids will now expand to fill the full width of the padded wrapper */
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
  .skill-item .skill-icon { font-size: 50px; color: #ffffff; filter: drop-shadow(0 0 3px var(--glow-color)) drop-shadow(0 0 8px rgba(138, 43, 226, 0.6)) drop-shadow(0 0 15px rgba(138, 43, 226, 0.4)); transition: filter 0.3s ease; }
  .skill-item:hover .skill-icon { filter: drop-shadow(0 0 5px var(--glow-color)) drop-shadow(0 0 12px rgba(138, 43, 226, 0.8)) drop-shadow(0 0 20px rgba(138, 43, 226, 0.6)); }
  .certification-item { cursor: pointer; }
  .certification-item i { font-size: 50px; color: var(--primary-color); margin-bottom: 0.5rem; }
  .project-card { background-color: var(--bg-color); border: 1px solid var(--border-color); border-radius: 8px; padding: 1.5rem; transition: transform 0.3s ease, border-color 0.3s ease; box-shadow: 0 0 5px rgba(0,0,0,0.5); cursor: pointer; }
  .project-card:hover { transform: scale(1.03); border-color: var(--primary-color); }
  .project-card h3 { margin-top: 0; color: var(--primary-color); }
  .project-card .tech-tag { background-color: var(--primary-color); color: var(--bg-color); padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.8rem; font-weight: bold; }
  details { margin-bottom: 1rem; border-left: 3px solid var(--primary-color); padding-left: 15px; }
  summary { cursor: pointer; font-weight: bold; font-size: 1.1rem; outline: none; color: var(--text-color); }
  summary:hover { color: var(--primary-color); }
  .job-title, .degree-title { font-style: italic; color: var(--text-color); opacity: 0.7; }
  .theme-switch-wrapper { position: absolute; top: 1rem; right: 1rem; z-index: 10; }
  .theme-switch { display: inline-block; height: 34px; position: relative; width: 60px; }
  .theme-switch input { display:none; }
  .slider { background-color: #555; bottom: 0; cursor: pointer; left: 0; position: absolute; right: 0; top: 0; transition: .4s; border-radius: 34px; }
  .slider:before { background-color: #fff; bottom: 4px; content: ""; height: 26px; left: 4px; position: absolute; transition: .4s; width: 26px; border-radius: 50%; }
  input:checked + .slider { background-color: var(--primary-color); }
  input:checked + .slider:before { transform: translateX(26px); }
  .modal { display: none; position: fixed; z-index: 1000; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.8); backdrop-filter: blur(5px); }
  .modal-content { background-color: var(--card-bg); margin: 5% auto; padding: 20px; border: 1px solid var(--border-color); width: 80%; max-width: 900px; position: relative; border-radius: 8px; animation: fadeIn 0.5s; }
  @keyframes fadeIn { from {opacity: 0; transform: scale(0.9);} to {opacity: 1; transform: scale(1);} }
  .modal-content img { width: 100%; border-radius: 4px; }
  .close-button { color: #aaaaaa; position: absolute; top: 10px; right: 25px; font-size: 35px; font-weight: bold; cursor: pointer; }
  .close-button:hover, .close-button:focus { color: var(--primary-color); }

</style>

<div class="wrapper">
  <header class="header">
    <div class="theme-switch-wrapper">
      <label class="theme-switch" for="checkbox">
        <input type="checkbox" id="checkbox" />
        <div class="slider round"></div>
      </label>
    </div>
    
    <h1 id="typing-text" class="typing-effect"></h1>
    <h2>Applied Statistics & Data Analytics Student</h2>
    <div class="social-links">
      <a href="mailto:tanishkmestry4183@gmail.com" target="_blank" title="Email"><i class='bx bx-envelope'></i></a>
      <a href="https://www.linkedin.com/in/YOUR_LINKEDIN_URL" target="_blank" title="LinkedIn"><i class='bx bxl-linkedin-square'></i></a>
      <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" title="GitHub"><i class='bx bxl-github'></i></a>
    </div>
  </header>

  <section id="skills" class="section">
    <h2>Technical Skills</h2>
    <div class="skills-grid">
      </div>
  </section>

  <section id="projects" class="section">
    <h2>Projects</h2>
    <div class="projects-grid">
      </div>
  </section>

  <section id="certifications" class="section">
    <h2>Certifications</h2>
    <div class="certifications-grid">
      </div>
  </section>

  <section id="experience" class="section">
    <h2>Work Experience</h2>
    </section>

  <section id="education" class="section">
    <h2>Education</h2>
    </section>
</div>
