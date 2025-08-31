---
layout: default
title: Tanishk Mestry - Portfolio
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
    height: 40px
