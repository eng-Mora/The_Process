<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
        /* Your existing styles */
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
            max-width: 1000px; /* Increase the max-width to make the container wider */
            transition: background-color 0.5s, color 0.5s;
            overflow-y: auto;
            height: 100vh;
        }
        .container img {
            width: 160px;
            height: auto;
            margin-bottom: 10px;
            background-color: #fff; /* Light background for images in light mode */
            padding: 10px; /* Padding to ensure the background is visible */
            border-radius: 8px; /* Optional: to match container style */
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
            background-color: #9f54d9; /* Updated color */
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .container button:hover {
            background-color: #8c4aad; /* Slightly darker shade for hover effect */
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
        body.dark-mode .container img {
            background-color: #3c3c3c; /* Dark background for images in dark mode */
        }
        body.dark-mode input {
            background-color: #5c5c5c;
            color: #f0f0f0;
            border: 1px solid #7c7c7c;
        }
        body.dark-mode .container button {
            background-color: #9f54d9; /* Color for the button in dark mode */
            color: white; /* Text color for the button */
        }
        body.dark-mode .container button:hover {
            background-color: #8c4aad; /* Slightly darker shade for hover effect in dark mode */
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
            background-color: #fff; /* Light background for medallion in light mode */
            padding: 10px; /* Padding to ensure the background is visible */
            border-radius: 8px; /* Optional: to match container style */
        }
        body.dark-mode .medallion {
            background-color: #3c3c3c; /* Dark background for medallion in dark mode */
        }
        .video-container {
            padding: 10px 0; /* Adjust padding to add space around the title and video */
            position: relative;
            margin-bottom: 15px; /* Increase margin-bottom for more space between videos */
            text-align: center; /* Center align the text */
        }
        .video-title {
            font-size: 17px; /* Adjust the font size for the video title */
            margin-bottom: 10px; /* Add space between the title and the video */
        }
        .video-container iframe {
            border-radius: 8px; /* Add border-radius to match the design */
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

        .menu-content {
            background-color: #2c2c2c;
            color: white;
            padding: 10px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .menu-button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 4px;
            margin-bottom: 20px;
        }
        .menu-button:hover {
            background-color: #45a049;
        }

        .menu-content ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }

        .menu-content ul li {
            padding: 10px 15px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .menu-content ul li:hover {
            background-color: #444;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <div class="container" id="login-container">
        <img src="https://i.ibb.co/G2dH87P/Clipped-image-20240718-232638.png" alt="Medal Image">
        <h2>The Process platform</h2>
        <input type="text" id="username" placeholder="Enter Username" onkeydown="handleEnterKey(event)">
        <button onclick="login()">Login</button>
        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
            </a>
            <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
            </a>
            <a href="http://t.me/Mora_mo1" target="_blank" title="Telegram">
                <img src="https://i.ibb.co/9TGmH7c/cropped-image.png" alt="Telegram Icon">
            </a>
        </div>
        <p class="footer-text">Developed by Eng: Amr Mohamed</p>
    </div>

    <div class="container hidden" id="video-container">
        <img src="https://i.ibb.co/G2dH87P/Clipped-image-20240718-232638.png" alt="Medal Image" class="medallion">
        <div id="welcome-container" class="hidden"></div>
        <h2 id="video-heading">The Process platform - {{username}}</h2>
        <button class="menu-button" onclick="document.getElementById('video-menu').classList.toggle('hidden')">Select Video</button>
        <div id="video-menu" class="menu-content hidden">
            <ul>
                <li onclick="showVideo('video1')">Amr Diab - El Ta'ama</li>
                <li onclick="showVideo('video2')">Amr Diab - Tetehabi</li>
                <li onclick="showVideo('video3')">Magd El Qasem - Qasswet Albak</li>
                <li onclick="showVideo('video4')">Amr Diab - El Ta'ama (Maqsoum Remix)</li>
                <li onclick="showVideo('video5')">اه يا زمن</li>
            </ul>
        </div>
        <div id="video1" class="video-container hidden">
            <h1 class="video-title">Amr Diab - El Ta'ama عمرو دياب - الطعامه</h1>
            <iframe src="https://www.youtube.com/embed/zrTT4CJAvZs?si=2OVur3UJKSbsJvpM" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama"></iframe>
        </div>
        <div id="video2" class="video-container hidden">
            <h1 class="video-title">Amr Diab - Tetehabi عمرو دياب - تتحبي</h1>
            <iframe src="https://www.youtube.com/embed/fDaHi6t9y9k?si=iYTIaiR3khSskU46" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - Tetehabi"></iframe>
        </div>
        <div id="video3" class="video-container hidden">
            <h1 class="video-title">Magd El Qasem - Qasswet Albak| مجد القاسم - قسوة قلبك</h1>
            <iframe src="https://www.youtube.com/embed/Spo8ijT3WKI?si=_j0KJVMSUUKYq6ft" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Magd El Qasem - Qasswet Albak"></iframe>
        </div>
        <div id="video4" class="video-container hidden">
            <h1 class="video-title">Amr Diab - El Ta'ama (Maqsoum Remix عمرو دياب - الطعامه (ريميكس مقسوم</h1>
            <iframe src="https://www.youtube.com/embed/9KRVRzErIOg?si=j76ruz-bxIPa5ehu" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama (Maqsoum Remix"></iframe>
        </div>
        <div id="video5" class="video-container hidden">
            <h1 class="video-title">اه يا زمن</h1>
            <script src="https://fast.wistia.com/embed/medias/iu5pz1rqv3.jsonp" async></script>
            <script src="https://fast.wistia.com/assets/external/E-v1.js" async></script>
            <div class="wistia_responsive_padding" style="padding:55.94% 0 0 0;position:relative;">
                <div class="wistia_responsive_wrapper" style="height:100%;left:0;position:absolute;top:0;width:100%;">
                    <div class="wistia_embed wistia_async_iu5pz1rqv3 seo=true videoFoam=true" style="height:100%;position:relative;width:100%">
                        <div class="wistia_swatch" style="height:100%;left:0;opacity:0;overflow:hidden;position:absolute;top:0;transition:opacity 200ms;width:100%;">
                            <img src="https://fast.wistia.com/embed/medias/iu5pz1rqv3/swatch" style="filter:blur(5px);height:100%;object-fit:contain;width:100%;" alt="" aria-hidden="true" onload="this.parentNode.style.opacity=1;" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
            </a>
            <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
            </a>
            <a href="http://t.me/Mora_mo1" target="_blank" title="Telegram">
                <img src="https://i.ibb.co/9TGmH7c/cropped-image.png" alt="Telegram Icon">
            </a>
        </div>
        <p class="video-footer-text">Developed by Eng: Amr Mohamed</p>
    </div>

    <div class="theme-switch-wrapper">
        <input type="checkbox" id="theme-switch" class="theme-switch">
        <label class="theme-switch-label" for="theme-switch">
            <span class="moon-icon">🌚</span>
            <span class="sun-icon">🌞</span>
        </label>
    </div>

    <script>
        let activeUsers = {};

        function login() {
            const username = document.getElementById('username').value.trim();
            const welcomeContainer = document.getElementById('welcome-container');
            const videoHeading = document.getElementById('video-heading');

            if (username === '') {
                alert('Please enter a username.');
                return;
            }

            if (username === '45455' || username === '45454') {
                if (Object.keys(activeUsers).length > 0) {
                    alert('Another user is already logged in. Please log out first.');
                    return;
                }

                activeUsers[username] = true;
                document.getElementById('login-container').classList.add('hidden');
                document.getElementById('video-container').classList.remove('hidden');

                if (username === '45455') {
                    welcomeContainer.textContent = 'Welcome, Teto 🤩!';
                    videoHeading.innerHTML = 'The Process platform - Teto 🤩';
                } else if (username === '45454') {
                    welcomeContainer.textContent = 'Welcome, Eng: Mora 🤩!';
                    videoHeading.innerHTML = 'The Process platform - Eng: Mora 🤩';
                }

                welcomeContainer.classList.remove('hidden');
                setTimeout(() => {
                    welcomeContainer.classList.add('hidden');
                }, 7000);
            } else {
                alert('Invalid username');
            }
        }

        function handleEnterKey(event) {
            if (event.key === 'Enter') {
                login();
            }
        }

        window.addEventListener('beforeunload', () => {
            const username = document.getElementById('username').value.trim();
            if (username === '45455' || username === '45454') {
                delete activeUsers[username];
            }
        });

        function showVideo(videoId) {
            document.querySelectorAll('.video-container').forEach(video => {
                video.classList.add('hidden');
            });
            document.getElementById(videoId).classList.remove('hidden');
        }

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
        }

        document.getElementById('theme-switch').addEventListener('change', toggleDarkMode);
    </script>
