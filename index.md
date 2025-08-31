---
layout: default
title: Tanishk Manoj Mestry - Portfolio
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;700&display=swap');

  :root {
    --bg-color: #0a0a0a;
    --primary-color: #00ffff; /* Cyan / Aqua */
    --text-color: #e0e0e0;
    --card-bg: #1a1a1a;
    --border-color: #333;
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Roboto Mono', monospace;
    margin: 0;
    padding: 0; /* Removed padding from body */
    line-height: 1.6;
  }

  /* --- MODIFIED: This container is now full-width --- */
  .container {
    width: 100%;
    padding: 2rem 4rem; /* Added more horizontal padding */
    box-sizing: border-box; /* Ensures padding is included in the width */
  }

  /* --- Header & Typing Animation --- */
  .header {
    text-align: center;
    margin-bottom: 4rem;
    padding-top: 2rem; /* Added padding to give space at the top */
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

  @keyframes typing {
    from { width: 0 }
    to { width: 100% }
  }

  @keyframes blink-caret {
    from, to { border-color: transparent }
    50% { border-color: var(--primary-color); }
  }

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
    color: #fff;
    text-shadow: 0 0 10px var(--primary-color);
  }
  
  /* --- Section Styling --- */
  .section {
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 8px;
    padding: 2rem;
    margin-bottom: 2rem;
    box-shadow: 0 0 15px rgba(0, 255, 255, 0.1);
  }

  .section h2 {
    color: var(--primary-color);
    border-bottom: 2px solid var(--primary-color);
    padding-bottom: 10px;
    margin-top: 0;
  }

  /* --- Skills Grid --- */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem;
  }

  .skill-item {
    background-color: #252525;
    text-align: center;
    padding: 1rem;
    border-radius: 5px;
    font-weight: bold;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 0.8rem;
  }
  
  .skill-item .skill-icon {
    width: 40px;
    height: 40px;
    fill: var(--primary-color); /* Style the icon color */
  }

  .skill-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 0 10px var(--primary-color);
  }

  /* --- Projects Grid --- */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
  }

  .project-card {
    background-color: #252525;
    border: 1px solid var(--border-color);
    border-radius: 8px;
    padding: 1.5rem;
    transition: transform 0.3s ease, border-color 0.3s ease;
  }
  
  .project-card:hover {
      transform: scale(1.03);
      border-color: var(--primary-color);
  }

  .project-card h3 {
    margin-top: 0;
    color: var(--primary-color);
  }
  
  .project-card .tech-tag {
      background-color: var(--primary-color);
      color: var(--bg-color);
      padding: 0.2rem 0.6rem;
      border-radius: 4px;
      font-size: 0.8rem;
      font-weight: bold;
  }

  /* --- Experience & Education --- */
  details {
    margin-bottom: 1rem;
    border-left: 3px solid var(--border-color);
    padding-left: 15px;
  }

  summary {
    cursor: pointer;
    font-weight: bold;
    font-size: 1.1rem;
    outline: none;
  }
  
  summary:hover {
      color: var(--primary-color);
  }

  .job-title, .degree-title {
      font-style: italic;
      color: #aaa;
  }

  /* --- Footer --- */
  .footer {
    text-align: center;
    padding: 2rem 0;
    color: #888;
  }

</style>

