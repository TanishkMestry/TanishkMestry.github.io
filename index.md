<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tanishk Mestry - Portfolio</title>
    <style>
        body { margin: 0; overflow: hidden; font-family: 'Inter', sans-serif; background-color: #f0f0f0; color: #333; }
        #loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            flex-direction: column;
        }
        .sk-cube-grid {
            width: 40px;
            height: 40px;
            margin: 100px auto;
        }

        .sk-cube-grid .sk-cube {
            width: 33%;
            height: 33%;
            background-color: #333;
            float: left;
            -webkit-animation: sk-cubeGridScaleDelay 1.3s infinite ease-in-out;
                    animation: sk-cubeGridScaleDelay 1.3s infinite ease-in-out; 
        }
        .sk-cube-grid .sk-cube1 { -webkit-animation-delay: 0.2s; animation-delay: 0.2s; }
        .sk-cube-grid .sk-cube2 { -webkit-animation-delay: 0.3s; animation-delay: 0.3s; }
        .sk-cube-grid .sk-cube3 { -webkit-animation-delay: 0.4s; animation-delay: 0.4s; }
        .sk-cube-grid .sk-cube4 { -webkit-animation-delay: 0.1s; animation-delay: 0.1s; }
        .sk-cube-grid .sk-cube5 { -webkit-animation-delay: 0.2s; animation-delay: 0.2s; }
        .sk-cube-grid .sk-cube6 { -webkit-animation-delay: 0.3s; animation-delay: 0.3s; }
        .sk-cube-grid .sk-cube7 { -webkit-animation-delay: 0s; animation-delay: 0s; }
        .sk-cube-grid .sk-cube8 { -webkit-animation-delay: 0.1s; animation-delay: 0.1s; }
        .sk-cube-grid .sk-cube9 { -webkit-animation-delay: 0.2s; animation-delay: 0.2s; }

        @-webkit-keyframes sk-cubeGridScaleDelay {
            0%, 70%, 100% { -webkit-transform: scale3D(1, 1, 1); transform: scale3D(1, 1, 1); }
            35% { -webkit-transform: scale3D(0, 0, 1); transform: scale3D(0, 0, 1); }
        }

        @keyframes sk-cubeGridScaleDelay {
            0%, 70%, 100% { -webkit-transform: scale3D(1, 1, 1); transform: scale3D(1, 1, 1); }
            35% { -webkit-transform: scale3D(0, 0, 1); transform: scale3D(0, 0, 1); }
        }
        #content-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: none;
            justify-content: center;
            align-items: center;
            background: rgba(0, 0, 0, 0.5);
            z-index: 100;
        }
        .content-box {
            background: white;
            padding: 2em;
            border-radius: 10px;
            width: 90%;
            max-width: 800px;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
            display: flex;
            flex-direction: column;
        }
        .content-box h2 { margin-top: 0; }
        .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5em;
            cursor: pointer;
        }
        .project-details { display: none; }
        
        /* Gemini Features Styling */
        .gemini-btn {
            background-color: #4a4af5;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 15px;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        .gemini-btn:disabled {
            background-color: #ccc;
            cursor: not-allowed;
        }
        .gemini-btn:hover:not(:disabled) { background-color: #3a3ad5; }
        .gemini-response {
            margin-top: 15px;
            padding: 15px;
            background-color: #f5f5f5;
            border-radius: 5px;
            border: 1px solid #ddd;
            white-space: pre-wrap;
            font-family: monospace;
        }

        #chat-window {
            height: 40vh;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 10px;
            overflow-y: auto;
            margin-bottom: 10px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .chat-message {
            padding: 8px 12px;
            border-radius: 15px;
            max-width: 70%;
        }
        .user-message {
            background-color: #4a4af5;
            color: white;
            align-self: flex-end;
            border-bottom-right-radius: 0;
        }
        .bot-message {
            background-color: #e9e9eb;
            color: #333;
            align-self: flex-start;
            border-bottom-left-radius: 0;
        }
        #chat-input-container { display: flex; }
        #chat-input {
            flex-grow: 1;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 5px 0 0 5px;
        }
        #chat-send {
            padding: 10px 15px;
            border: none;
            background-color: #4a4af5;
            color: white;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
        }
        .spinner {
            display: inline-block;
            width: 1em;
            height: 1em;
            border: 2px solid #fff;
            border-radius: 50%;
            border-top-color: transparent;
            animation: spin 1s linear infinite;
        }
        @keyframes spin { to { transform: rotate(360deg); } }

    </style>
