<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
        /* General styles */
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
            transition: background-color 0.5s, color 0.5s;
            overflow: hidden; /* Prevent scrolling on the body */
        }

        .container {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
            text-align: center;
            width: 100%;
            max-width: 1000px;
            transition: background-color 0.5s, color 0.5s;
            overflow-y: auto; /* Enable vertical scrolling */
            max-height: 90vh; /* Limit the height to fit in the viewport */
        }

        .container img {
            width: 160px;
            height: auto;
            margin-bottom: 10px;
            background-color: #fff;
            padding: 10px;
            border-radius: 8px;
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
            box-sizing: border-box;
        }

        .container button {
            width: 100%;
            padding: 12px;
            background-color: #9f54d9;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: background-color 0.3s, transform 0.3s;
        }

        .container button:hover {
            background-color: #8c4aad;
            transform: scale(1.05);
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
            color: black;
            margin-bottom: 10px;
        }

        body.dark-mode .contact-message {
            color: #f0f0f0;
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

        .video-container {
            padding: 10px 0;
            position: relative;
            margin-bottom: 15px;
            text-align: center;
            max-height: 70vh; /* Limit the height to fit in the viewport */
            overflow: auto; /* Enable scrolling if content overflows */
        }

        .video-title {
            font-size: 17px;
            margin-bottom: 10px;
        }

        .video-footer-text {
            margin-top: 5px;
            font-size: 19px;
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

        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            padding: 10px;
            background-color: #f9f9f9;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        body.dark-mode .user-info {
            background-color: #444;
        }

        .user-info img {
            border-radius: 50%;
            width: 50px;
            height: 50px;
            margin-right: 15px;
        }

        .user-info p {
            margin: 0;
            font-size: 16px;
            font-weight: bold;
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
        <div class="user-info">
            <img id="user-icon" src="" alt="User Icon">
            <p id="user-name">Username</p>
        </div>
        <img src="https://i.ibb.co/G2dH87P/Clipped-image-20240718-232638.png" alt="Medal Image" class="medallion">
        <h2 id="video-heading">The Process platform</h2>
        <button class="menu-button" onclick="document.getElementById('video-menu').classList.toggle('hidden')">Select Video</button>
        <div id="video-menu" class="menu-content hidden">
            <ul>
                <li onclick="showVideo('video1')">حصة التأهيل</li>
            </ul>
        </div>
        <div id="video1" class="video-container hidden">
            <h1 class="video-title">حصة التأهيل</h1>
            <div style="position: relative; padding-bottom: 56.25%;">
                <iframe src="https://drive.google.com/file/d/1mwmNKYtvwn318OhJEIC6nFOHnaOCr1ne/preview" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;" allowfullscreen scrolling="no"></iframe>
            </div>
        </div>

        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://