<div class="container">

  <header class="header">
    <h1 id="typing-text" class="typing-effect"></h1>
    <h2>Applied Statistics & Data Analytics Student</h2>
    <div class="social-links">
      <a href="mailto:tanishkmestry4183@gmail.com" target="_blank" title="Email">📧</a>
      <a href="https://www.linkedin.com/in/YOUR_LINKEDIN_URL" target="_blank" title="LinkedIn">🔗</a>
      <a href="https://github.com/YOUR_GITHUB_USERNAME" target="_blank" title="GitHub">💻</a>
    </div>
  </header>

  <section id="skills" class="section">
    <h2>Technical Skills</h2>
    <div class="skills-grid">
      <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 128 128"><path d="M62.3 14.3c-1.2-1-2.9-1-4.1 0l-16.8 14.2c-.6.5-1 1.2-1 2v21.1c0 .8-.3 1.5-.9 2L23 68c-.6.5-1 1.2-1 2v21.5c0 .8-.3 1.5-.9 2l-16.8 14.2c-1.2 1-1.2 2.7 0 3.7l16.8 14.2c.6.5 1 1.2 1 2v21.1c0 .8.3 1.5.9 2l16.4 14.3c1.2 1 2.9 1 4.1 0l16.8-14.2c.6-.5 1-1.2 1-2v-21.1c0-.8.3-1.5.9-2l16.4-14.3c.6-.5 1-1.2 1-2V70.1c0-.8.3-1.5.9-2l16.8-14.2c1.2-1 1.2-2.7 0-3.7l-16.8-14.2c-.6-.5-1-1.2-1-2V16.7c0-.8-.3-1.5-.9-2L62.3 14.3zM49 39.8c.2 0 .4.1.6.2l12.3 7.1c.3.2.6.2.9 0l12.3-7.1c.5-.3.9-.1.9.5v14.2c0 .4-.2.7-.5.9l-12.2 7.1c-.3.2-.6.2-.9 0l-12.2-7.1c-.3-.2-.5-.5-.5-.9V40.3c0-.6.4-.5.8-.5zm-13.4 22c.2 0 .4.1.6.2l12.3 7.1c.3.2.6.2.9 0l12.3-7.1c.5-.3.9-.1.9.5v14.2c0 .4-.2.7-.5.9L50.1 85c-.3.2-.6.2-.9 0l-12.2-7.1c-.3-.2-.5-.5-.5-.9V62.8c.1-.6.5-.5.9-.5z"></path></svg>
        <span>Python</span>
      </div>
      <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 24 24"><path d="M12.63,21.5a8.23,8.23,0,0,1-5.3-1.81,1,1,0,0,1,1.34-1.48,6.17,6.17,0,0,0,8-8,6.21,6.21,0,0,0-8.06,0,1,1,0,1,1-1.42-1.42,8.21,8.21,0,0,1,11.62,0,8.1,8.1,0,0,1,1.81,5.3,8.08,8.08,0,0,1-1.81,5.3A8.23,8.23,0,0,1,12.63,21.5Z"/><path d="M12.63,12.5a8.23,8.23,0,0,1-5.3-1.81,1,1,0,0,1,1.34-1.48,6.17,6.17,0,0,0,8-8,6.21,6.21,0,0,0-8.06,0,1,1,0,1,1-1.42-1.42,8.21,8.21,0,0,1,11.62,0,8.1,8.1,0,0,1,1.81,5.3,8.08,8.08,0,0,1-1.81,5.3A8.23,8.23,0,0,1,12.63,12.5Z"/></svg>
        <span>SQL</span>
      </div>
      <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 24 24"><path d="M18.7,3.8H5.3a1.5,1.5,0,0,0-1.5,1.5V18.7a1.5,1.5,0,0,0,1.5,1.5H18.7a1.5,1.5,0,0,0,1.5-1.5V5.3A1.5,1.5,0,0,0,18.7,3.8ZM9,18H7.1V10.7H9Zm-1-8.5a1.1,1.1,0,1,1,1-1.1A1.1,1.1,0,0,1,8,9.5Zm10,8.5H16.1V13.4c0-1.1,0-2.5-1.5-2.5s-1.8,1.2-1.8,2.4V18H10.9V10.7h1.9v.9h0a2.1,2.1,0,0,1,1.9-1c2,0,2.4,1.3,2.4,3.1Z"/></svg>
        <span>Power BI</span>
      </div>
      <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 24 24"><path d="M12 2C6.5 2 2 6.5 2 12s4.5 10 10 10 10-4.5 10-10S17.5 2 12 2zM5.1 11.3h2.8v9.4H5.1zm1.4-5.6c-.9 0-1.7.7-1.7 1.7s.8 1.7 1.7 1.7 1.7-.8 1.7-1.7-.8-1.7-1.7-1.7zm13 15h-2.8V13c0-.8-.3-1.4-.9-1.4s-.8.6-.9 1.4v6.1h-2.8v-9.4h2.8v1.3c.4-.7 1.4-1.4 2.5-1.4 1.8 0 3.1 1.2 3.1 3.7v5.8z"/></svg>
        <span>Tableau</span>
      </div>
      <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10" stroke-width="2" stroke="currentColor" fill="none"/><path d="M9.5,7.5 L14.5,12 L9.5,16.5"/></svg>
        <span>R</span>
      </div>
      <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 24 24"><path d="M21 3H3C2.4 3 2 3.4 2 4v16c0 .6.4 1 1 1h18c.6 0 1-.4 1-1V4c0-.6-.4-1-1-1zM8 19H4V5h4v14zm6 0h-4V5h4v14zm6 0h-4V5h4v14z"/></svg>
        <span>Advanced Excel</span>
      </div>
      <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 24 24"><path d="M9.4 16.6L4.8 12l4.6-4.6L8 6l-6 6 6 6 1.4-1.4zm5.2 0l4.6-4.6-4.6-4.6L16 6l6 6-6 6-1.4-1.4z"/></svg>
        <span>MATLAB</span>
      </div>
       <div class="skill-item">
        <svg class="skill-icon" viewBox="0 0 24 24"><path d="M12 2C6.5 2 2 6.5 2 12s4.5 10 10 10 10-4.5 10-10S17.5 2 12 2zm-1 16.9c-2.7 0-4.9-2.2-4.9-4.9S8.3 9.1 11 9.1v2.8c0 .3.2.5.5.5s.5-.2.5-.5V8.1c-2.2 0-4 1.8-4 4s1.8 4 4 4v-2.8c0-.3-.2-.5-.5-.5s-.5.2-.5.5v3.1zm2-1.9v2.8c2.7 0 4.9-2.2 4.9-4.9s-2.2-4.9-4.9-4.9v2.8c0 .3.2.5.5.5s.5-.2.5-.5V8.1c2.2 0 4 1.8 4 4s-1.8 4-4 4z"/></svg>
        <span>Machine Learning</span>
      </div>
    </div>
  </section>

  <section id="projects" class="section">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card">
        <span class="tech-tag">Power BI</span>
        <h3>Global YouTube Statistics</h3>
        <p>Developed an interactive dashboard to evaluate channel performance, video views, and earnings, delivering actionable insights for content strategy.</p>
      </div>
      <div class="project-card">
        <span class="tech-tag">Excel</span>
        <h3>Product Sales Analysis</h3>
        <p>Designed an interactive dashboard to analyse product sales trends using advanced data cleaning and visualization techniques for performance tracking.</p>
      </div>
      <div class="project-card">
        <span class="tech-tag">Tableau</span>
        <h3>Video Game Sales Analysis</h3>
        <p>Built a dynamic dashboard to analyze regional video game sales, identifying key trends and providing data-driven performance insights.</p>
      </div>
      <div class="project-card">
        <span class="tech-tag">SQL</span>
        <h3>Library Management System</h3>
        <p>Created a comprehensive system for managing book inventory, tracking member activities, and generating detailed analytical reports.</p>
      </div>
    </div>
  </section>

  <section id="experience" class="section">
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
  </section>

  <section id="education" class="section">
    <h2>Education</h2>
    <details>
      <summary>SVKM's Mithibai College (Expected: April 2026)</summary>
      <p class="degree-title">B.Sc. in Applied Statistics & Data Analytics</p>
    </details>
    <details>
      <summary>ITVEDANT (Jan 2025)</summary>
      <p class="degree-title">Master in Data Science & Analytics with Artificial Intelligence</p>
    </details>
  </section>
  
  <footer class="footer">
    <p>&copy; 2025 Tanishk Manoj Mestry. Built with passion and code.</p>
  </footer>

</div>

<script>
  const textToType = "TANISHK MANOJ MESTRY";
  const typingElement = document.getElementById('typing-text');
  
  // This function simulates the typing effect.
  function typeEffect() {
    typingElement.style.width = '0'; // Reset width
    typingElement.textContent = textToType;
    typingElement.style.animation = 'none'; // Reset animation
    // A small delay to restart the animation properly
    setTimeout(() => {
      typingElement.style.animation = '';
    }, 10);
  }
  
  // Initial call
  typeEffect();
  
  // Optional: Re-trigger the animation every 10 seconds
  setInterval(typeEffect, 10000);
</script>
