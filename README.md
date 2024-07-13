<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
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
            position: relative; /* Added for the menu button positioning */
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
            color: white; /* Color for dark mode */
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

        /* Sidebar styles */
        .sidebar {
            position: fixed;
            top: 0;
            left: 0;
            width: 250px;
            height: 100%;
            background-color: #333;
            color: #fff;
            transform: translateX(-100%);
            transition: transform 0.3s ease;
            z-index: 1000;
            overflow-y: auto;
            padding: 20px;
        }

        .sidebar.active {
            transform: translateX(0);
        }

        .menu-content {
            margin-bottom: 20px;
        }

        .menu {
            list-style-type: none;
            padding: 0;
        }

        .menu li {
            margin-bottom: 10px;
        }

        .menu a {
            color: #fff;
            text-decoration: none;
        }

        .menu a:hover {
            text-decoration: underline;
        }

        /* Smaller menu icon */
        .menu-toggle {
            position: absolute;
            top: 10px; /* Adjusted for the position of the icon */
            left: 10px; /* Position from the left edge */
            background: #4CAF50; /* Green background */
            color: white;
            border: none;
            border-radius: 50%; /* Circle shape */
            width: 40px; /* Size of the button */
            height: 40px; /* Size of the button */
            font-size: 24px; /* Size of the icon */
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 1000;
            transition: background-color 0.3s ease; /* Smooth transition */
        }

        .menu-toggle:hover {
            background-color: #45a049; /* Darker green on hover */
        }

        .menu-toggle::before {
            content: '☰'; /* Hamburger icon */
            font-size: 24px; /* Adjust icon size */
            color: white; /* Icon color */
        }

        .menu-toggle::after {
            content: '';
            position: absolute;
            top: 10px; /* Position the square in the middle of the top */
            left: 50%;
            width: 10px; /* Size of the square */
            height: 10px; /* Size of the square */
            background: white; /* Square color */
            transform: translateX(-50%); /* Center the square horizontally */
        }

        .content {
            padding-top: 70px; /* Adjusted for the position of the menu button */
        }

        /* Close Button */
        .close-btn {
            position: absolute;
            top: 5px;
            right: 5px;
            background: #ff4d4d; /* Red background */
            color: white;
            border: none;
            border-radius: 4px; /* Square corners */
            width: 15px;
            height: 15px;
            font-size: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 1001; /* Ensure the button is on top */
        }

        .close-btn:hover {
            background: #ff3333; /* Darker red on hover */
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

        function toggleSidebar() {
            document.querySelector('.sidebar').classList.toggle('active');
        }

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
            const themeSwitch = document.getElementById('theme-switch');
            if (document.body.classList.contains('dark-mode')) {
                themeSwitch.checked = true;
            } else {
                themeSwitch.checked = false;
            }
        }
    </script>
</head>
<body>
    <div class="container" id="login-container">
        <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image" class="medallion">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Enter username" onkeypress="handleEnterKey(event)">
        <button onclick="login()">Login</button>
        <p class="footer-text">Developed by Eng: Mora</p>
    </div>

    <div class="container hidden" id="video-container">
        <button class="menu-toggle" onclick="toggleSidebar()"></button>  <!-- Menu Icon Button -->
        <div class="sidebar">
            <button class="close-btn" onclick="toggleSidebar()">✖</button> <!-- Close Button -->
            <div class="menu-content">
                <ul class="menu">
                    <li><a href="#video-1">Amr Diab - El Ta'ama</a></li>
                    <li><a href="#video-2">Amr Diab - Tetehabi</a></li>
                    <li><a href="#video-3">Magd El Qasem - Qasswet Albak</a></li>
                    <li><a href="#video-4">Amr Diab - El Ta'ama (Maqsoum Remix)</a></li>
                    <li><a href="#video-5">اه يا زمن</a></li>
                </ul>
            </div>
        </div>

        <!-- Main Content Section -->
        <section class="content">
            <h1 id="video-1">Amr Diab - El Ta'ama عمرو دياب - الطعامه</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/zrTT4CJAvZs?si=2OVur3UJKSbsJvpM" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama"></iframe>
            </div>
            
            <h1 id="video-2">Amr Diab - Tetehabi عمرو دياب - تتحبي</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/fDaHi6t9y9k?si=iYTIaiR3khSskU46" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - Tetehabi"></iframe>
            </div>
            
            <h1 id="video-3">Magd El Qasem - Qasswet Albak| مجد القاسم - قسوة قلبك</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/Spo8ijT3WKI?si=_j0KJVMSUUKYq6ft" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Magd El Qasem - Qasswet Albak"></iframe>
            </div>
            
            <h1 id="video-4">Amr Diab - El Ta'ama (Maqsoum Remix عمرو دياب - الطعامه (ريميكس مقسوم</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/9KRVRzErIOg?si=j76ruz-bxIPa5ehu" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama (Maqsoum Remix)"></iframe>
            </div>
            
            <h1 id="video-5">اه يا زمن</h1>
            <div class="video-container">
                <iframe src="https://fast.wistia.net/embed/iframe/iu5pz1rqv3?videoFoam=true" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="اه يا زمن"></iframe>
            </div>

            <p class="video-footer-text">Enjoy the videos! 😄</p>
        </section>

        <div class="theme-switch-wrapper">
            <input type="checkbox" id="theme-switch" class="theme-switch" onclick="toggleDarkMode()">
            <label class="theme-switch-label" for="theme-switch">
                <span class="sun-icon">☀️</span>
                <span class="moon-icon">🌙</span>
            </label>
        </div>
        <div id="welcome-container"></div>
    </div>