</head>
<body>
    <div id="loader">
        <div class="sk-cube-grid">
            <div class="sk-cube sk-cube1"></div><div class="sk-cube sk-cube2"></div><div class="sk-cube sk-cube3"></div>
            <div class="sk-cube sk-cube4"></div><div class="sk-cube sk-cube5"></div><div class="sk-cube sk-cube6"></div>
            <div class="sk-cube sk-cube7"></div><div class="sk-cube sk-cube8"></div><div class="sk-cube sk-cube9"></div>
        </div>
        <p>Loading Portfolio...</p>
    </div>

    <div id="content-container">
        <div class="content-box">
            <button class="close-btn">&times;</button>
            <div id="resume-content" class="project-details">
                <h2>Resume</h2>
                <h3>TANISHK MANOJ MESTRY</h3>
                <p>+91 7047991555 | tanishkmestry4183@gmail.com | <a href="#" target="_blank">LinkedIn</a> | <a href="#" target="_blank">GitHub</a></p>
                <h4>SUMMARY</h4>
                <p>Applied Statistics and Data Analytics student with strong skills in data analysis, statistical modelling, and visualization. Proficient in Advanced Excel, SQL, Python, R, MATLAB, Tableau, and Power BI for data cleaning, reporting, and Interactive Dashboards. Completed multiple certifications in Data Science, ML & Al, with hands-on projects in forecasting, business analytics, and visualization. Gained professional exposure as an Accounts Assistant, applying analytical and reporting skills to financial data. Detail-oriented and analytical, eager to apply data-driven insights in academic, research, and business environments.</p>
                <h4>WORK EXPERIENCE</h4>
                <p><strong>BHOIR & PATIL ASSOCIATES, TAX CONSULTANTS</strong><br>Accounts Assistant, Apr 2024-Mar 2025</p>
                <ul>
                    <li>Managed and entered client financial data, including balance sheets, purchase and sales records, using Tally.</li>
                    <li>Prepared and analysed financial statements and maintained detailed creditor and debtor records in Excel.</li>
                    <li>Ensured tax compliance by generating accurate reports through GST software.</li>
                </ul>
                <h4>EDUCATION</h4>
                <p><strong>ITVEDANT</strong><br>Master in Data Science & Analytics with Artificial Intelligence: 70.01% (January 2025)</p>
                <p><strong>SVKM's MITHIBAI COLLEGE</strong><br>Pursuing B.Sc. in Applied Statistics & Data Analytics (Expected: April 2026)</p>
                <p>Higher Secondary Certificate (HSC): 77.9%</p>
                <p><strong>ANAND ASHRAM CONVENT ENGLISH HIGH SCHOOL</strong><br>Secondary School Certificate (SSC): 77.4%</p>
            </div>
            <div id="project1-content" class="project-details">
                <h2>Product Sales Analysis (Excel)</h2>
                <p>Designed an interactive dashboard to analyse product sales trends using advanced data cleaning and visualization techniques for performance tracking.</p>
                <div style="width:100%; height: 300px; background: #eee; border-radius: 8px; display:flex; align-items:center; justify-content:center;">Image Placeholder</div>
                <button class="gemini-btn" data-project-id="project1">✨ Suggest Next Steps</button>
                <div class="gemini-response" id="response-project1"></div>
            </div>
             <div id="project2-content" class="project-details">
                <h2>Global YouTube Statistics (Power BI)</h2>
                <p>Developed an interactive dashboard to evaluate channel performance, video views, and earnings, delivering actionable insights for content strategy.</p>
                 <div style="width:100%; height: 300px; background: #eee; border-radius: 8px; display:flex; align-items:center; justify-content:center;">Image Placeholder</div>
                <button class="gemini-btn" data-project-id="project2">✨ Suggest Next Steps</button>
                <div class="gemini-response" id="response-project2"></div>
            </div>
            <div id="project3-content" class="project-details">
                <h2>Video Game Sales Analysis (Tableau)</h2>
                <p>Built a dynamic dashboard to analyze regional video game sales, identifying key trends and providing data-driven performance insights.</p>
                <div style="width:100%; height: 300px; background: #eee; border-radius: 8px; display:flex; align-items:center; justify-content:center;">Image Placeholder</div>
                <button class="gemini-btn" data-project-id="project3">✨ Suggest Next Steps</button>
                <div class="gemini-response" id="response-project3"></div>
            </div>
             <div id="chatbot-content" class="project-details">
                <h2>AI Career Assistant</h2>
                <p>Ask me about Tanishk's skills, projects, or experience!</p>
                <div id="chat-window"></div>
                <div id="chat-input-container">
                    <input type="text" id="chat-input" placeholder="Ask a question...">
                    <button id="chat-send">Send</button>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>

    <script>
        // --- Basic Three.js Setup ---
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.setClearColor(0xf0f0f0);
        document.body.appendChild(renderer.domElement);

        // --- Lighting ---
        const ambientLight = new THREE.AmbientLight(0xffffff, 0.6);
        scene.add(ambientLight);
        const directionalLight = new THREE.DirectionalLight(0xffffff, 0.8);
        directionalLight.position.set(5, 10, 7.5);
        scene.add(directionalLight);

        camera.position.z = 150;
        camera.position.y = 20;
        camera.lookAt(0, 0, 0);

        // --- Desk and Objects ---
        const objects = [];
        const interactiveObjects = [];

        // Desk
        const deskGeometry = new THREE.BoxGeometry(200, 2, 100);
        const deskMaterial = new THREE.MeshStandardMaterial({ color: 0x8B4513 });
        const desk = new THREE.Mesh(deskGeometry, deskMaterial);
        desk.position.y = -1;
        scene.add(desk);

        // --- Gemini API Setup ---
        const apiKey = ""; 
        const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-05-20:generateContent?key=${apiKey}`;

        async function callGeminiAPI(prompt, systemPrompt = null, retries = 3, delay = 1000) {
            const payload = {
                contents: [{ parts: [{ text: prompt }] }],
            };

            if (systemPrompt) {
                payload.systemInstruction = { parts: [{ text: systemPrompt }] };
            }

            try {
                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                    if (response.status === 429 && retries > 0) {
                        await new Promise(resolve => setTimeout(resolve, delay));
                        return callGeminiAPI(prompt, systemPrompt, retries - 1, delay * 2);
                    }
                    throw new Error(`API call failed with status: ${response.status}`);
                }

                const result = await response.json();
                return result.candidates?.[0]?.content?.parts?.[0]?.text || "Sorry, I couldn't generate a response.";
            } catch (error) {
                console.error("Gemini API call failed:", error);
                if (retries > 0) {
                    await new Promise(resolve => setTimeout(resolve, delay));
                    return callGeminiAPI(prompt, systemPrompt, retries - 1, delay * 2);
                }
                return "An error occurred while trying to connect to the AI assistant.";
            }
        }


        // --- Create interactive items on the desk ---
        function createInteractiveItem(name, config) {
            const geometry = new THREE.BoxGeometry(config.width, config.height, config.depth);
            const material = new THREE.MeshStandardMaterial({ 
                color: config.color,
                map: createTexture(config.label),
             });
            const item = new THREE.Mesh(geometry, material);
            item.position.set(config.x, config.height / 2, config.z);
            item.rotation.y = config.rotation || 0;
            item.name = name;
            item.userData = { 
                originalPosition: item.position.clone(),
                originalRotation: item.rotation.clone(),
                bringToFront: bringToFront,
                bringBack: bringBack,
                contentId: config.contentId
            };
            scene.add(item);
            objects.push(item);
            interactiveObjects.push(item);
            return item;
        }
        
        function createTexture(text) {
            const canvas = document.createElement('canvas');
            canvas.width = 256;
            canvas.height = 128;
            const context = canvas.getContext('2d');
            context.fillStyle = '#fff';
            context.fillRect(0, 0, 256, 128);
            context.font = '20px Arial';
            context.fillStyle = '#000';
            context.textAlign = 'center';
            context.fillText(text, 128, 70);
            const texture = new THREE.CanvasTexture(canvas);
            texture.needsUpdate = true;
            return texture;
        }

        // Resume
        createInteractiveItem("resume", { width: 21, height: 1, depth: 29.7, x: -50, z: 10, color: 0xffffff, label: 'Resume', contentId: 'resume-content' });
        // Projects
        createInteractiveItem("project1", { width: 30, height: 1, depth: 20, x: 0, z: -20, color: 0xeeeeee, label: 'Sales Analysis', contentId: 'project1-content' });
        createInteractiveItem("project2", { width: 30, height: 1, depth: 20, x: 40, z: -15, color: 0xdddddd, label: 'YouTube Stats', contentId: 'project2-content' });
        createInteractiveItem("project3", { width: 30, height: 1, depth: 20, x: -30, z: -25, color: 0xcccccc, label: 'Game Sales', contentId: 'project3-content' });

        // AI Assistant Sphere
        const assistantGeometry = new THREE.SphereGeometry(8, 32, 32);
        const assistantMaterial = new THREE.MeshStandardMaterial({
            color: 0x2d2dff, metalness: 0.8, roughness: 0.2, emissive: 0x1a1a8d
        });
        const assistantSphere = new THREE.Mesh(assistantGeometry, assistantMaterial);
        assistantSphere.position.set(60, 8, 20);
        assistantSphere.name = "ai_assistant";
        assistantSphere.userData = { 
            originalPosition: assistantSphere.position.clone(),
            originalRotation: assistantSphere.rotation.clone(),
            bringToFront: bringToFront,
            bringBack: bringBack,
            contentId: 'chatbot-content'
        };
        scene.add(assistantSphere);
        objects.push(assistantSphere);
        interactiveObjects.push(assistantSphere);


        // --- Interaction Logic ---
        const raycaster = new THREE.Raycaster();
        const mouse = new THREE.Vector2();
        let hoveredObject = null;
        let selectedObject = null;

        function onMouseMove(event) {
            mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
            mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
            if (!selectedObject) {
                gsap.to(camera.position, { x: -mouse.x * 5, y: 20 + mouse.y * 5, duration: 0.5, ease: "power1.out" });
                camera.lookAt(0, 0, 0);
            }
        }
        
        function onMouseClick(event) {
            if (hoveredObject && !selectedObject) {
                selectedObject = hoveredObject;
                selectedObject.userData.bringToFront();
            }
        }

        function bringToFront() {
            if (selectedObject) return;
            selectedObject = this;
            
            const targetPosition = new THREE.Vector3();
            camera.getWorldDirection(targetPosition);
            targetPosition.multiplyScalar(80).add(camera.position);

            const isAISphere = this.name === "ai_assistant";

            gsap.to(this.position, {
                x: camera.position.x,
                y: isAISphere ? camera.position.y : camera.position.y,
                z: camera.position.z - (isAISphere ? 30 : 50),
                duration: 1,
                ease: 'power3.inOut'
            });
            gsap.to(this.rotation, {
                x: 0, y: 0, z: 0, duration: 1, ease: 'power3.inOut',
                onComplete: () => showContent(this.userData.contentId)
            });
             gsap.to(camera.position, { x: 0, y: 20, z: 150, duration: 1, ease: 'power3.inOut' });
        }

        function bringBack() {
            if (!this) return;
            hideContent();
            gsap.to(this.position, {
                x: this.userData.originalPosition.x, y: this.userData.originalPosition.y, z: this.userData.originalPosition.z,
                duration: 1, ease: 'power3.inOut'
            });
            gsap.to(this.rotation, {
                x: this.userData.originalRotation.x, y: this.userData.originalRotation.y, z: this.userData.originalRotation.z,
                duration: 1, ease: 'power3.inOut', onComplete: () => { selectedObject = null; }
            });
        }

        // --- Content Display & Gemini Logic ---
        const contentContainer = document.getElementById('content-container');
        const allDetails = document.querySelectorAll('.project-details');
        const closeBtn = document.querySelector('.close-btn');

        function showContent(id) {
            allDetails.forEach(detail => detail.style.display = 'none');
            const activeContent = document.getElementById(id);
            if (activeContent) {
                activeContent.style.display = 'flex';
                contentContainer.style.display = 'flex';
            }
        }

        function hideContent() {
            contentContainer.style.display = 'none';
        }

        closeBtn.addEventListener('click', () => {
            if (selectedObject) {
                selectedObject.userData.bringBack.call(selectedObject);
            }
        });
        
        // Project idea generator
        document.querySelectorAll('.gemini-btn').forEach(button => {
            button.addEventListener('click', async () => {
                const projectId = button.dataset.projectId;
                const responseDiv = document.getElementById(`response-${projectId}`);
                const projectContent = document.getElementById(`${projectId}-content`);
                const projectTitle = projectContent.querySelector('h2').innerText;
                const projectDesc = projectContent.querySelector('p').innerText;

                button.disabled = true;
                button.innerHTML = '<span class="spinner"></span> Generating...';
                
                const prompt = `Based on the following data analytics project, suggest three innovative and impressive next steps or related project ideas. The goal is to showcase forward-thinking and an ambition to use more advanced technologies. Keep the suggestions concise and in a bulleted list. Project Title: ${projectTitle}. Description: ${projectDesc}`;
                
                const response = await callGeminiAPI(prompt);
                responseDiv.innerHTML = response.replace(/\*/g, '•');
                
                button.disabled = false;
                button.innerHTML = '✨ Suggest Next Steps';
            });
        });
        
        // Chatbot logic
        const chatWindow = document.getElementById('chat-window');
        const chatInput = document.getElementById('chat-input');
        const chatSend = document.getElementById('chat-send');
        const resumeText = document.getElementById('resume-content').innerText;
        const chatSystemPrompt = `You are a friendly and professional AI career assistant representing Tanishk Mestry. Your goal is to answer questions from potential recruiters or employers based on Tanishk's resume. Be concise, helpful, and always positive. Here is the resume information to use as your knowledge base: ${resumeText}. Do not go beyond the information provided in the resume.`;
        
        async function handleChat() {
            const userMessage = chatInput.value.trim();
            if (!userMessage) return;

            appendMessage(userMessage, 'user-message');
            chatInput.value = '';
            chatSend.disabled = true;
            chatSend.innerHTML = '<span class="spinner"></span>';

            const botResponse = await callGeminiAPI(userMessage, chatSystemPrompt);
            appendMessage(botResponse, 'bot-message');
            chatSend.disabled = false;
            chatSend.textContent = 'Send';
        }

        function appendMessage(text, className) {
            const messageElement = document.createElement('div');
            messageElement.classList.add('chat-message', className);
            messageElement.textContent = text;
            chatWindow.appendChild(messageElement);
            chatWindow.scrollTop = chatWindow.scrollHeight;
        }

        chatSend.addEventListener('click', handleChat);
        chatInput.addEventListener('keyup', (e) => {
            if (e.key === 'Enter') {
                handleChat();
            }
        });


        // --- Animation Loop ---
        function animate() {
            requestAnimationFrame(animate);

            if (!selectedObject) {
                raycaster.setFromCamera(mouse, camera);
                const intersects = raycaster.intersectObjects(interactiveObjects);

                if (intersects.length > 0) {
                    if (hoveredObject !== intersects[0].object) {
                        if (hoveredObject) gsap.to(hoveredObject.position, { y: hoveredObject.userData.originalPosition.y, duration: 0.3 });
                        hoveredObject = intersects[0].object;
                        gsap.to(hoveredObject.position, { y: hoveredObject.userData.originalPosition.y + 5, duration: 0.3 });
                        document.body.style.cursor = 'pointer';
                    }
                } else {
                    if (hoveredObject) {
                        gsap.to(hoveredObject.position, { y: hoveredObject.userData.originalPosition.y, duration: 0.3 });
                        hoveredObject = null;
                        document.body.style.cursor = 'default';
                    }
                }
            } else {
                 if (selectedObject.name === "ai_assistant") {
                    selectedObject.rotation.y += 0.005;
                }
            }

            renderer.render(scene, camera);
        }

        // --- Event Listeners ---
        window.addEventListener('mousemove', onMouseMove);
        window.addEventListener('click', onMouseClick);
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });

        // --- Loader ---
        window.addEventListener('load', () => {
            const loader = document.getElementById('loader');
            gsap.to(loader, {
                opacity: 0, duration: 1,
                onComplete: () => loader.style.display = 'none'
            });
            animate();
        });
    </script>
</body>
</html>

