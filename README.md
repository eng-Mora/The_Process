<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
        /* Reset default styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Global Styles */
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
        }

        /* Login Page Styles */
        .login-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }

        .login-form {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
            text-align: center;
            width: 100%;
            max-width: 400px;
            transition: background-color 0.5s, color 0.5s;
        }

        .login-form img {
            width: 180px;
            height: auto;
            margin-bottom: 20px;
        }

        .login-form h2 {
            margin-bottom: 20px;
        }

        .login-form input {
            width: 100%;
            padding: 12px;
            margin: 12px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .login-form button {
            width: 100%;
            padding: 12px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .login-form button:hover {
            background-color: #45a049;
        }

        .login-form .contact-message {
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }

        .login-form .contact-icons {
            margin-top: 10px;
        }

        .login-form .contact-icons a {
            display: inline-block;
            margin: 0 10px;
        }

        .login-form .contact-icons img {
            width: 30px;
            height: 30px;
        }

        .login-form .footer-text {
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }

        /* Dark Mode Styles */
        body.dark-mode {
            background-color: #2c2c2c;
            color: #f0f0f0;
        }

        body.dark-mode .login-form {
            background-color: #3c3c3c;
            color: #f0f0f0;
        }

        body.dark-mode .login-form input {
            background-color: #5c5c5c;
            color: #f0f0f0;
            border: 1px solid #7c7c7c;
        }

        body.dark-mode .login-form button {
            background-color: #45a049;
        }

        body.dark-mode .login-form button:hover {
            background-color: #3a8b3e;
        }

        body.dark-mode .login-form .contact-message {
            color: white;
        }

        body.dark-mode .login-form .contact-icons a {
            filter: brightness(0.8);
        }

        body.dark-mode .login-form .footer-text {
            color: #f0f0f0;
        }

        /* Header and Navigation Styles */
        header {
            background-color: transparent; /* Make header transparent */
            color: white;
            padding: 10px 20px;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            display: flex;
            align-items: center;
            z-index: 1000;
        }

        /* Menu Button */
        .menu-button {
            position: relative;
        }

        #menu-toggle {
            background-color: #555;
            color: white;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 5px;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }

        #menu-toggle:hover {
            background-color: #777;
        }

        /* Menu Styles */
        .menu-content {
            display: none;
            background-color: #2c2c2c;
            color: white;
            padding: 15px;
            position: absolute;
            top: 50px;
            left: 20px; /* Menu on the left */
            box-shadow: 0 4px 8px rgba(0,0,0,0.3);
            border-radius: 8px;
            z-index: 1000;
            width: 200px;
        }

        .menu-content.show {
            display: block;
        }

        .menu-content a {
            text-decoration: none;
            color: white;
            padding: 10px;
            display: block;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        .menu-content a:hover {
            background-color: #444;
        }

        /* Main Content Styles */
        .content {
            padding: 20px;
            margin-top: 60px; /* Space for the fixed header */
        }

        .video-container {
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
        }

        .video-section {
            margin-bottom: 30px;
        }

        .video-container iframe {
            width: 100%;
            height: 315px;
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

        .video-footer-text {
            text-align: center;
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }

        /* Dark Mode Styles */
        body.dark-mode .video-container {
            background-color: #3c3c3c;
            color: #f0f0f0;
        }

        body.dark-mode #menu-toggle {
            background-color: #777;
            color: #f0f0f0;
        }

        body.dark-mode #menu-toggle:hover {
            background-color: #999;
        }

        body.dark-mode .menu-content {
            background-color: #3c3c3c;
        }

        body.dark-mode .menu-content a {
            color: #f0f0f0;
        }

        body.dark-mode .menu-content a:hover {
            background-color: #555;
        }

        body.dark-mode .contact-icons a {
            filter: brightness(0.8);
        }

        body.dark-mode .video-footer-text {
            color: #f0f0f0;
        }

        /* Theme Switch */
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

        /* Medallion Image */
        .medallion {
            width: 180px;
            height: auto;
            margin: 0 auto 20px;
            display: block;
        }
    </style>
</head>
<body>
    <!-- Login Page -->
    <div class="login-container" id="login-container">
        <div class="login-form">
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

    <!-- Video Page -->
    <header>
        <button id="menu-toggle" class="menu-button">Menu</button>
        <div class="menu-content">
            <a href="#video1">Amr Diab - El Ta'ama</a>
            <a href="#video2">Amr Diab - Tetehabi</a>
            <a href="#video3">Magd El Qasem - Qasswet Albak</a>
            <a href="#video4">Amr Diab - El Ta'ama (Maqsoum Remix</a>
            <a href="#video5">اه يا زمن</a>
        </div>
    </header>

    <section class="content" id="video-page" class="hidden">
        <div class="video-container">
            <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image" class="medallion">
            <div id="welcome-container" class="hidden"></div>

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
                <iframe src="https://fast.wistia.net/embed/iframe/iu5pz1rqv3?videoFoam=true" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Magd El Qasem - Qasswet Albak"></iframe>
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
        </div>
    </section>

    <!-- Dark Mode Switch -->
    <div class="theme-switch-wrapper">
        <input type="checkbox" id="theme-switch" class="theme-switch" onclick="toggleDarkMode()">
        <label for="theme-switch" class="theme-switch-label">
            <span class="sun-icon">🌞</span>
            <span class="moon-icon">🌚</span>
        </label>
    </div>

    <!-- JavaScript -->
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
                    document.querySelector('.login-container').style.display = 'none';
                    document.querySelector('#video-page').style.display = 'block';

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

        // Function to show/hide the menu
        const menuToggle = document.getElementById('menu-toggle');
        const menuContent = document.querySelector('.menu-content');

        menuToggle.addEventListener('click', () => {
            menuContent.classList.toggle('show');
        });

        // Smooth scroll to video sections
        document.querySelectorAll('.menu-content a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Set a personalized welcome message
        function setWelcomeMessage() {
            const welcomeContainer = document.getElementById('welcome-container');
            const urlParams = new URLSearchParams(window.location.search);
            const username = urlParams.get('username');
            
            if (username === '45455') {
                welcomeContainer.textContent = 'Welcome, Teto 🤩!';
            } else if (username === '45454') {
                welcomeContainer.textContent = 'Welcome, Eng: Mora 🤩!';
            }
            setTimeout(() => {
                welcomeContainer.classList.add('hidden');
            }, 7000);  // Display welcome message for 7 seconds
        }

        // Call the setWelcomeMessage function when the page loads
        window.addEventListener('load', setWelcomeMessage);
    </script>
