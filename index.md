---
layout: default
title: Tanishk Manoj Mestry - Portfolio
---

<link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;700&display=swap');

  /* Global Theme Variables - Inspired by your image */
  :root {
    --primary-color: #8a2be2; /* BlueViolet */
    --glow-color: #8a2be2;
    --bg-color: #11111a; /* Dark background */
    --card-bg: #222233; /* Slightly lighter for sections/cards */
    --text-color: #e0e0e0;
    --border-color: #444455;
    --subtle-text: #aaaaaa;
    --grid-bg-color: #1a1a2e; /* Darker for the grid */
    --grid-line-color: #2a2a4a; /* Very subtle grid lines */
  }

  /* Light Theme Adaptation */
  body.light-theme {
    --primary-color: #483d8b; /* DarkSlateBlue */
    --glow-color: #483d8b;
    --bg-color: #f5f5f5;
    --card-bg: #ffffff;
    --text-color: #1c1c1c;
    --border-color: #dddddd;
    --subtle-text: #555555;
    --grid-bg-color: #eeeeee;
    --grid-line-color: #cccccc;
  }
  
  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0;
    padding: 0;
    line-height: 1.6;
    transition: background-color 0.3s, color 0.3s;
    /* Subtle grid background pattern */
    background-image: linear-gradient(0deg, var(--grid-line-color) 1px, transparent 1px), 
                      linear-gradient(90deg, var(--grid-line-color) 1px, transparent 1px);
    background-size: 30px 30px; /* Adjust grid size */
    background-color: var(--grid-bg-color); /* Base for the grid */
  }

  .content-wrapper {
      padding: 0 4rem; /* Generous side padding for content */
      margin: 0 auto; /* Keep content centered in its padded area */
  }

  /* --- Header --- */
  .header {
    text-align: center;
    padding: 4rem 0;
    position: relative;
    background-color: transparent; /* Ensure header background is grid */
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

  .header h2 {
    font-size: 1.2rem;
    color: var(--text-color);
    margin-top: 0.5rem;
    font-weight: 300;
  }

  .social-links a {
    color: var(--primary-color);
    text-decoration: none;
    margin: 0 15px;
    font-size: 1.5rem;
    transition: color 0.3s ease, text-shadow 0.3s ease;
  }
  .social-links a:hover {
    text-shadow: 0 0 10px var(--glow-color), 0 0 20px var(--glow-color);
  }

  /* --- Section Styling --- */
  .section {
    padding: 4rem 0;
    border-bottom: 1px solid var(--border-color);
    background-color: transparent; /* Ensure sections also show grid by default */
  }
  .section:nth-of-type(2n) {
      background-color: var(--card-bg); /* Use card_bg for alternating sections */
      /* Override grid for alternating sections if desired, or keep grid */
      background-image: none; /* Remove grid from these sections for contrast */
  }

  .section h2 {
    color: var(--primary-color);
    border-bottom: 2px solid var(--primary-color);
    padding-bottom: 10px;
    margin-top: 0;
    margin-bottom: 2rem;
    text-align: center;
  }

  /* --- Technical Skills Section Styling (matching image) --- */
  #skills.section {
    background-color: var(--bg-color); /* Ensure skills section has the main grid background */
    background-image: linear-gradient(0deg, var(--grid-line-color) 1px, transparent 1px), 
                      linear-gradient(90deg, var(--grid-line-color) 1px, transparent 1px);
    background-size: 30px 30px;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1.5rem;
  }
  .skill-item {
    background-color: var(--card-bg); /* Use card_bg for the skill item boxes */
    text-align: center;
    padding: 1.5rem 1rem;
    border-radius: 8px;
    font-weight: bold;
    transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 0.8rem;
    border: 1px solid var(--border-color);
    box-shadow: 0 0 5px rgba(0,0,0,0.5); /* Inner shadow for depth */
  }
  .skill-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 0 25px rgba(var(--glow-color-rgb), 0.7), 0 0 10px var(--glow-color); /* Stronger glow */
    border-color: var(--glow-color);
  }
  .skill-item .skill-icon {
    font-size: 50px;
    color: #ffffff; /* Icon base color is white */
    /* Multi-layered drop shadow for deep glow, inspired by your image */
    filter: drop-shadow(0 0 3px var(--glow-color)) /* Inner glow */
            drop-shadow(0 0 8px rgba(138, 43, 226, 0.6)) /* Outer glow */
            drop-shadow(0 0 15px rgba(138, 43, 226, 0.4)); /* Even wider subtle glow */
    transition: filter 0.3s ease;
  }
  .skill-item:hover .skill-icon {
    filter: drop-shadow(0 0 5px var(--glow-color))
            drop-shadow(0 0 12px rgba(138, 43, 226, 0.8))
            drop-shadow(0 0 20px rgba(138, 43, 226, 0.6));
  }
  /* Define RGB values for the glow color for rgba() usage */
  :root {
      --glow-color-rgb: 138, 43, 226; /* For BlueViolet */
  }
  body.light-theme {
      --glow-color-rgb: 72, 61, 139; /* For DarkSlateBlue */
  }


  /* --- Projects Grid --- */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
  }
  .project-card {
    background-color: var(--bg-color);
    border: 1px solid var(--border-color);
    border-radius: 8px;
    padding: 1.5rem;
    transition: transform 0.3s ease, border-color 0.3s ease;
    box-shadow: 0 0 5px rgba(0,0,0,0.5);
  }
  .project-card:hover { transform: scale(1.03); border-color: var(--primary-color); }
  .project-card h3 { margin-top: 0; color: var(--primary-color); }
  .project-card .tech-tag { background-color: var(--primary-color); color: var(--bg-color); padding: 0.2rem 0.6rem; border-radius: 4px; font-size: 0.8rem; font-weight: bold; }
  
  /* --- Experience & Education --- */
  details { margin-bottom: 1rem; border-left: 3px solid var(--primary-color); padding-left: 15px; }
  summary { cursor: pointer; font-weight: bold; font-size: 1.1rem; outline: none; color: var(--text-color); }
  summary:hover { color: var(--primary-color); }
  .job-title, .degree-title { font-style: italic; color: var(--subtle-text); }
  
  /* --- Footer --- */
  .footer { text-align: center; padding: 2rem 0; color: #888; background-color: var(--card-bg); }
  
  /* --- Theme Toggle Styling --- */
  .theme-switch-wrapper {
    position: absolute;
    top: 1rem;
    right: 2rem;
    z-index: 10; /* Ensure toggle is always on top */
  }
  .theme-switch { display: inline-block; height: 34px; position: relative; width: 60px; }
  .theme-switch input { display:none; }
  .slider { background-color: #555; bottom: 0; cursor: pointer; left: 0; position: absolute; right: 0; top: 0; transition: .4s; border-radius: 34px; }
  .slider:before { background-color: #fff; bottom: 4px; content: ""; height: 26px; left: 4px; position: absolute; transition: .4s; width: 26px; border-radius: 50%; }
  input:checked + .slider { background-color: var(--primary-color); } /* Light theme toggle color */
  input:checked + .slider:before { transform: translateX(26px); }

  /* Responsive adjustments */
  @media (max-width: 768px) {
      .content-wrapper {
          padding: 0 1rem;
      }
      .header {
          padding: 3rem 0;
      }
      .section {
          padding: 3rem 0;
      }
      .typing-effect {
          font-size: 1.8rem;
      }
      .theme-switch-wrapper {
          right: 1rem;
      }
  }

</style>

<header class="header">
  <div class="content-wrapper">
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
  </div>
</header>

<section id="skills" class="section">
  <div class="content-wrapper">
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
  </div>
</section>

<section id="projects" class="section">
  <div class="content-wrapper">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card">
        <span class="tech-tag">Power BI</span><h3>Global YouTube Statistics</h3>
        <p>Developed an interactive dashboard to evaluate channel performance, video views, and earnings, delivering actionable insights for content strategy.</p>
      </div>
      <div class="project-card">
        <span class="tech-tag">Excel</span><h3>Product Sales Analysis</h3>
        <p>Designed an interactive dashboard to analyse product sales trends using advanced data cleaning and visualization techniques for performance tracking.</p>
      </div>
      <div class="project-card">
        <span class="tech-tag">Tableau</span><h3>Video Game Sales Analysis</h3>
        <p>Built a dynamic dashboard to analyze regional video game sales, identifying key trends and providing data-driven performance insights.</p>
      </div>
      <div class="project-card">
        <span class="tech-tag">SQL</span><h3>Library Management System</h3>
        <p>Created a comprehensive system for managing book inventory, tracking member activities, and generating detailed analytical reports.</p>
      </div>
    </div>
  </div>
</section>

<section id="experience" class="section">
  <div class="content-wrapper">
    <h2>Work Experience</h2>
    <details>
      <summary>Bhoir & Patil Associates, Tax Consultants (Apr 2024 - Mar 2025)</summary>
      <p class="job-title">Accounts Assistant</p>
      <ul>
        <li>Managed and entered client financial data, including balance sheets, purchase and sales records, using Tally.</li>
        <li>Prepared and analysed financial statements and maintained detailed creditor and debtor records in Excel.</li>
        <li>Ensured tax compliance by generating accurate reports through GST software.</li>
      </ul>
    </details>
  </div>
</section>

<section id="education" class="section">
  <div class="content-wrapper">
    <h2>Education</h2>
    <details>
      <summary>SVKM's Mithibai College (Expected: April 2026)</summary>
      <p class="degree-title">B.Sc. in Applied Statistics & Data Analytics</p>
    </details>
    <details>
      <summary>ITVEDANT (Jan 2025)</summary>
      <p class="degree-title">Master in Data Science & Analytics with Artificial Intelligence</p>
    </details>
  </div>
</section>
  
<footer class="footer">
  <p>&copy; 2025 Tanishk Manoj Mestry. Built with passion and code.</p>
</footer>

<script>
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

  // Theme Toggle Script
  const toggleSwitch = document.querySelector('.theme-switch input[type="checkbox"]');
  const currentTheme = localStorage.getItem('theme');
  if (currentTheme) {
    document.body.classList.add(currentTheme);
    if (currentTheme === 'light-theme') {
      toggleSwitch.checked = true;
    }
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
</script>
