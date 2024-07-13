<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
        /* Global styles */
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
            transition: background-color 0.5s, color 0.5s;
        }
        .container {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
            text-align: center;
            width: 100%;
            max-width: 800px;
            transition: background-color 0.5s, color 0.5s;
            overflow-y: auto;
            height: 100vh;
        }
        .container img {
            width: 180px;
            height: auto;
            margin-bottom: 20px;
        }
        .container h2, .container h1 {
            margin-bottom: 20px;
        }
        .container input {
            width: 100%;
            padding: 12px;
            margin: 12px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .container button {
            width: 100%;
            padding: 12px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .container button:hover {
            background-color: #45a049;
        }
        .hidden {
            display: none;
        }
        .icon {
            width: 50px;
            height: 50px;
            cursor: pointer;
            margin-top: 20px;
        }
        .footer-text {
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }
        .contact-icons {
            margin-top: 10px;
        }
        .contact-icons a {
            display: inline-block;
            margin: 0 10px;
        }
        .contact-icons img {
            width: 30px;
            height: 30px;
        }
        .contact-message {
            font-size: 18px;
            color: black; /* Default color for light mode */
            margin-bottom: 10px;
        }
        body.dark-mode .contact-message {
            color: #f0f0f0; /* Color for dark mode */
        }
        body.dark-mode {
            background-color: #2c2c2c;
            color: #f0f0f0;
        }
        body.dark-mode .container {
            background-color: #3c3c3c;
            color: #f0f0f0;
        }
        body.dark-mode input {
            background-color: #5c5c5c;
            color: #f0f0f0;
            border: 1px solid #7c7c7c;
        }
        body.dark-mode button {
            background-color: #45a049;
        }
        body.dark-mode button:hover {
            background-color: #3a8b3e;
        }
        #welcome-container {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 20px;
            color: #888;
            background-color: rgba(0, 0, 0, 0.6);
            padding: 12px 18px;
            border-radius: 4px;
        }
        body.dark-mode #welcome-container {
            color: #f0f0f0;
            background-color: rgba(255, 255, 255, 0.3);
        }
        .medallion {
            width: 180px;
            height: auto;
            margin: 0 auto 20px;
            display: block;
        }
        .video-container {
            padding: 56.25% 0 0 0;
            position: relative;
            margin-bottom: 20px;
        }
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        .video-footer-text {
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }
        body.dark-mode .video-footer-text {
            color: #f0f0f0;
        }
        .theme-switch-wrapper {
            position: absolute;
            top: 20px;
            right: 20px;
            display: flex;
            align-items: center;
        }
        .theme-switch {
            display: none;
        }
        .theme-switch-label {
            display: flex;
            align-items: center;
            cursor: pointer;
        }
        .theme-switch-label .sun-icon,
        .theme-switch-label .moon-icon {
            font-size: 24px;
            transition: opacity 0.5s;
        }
        .theme-switch:checked + .theme-switch-label .sun-icon {
            opacity: 0;
        }
        .theme-switch:not(:checked) + .theme-switch-label .moon-icon {
            opacity: 0;
        }
        .video-section {
            display: flex;
        }
        .video-menu {
            width: 250px;
            background-color: #f8f8f8;
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            margin-right: 20px;
            height: 100%;
            overflow-y: auto;
        }
        .video-menu h3 {
            margin-top: 0;
        }
        .video-menu a {
            display: block;
            padding: 10px;
            margin-bottom: 10px;
            background-color: #e0e0e0;
            color: #333;
            text-decoration: none;
            border-radius: 4px;
        }
        .video-menu a:hover {
            background-color: #d0d0d0;
        }
        .video-menu a.active {
            background-color: #b0b0b0;
        }
        .video-content {
            flex: 1;
        }
        .video-item {
            margin-bottom: 20px;
        }
    </style>
    <script>
        let activeUsers = {};

        function login() {
            const username = document.getElementById('username').value.trim();
            const welcomeContainer = document.getElementById('welcome-container');
            if (username === '') {
                alert('Please enter a username.');
                return;
            }

            if (username === '45455' || username === '45454') {
                if (activeUsers[username]) {
                    alert('This username is already logged in on another device.');
                } else {
                    activeUsers[username] = true;
                    document.getElementById('login-container').classList.add('hidden');
                    document.getElementById('video-container').classList.remove('hidden');

                    // Set personalized welcome message
                    if (username === '45455') {
                        welcomeContainer.textContent = 'Welcome, Teto 🤩!';
                    } else if (username === '45454') {
                        welcomeContainer.textContent = 'Welcome, Eng: Mora 🤩!';
                    }

                    // Show welcome message for 7 seconds then hide it
                    setTimeout(() => {
                        welcomeContainer.classList.add('hidden');
                    }, 7000);  // Display welcome message for 7 seconds
                }
            } else {
                alert('Invalid username');
            }
        }

        function handleEnterKey(event) {
            if (event.key === 'Enter') {
                login();
            }
        }

        window.addEventListener('beforeunload', function () {
            const username = document.getElementById('username').value.trim();
            if (username && activeUsers[username]) {
                delete activeUsers[username];
            }
        });

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
            const themeSwitch = document.getElementById('theme-switch');
            if (document.body.classList.contains('dark-mode')) {
                themeSwitch.checked = true;
            } else {
                themeSwitch.checked = false;
            }
        }

        document.addEventListener('DOMContentLoaded', () => {
            // Add scroll event listener to update menu active link
            const menuLinks = document.querySelectorAll('.video-menu a');
            const sections = document.querySelectorAll('.video-item h1');

            window.addEventListener('scroll', () => {
                let index = sections.length;

                while (--index && window.scrollY + 50 < sections[index].offsetTop) {}

                menuLinks.forEach((link) => link.classList.remove('active'));
                menuLinks[index].classList.add('active');
            });

            // Add click event listeners to menu links
            menuLinks.forEach((link) => {
                link.addEventListener('click', (event) => {
                    event.preventDefault();
                    document.getElementById(link.getAttribute('href').substring(1)).scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                });
            });
        });
    </script>
