<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
        /* ... existing CSS styles ... */
        .medallion {
            width: 180px;
            height: auto;
            margin: 0 auto 20px;
            display: block;
        }
        /* ... existing CSS styles ... */
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
    </script>
</head>
<body>
    <div class="container" id="login-container">
        <img src="https://i.ibb.co/YbW8y4B/new-medal-image.png" alt="Medal Image"> <!-- Updated Medal Image -->
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

    <div class="container hidden" id="video-container">
        <img src="https://i.ibb.co/YbW8y4B/new-medal-image.png" alt="Medal Image" class="medallion"> <!-- Updated Medal Image -->
        <div id="welcome-container"></div>
        
        <!-- Video Section -->
        <div class="video-section">
            <h1>Amr Diab - El Ta'ama عمرو دياب - الطعامه</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/zrTT4CJAvZs?si=2OVur3UJKSbsJvpM" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama"></iframe>
            </div>
            
            <h1>Amr Diab - Tetehabi عمرو دياب - تتحبي</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/fDaHi6t9y9k?si=iYTIaiR3khSskU46" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - Tetehabi"></iframe>
            </div>
            
            <h1>Magd El Qasem - Qasswet Albak| مجد القاسم - قسوة قلبك</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/Spo8ijT3WKI?si=_j0KJVMSUUKYq6ft" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Magd El Qasem - Qasswet Albak"></iframe>
            </div>
            
            <h1>Amr Diab - El Ta'ama (Maqsoum Remix عمرو دياب - الطعامه (ريميكس مقسوم</h1>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/9KRVRzErIOg?si=j76ruz-bxIPa5ehu" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama (Maqsoum Remix"></iframe>
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

    <div class="theme-switch-wrapper">
        <input type="checkbox" id="theme-switch" class="theme-switch" onclick="toggleDarkMode()">
        <label for="theme-switch" class="theme-switch-label">
            <span class="sun-icon">🌞</span>
            <span class="moon-icon">🌚</span>
        </label>
    </div>
</body>
</html>
