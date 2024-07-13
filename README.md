<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
        /* General Styles */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            transition: background-color 0.5s, color 0.5s;
        }

        /* Login Page Styles */
        .login-page {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            padding: 20px;
        }

        .login-container {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
            text-align: center;
            width: 100%;
            max-width: 400px;
        }

        .login-container img {
            width: 180px;
            height: auto;
            margin-bottom: 20px;
        }

        .login-container h2 {
            margin-bottom: 20px;
        }

        .login-container input {
            width: 100%;
            padding: 12px;
            margin: 12px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .login-container button {
            width: 100%;
            padding: 12px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .login-container button:hover {
            background-color: #45a049;
        }

        .login-container .contact-icons {
            margin-top: 20px;
        }

        .login-container .contact-icons a {
            display: inline-block;
            margin: 0 10px;
        }

        .login-container .contact-icons img {
            width: 30px;
            height: 30px;
        }

        .login-container .footer-text {
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }

        /* Video Page Styles */
        .video-page {
            display: none;
            min-height: 100vh;
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: white;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
            padding: 10px 20px;
            z-index: 1000;
            display: flex;
            align-items: center;
        }

        .menu-button {
            background: none;
            border: none;
            cursor: pointer;
            font-size: 24px;
        }

        .menu-content {
            display: none;
            position: absolute;
            top: 50px;
            left: 20px;
            background-color: white;
            color: black;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
            border-radius: 5px;
            padding: 10px;
            z-index: 1000;
        }

        .menu-content a {
            display: block;
            padding: 10px;
            color: #333;
            text-decoration: none;
        }

        .menu-content a:hover {
            background-color: #f0f0f0;
        }

        .menu-content.show {
            display: block;
        }

        .video-container {
            padding-top: 60px; /* Adjust for fixed header */
        }

        .video-container {
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
            max-width: 800px;
            margin: 20px auto;
        }

        .video-container h1 {
            margin-bottom: 15px;
        }

        .video-container iframe {
            width: 100%;
            height: 315px;
            border: none;
        }

        .video-footer-text {
            margin-top: 20px;
            text-align: center;
            font-size: 16px;
            color: #888;
        }

        .contact-icons {
            margin-top: 20px;
            text-align: center;
        }

        .contact-icons a {
            display: inline-block;
            margin: 0 10px;
        }

        .contact-icons img {
            width: 30px;
            height: 30px;
        }

        /* Dark Mode Styles */
        body.dark-mode {
            background-color: #2c2c2c;
            color: #f0f0f0;
        }

        body.dark-mode .login-container {
            background-color: #3c3c3c;
            color: #f0f0f0;
        }

        body.dark-mode .login-container input {
            background-color: #5c5c5c;
            color: #f0f0f0;
            border: 1px solid #7c7c7c;
        }

        body.dark-mode .login-container button {
            background-color: #45a049;
        }

        body.dark-mode .login-container button:hover {
            background-color: #3a8b3e;
        }

        body.dark-mode .video-container {
            background-color: #3c3c3c;
            color: #f0f0f0;
        }

        body.dark-mode .video-container h1 {
            color: #f0f0f0;
        }

        body.dark-mode .video-container iframe {
            border: 1px solid #555;
        }

        body.dark-mode .video-footer-text {
            color: #f0f0f0;
        }

        body.dark-mode .contact-icons a {
            filter: brightness(0.8);
        }

        /* Dark Mode Switch */
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
    </style>
</head>
<body>
    <!-- Login Page Content -->
    <div class="login-page">
        <div class="login-container">
            <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image">
            <h2>Login</h2>
            <input type="text" id="username" placeholder="Username" onkeydown="handleEnterKey(event)">
            <button onclick="login()">Login</button>
            <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
            <div class="contact-icons">
                <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
                </a>
                <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
                </a>
            </div>
            <p class="footer-text">Developed by Eng: Mora</p>
        </div>
    </div>

    <!-- Video Page Content -->
    <div class="video-page">
        <header>
            <button id="menu-toggle" class="menu-button">☰</button>
            <div class="menu-content">
                <a href="#video1">Amr Diab - El Ta'ama</a>
                <a href="#video2">Amr Diab - Tetehabi</a>
                <a href="#video3">Magd El Qasem - Qasswet Albak</a>
                <a href="#video4">Amr Diab - El Ta'ama (Maqsoum Remix</a>
                <a href="#video5">اه يا زمن</a>
            </div>
        </header>

        <section class="video-container">
            <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image" class="medallion">
            <div id="welcome-container"></div>
            
            <!-- Video Sections -->
            <div class="video-section" id="video1">
                <h1>Amr Diab - El Ta'ama عمرو دياب - الطعامه</h1>
                <iframe src="https://www.youtube.com/embed/zrTT4CJAvZs?si=2OVur3UJKSbsJvpM" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama"></iframe>
            </div>

            <div class="video-section" id="video2">
                <h1>Amr Diab - Tetehabi عمرو دياب - تتحبي</h1>
                <iframe src="https://www.youtube.com/embed/fDaHi6t9y9k?si=iYTIaiR3khSskU46" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - Tetehabi"></iframe>
            </div>

            <div class="video-section" id="video3">
                <h1>Magd El Qasem - Qasswet Albak| مجد القاسم - قسوة قلبك</h1>
                <iframe src="https://www.youtube.com/embed/Spo8ijT3WKI?si=_j0KJVMSUUKYq6ft" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Magd El Qasem - Qasswet Albak"></iframe>
            </div>

            <div class="video-section" id="video4">
                <h1>Amr Diab - El Ta'ama (Maqsoum Remix عمرو دياب - الطعامه (ريميكس مقسوم</h1>
                <iframe src="https://www.youtube.com/embed/9KRVRzErIOg?si=j76ruz-bxIPa5ehu" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama (Maqsoum Remix"></iframe>
            </div>

            <div class="video-section" id="video5">
                <h1>اه يا زمن</h1>
                <iframe src="https://fast.wistia.net/embed/iframe/iu5pz1rqv3?videoFoam=true" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="اه يا زمن"></iframe>
            </div>

            <!-- Contact Icons -->
            <div class="contact-icons">
                <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
                </a>
                <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
                </a>
            </div>
            <p class="video-footer-text">Developed by Eng: Mora</p>
        </section>

        <!-- Dark Mode Switch -->
        <div class="theme-switch-wrapper">
            <input type="checkbox" id="theme-switch" class="theme-switch">
            <label for="theme-switch" class="theme-switch-label">
                <span class="sun-icon">🌞</span>
                <span class="moon-icon">🌚</span>
            </label>
        </div>
    </div>

    <script>
        let activeUsers = {};

        function login() {
            const username = document.getElementById('username').value.trim();
            if (username === '') {
                alert('Please enter a username.');
                return;
            }

            if (username === '45455' || username === '45454') {
                if (activeUsers[username]) {
                    alert('This username is already logged in on another device.');
                } else {
                    activeUsers[username] = true;
                    document.querySelector('.login-page').style.display = 'none';
                    document.querySelector('.video-page').style.display = 'block';

                    // Set personalized welcome message
                    const welcomeContainer = document.getElementById('welcome-container');
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
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme) {
                document.body.classList.add(savedTheme);
                if (savedTheme === 'dark-mode') {
                    document.getElementById('theme-switch').checked = true;
                }
            }
            setWelcomeMessage();
        });

        document.getElementById('theme-switch').addEventListener('change', toggleDarkMode);

        // Set theme on page load based on the saved theme in localStorage
        function setWelcomeMessage() {
            const username = document.getElementById('username').value.trim();
            const welcomeContainer = document.getElementById('welcome-container');
            if (username === '45455') {
                welcomeContainer.textContent = 'Welcome, Teto 🤩!';
            } else if (username === '45454') {
                welcomeContainer.textContent = 'Welcome, Eng: Mora 🤩!';
            }
        }

        // Menu Toggle
        document.getElementById('menu-toggle').addEventListener('click', () => {
            const menuContent = document.querySelector('.menu-content');
            menuContent.classList.toggle('show');
        });
    </script>