</head>
<body>
    <!-- Login Page -->
    <div class="container" id="login-container">
        <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image">
        <h2>Enter Your Username</h2>
        <input type="text" id="username" placeholder="Enter Username" onkeypress="handleEnterKey(event)">
        <button onclick="login()">Login</button>
        <p class="footer-text">Developed by Eng: Mora</p>
    </div>

    <!-- Video Page -->
    <div class="container hidden" id="video-container">
        <div class="video-section">
            <!-- Sidebar Menu -->
            <div class="video-menu">
                <h3>Video List</h3>
                <a href="#el-taama">Amr Diab - El Ta'ama عمرو دياب - الطعامه</a>
                <a href="#tetehabi">Amr Diab - Tetehabi عمرو دياب - تتحبي</a>
                <a href="#qasswet-albak">Magd El Qasem - Qasswet Albak مجد القاسم - قسوة قلبك</a>
                <a href="#el-taama-remix">Amr Diab - El Ta'ama (Maqsoum Remix) عمرو دياب - الطعامه (ريميكس مقسوم)</a>
                <a href="#ah-ya-zaman">اه يا زمن</a>
            </div>

            <!-- Video Content -->
            <div class="video-content">
                <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image" class="medallion">
                <div id="welcome-container"></div>
                
                <div class="video-item">
                    <h1 id="el-taama">Amr Diab - El Ta'ama عمرو دياب - الطعامه</h1>
                </div>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/Ej8eA09i6yE?si=E3UJKSbsJvpM" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama"></iframe>
                </div>
                
                <div class="video-item">
                    <h1 id="tetehabi">Amr Diab - Tetehabi عمرو دياب - تتحبي</h1>
                </div>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/fDaHi6t9y9k?si=iYTIaiR3khSskU46" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - Tetehabi"></iframe>
                </div>
                
                <div class="video-item">
                    <h1 id="qasswet-albak">Magd El Qasem - Qasswet Albak مجد القاسم - قسوة قلبك</h1>
                </div>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/Spo8ijT3WKI?si=_j0KJVMSUUKYq6ft" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Magd El Qasem - Qasswet Albak"></iframe>
                </div>
                
                <div class="video-item">
                    <h1 id="el-taama-remix">Amr Diab - El Ta'ama (Maqsoum Remix) عمرو دياب - الطعامه (ريميكس مقسوم)</h1>
                </div>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/9KRVRzErIOg?si=j76ruz-bxIPa5ehu" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama (Maqsoum Remix)"></iframe>
                </div>
                
                <div class="video-item">
                    <h1 id="ah-ya-zaman">اه يا زمن</h1>
                </div>
                <div class="video-container">
                    <iframe src="https://fast.wistia.net/embed/iframe/iu5pz1rqv3?videoFoam=true" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="اه يا زمن"></iframe>
                </div>
            </div>
        </div>

        <!-- Contact Icons -->
        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
            </a>
            <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
            </a>
        </div>
        <p class="video-footer-text">Developed by Eng: Mora</p>
    </div>

    <!-- Theme Switcher -->
    <div class="theme-switch-wrapper">
        <input type="checkbox" id="theme-switch" class="theme-switch" onclick="toggleDarkMode()">
        <label for="theme-switch" class="theme-switch-label">
            <span class="sun-icon">🌞</span>
            <span class="moon-icon">🌚</span>
        </label>
    </div>
