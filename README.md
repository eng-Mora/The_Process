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
    background-color: #302967; /* Updated background color */
    margin: 0;
    transition: background-color 0.5s, color 0.5s;
    overflow: hidden; /* Prevent scrolling on the body */
}
{
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

    .container button:before,
    .container button:after,
    .container button .button_reflection-1,
    .container button .button_reflection-2,
    .container button .button_circle-2 {
        content: "";
        position: absolute;
        top: 0;
        bottom: 0;
        width: 100%;
        background: rgba(255, 255, 255, 0.3);
        transition: all 0.3s ease;
    }

    .container button:before {
        left: -120%;
        transform: skewX(-30deg);
    }

    .container button:after {
        left: 100%;
        transform: skewX(30deg);
    }

    .container button:hover:before {
        left: 100%;
    }

    .container button:hover:after {
        left: -100%;
    }

    .container button:hover {
        transform: rotate(-4deg) scale(1.1);
    }

    .container button .button_reflection-1 {
        left: 120%;
    }

    .container button .button_reflection-2 {
        left: -70%;
    }

    .container button:hover .button_circle-2 {
        transform: translate(-20px, 20px) scale(1.1);
    }

    .container button.button_diamond:hover {
        transform: translateY(7px) rotate(-24deg) scale(1.1);
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

    body.dark-mode .container img {
        background-color: #3c3c3c;
    }

    body.dark-mode input {
        background-color: #5c5c5c;
        color: #f0f0f0;
        border: 1px solid #7c7c7c;
    }

    body.dark-mode .container button {
        background-color: #8c4aad;
    }

    body.dark-mode .container button:hover {
        background-color: #9f54d9;
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

    .video-container iframe {
        border-radius: 8px;
        width: 100%;
        height: auto;
        max-height: 100%;
    }

    .video-footer-text {
        margin-top: 5px;
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
    background-color: #8c4aad;
    color: white;
    padding: 10px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-height: 200px; /* Set the maximum height of the menu */
    overflow-y: auto;  /* Enable vertical scrolling */
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
        <input type="password" id="username" placeholder="Enter Username" onkeydown="handleEnterKey(event)">
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
                <li onclick="showVideo('video1')">حل واجب حصة 1 </li>
                <li onclick="showVideo('video2')">حل واجب حصة 2</li>
                <li onclick="showVideo('video3')">حل واجب حصة 3</li>
                <li onclick="showVideo('video4')">شرح حصة 3 (سنتر)</li>
                <li onclick="showVideo('video5')">حل واجب حصة 4</li>
                <li onclick="showVideo('video6')">حل واجب حصة 5</li>
                <li onclick="showVideo('video7')">lecture 1 exercises</li>
                <li onclick="showVideo('video8')">lecture 2 exercises</li>
                <li onclick="showVideo('video9')">lecture 3 exercises</li>
                <li onclick="showVideo('video10')">lecture 4 exercises</li>
                <li onclick="showVideo('video11')">حل واجب حصة 6</li>
                <li onclick="showVideo('video12')">حل واجب حصة 7</li>
                <li onclick="showVideo('video13')">حل واجب حصة 8</li>
                <li onclick="showVideo('video14')">حل واجب حصة 9</li>
                <li onclick="showVideo('video15')">حل واجب حصة10</li>
                <li onclick="showVideo('video16')">حل واجب حصة11</li>
                <li onclick="showVideo('video17')">حل واجب حصة 12</li>
                <li onclick="showVideo('video18')">حل واجب حصة 15</li>
                <li onclick="showVideo('video19')">حل واجب حصة 16</li>
                <li onclick="showVideo('video20')">حل واجب حصة 17</li>
                <li onclick="showVideo('video21')">حل واجب حصة 18</li>
                <li onclick="showVideo('video22')">حل واجب حصة 19</li>

            </ul>
        </div>
<div id="examVideo" class="video-container hidden">
    <h1 class="video-title">حل الامتحان</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1lVnm7PtWwWR6EVlMaod65E7EZ3iTy-ET/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        <h1 class="video-title">حل الامتحان</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1KupJUYCbdJQWeJhXop9np4u9i2OlHcTu/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
</div>
        <div id="video5" class="video-container hidden">
    <h1 class="video-title">(part1) حل واجب حصة 4</h1>
    <div style="position: relative; width: 100%; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1E_gyIwo2S8t_T5_4Q1XcTvekpPGlXQwg/preview" 
                style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;" 
                allowfullscreen scrolling="no" allow="encrypted-media">
        </iframe>
    </div>

    <h1 class="video-title">(part2) حل واجب حصة 4</h1>
    <div style="position: relative; width: 100%; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1JAJoaikg02O7DkbDu3317lMkbjEB_b9I/preview" 
                style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;" 
                allowfullscreen scrolling="no" allow="encrypted-media">
        </iframe>
    </div>

    <h1 class="video-title">الاجابات</h1>
    <iframe src="https://drive.google.com/file/d/1B9mwnM9Zl_k6l_qgUsLc2A16IoaBe4yz/preview" 
            width="640" height="480" allow="autoplay">
    </iframe>
</div>
        <div id="video1" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 1</h1>
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
                <iframe src="https://drive.google.com/file/d/1iiNJqMrDUKkTptUQVymPbMqEyf0UowBB/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
            </div>
            <iframe src="https://drive.google.com/file/d/1L5UPraDEgW_Kmh32eOaOU5uYK8UqER4V/preview" width="640" height="480" allow="autoplay"></iframe>
        </div>
        <div id="video2" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 2</h1>
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1kv5eqpNmC_X2ByBbfoLcXn6WUnA0eYVB/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
            </div>
            <iframe src="https://drive.google.com/file/d/1Qb7N0TRJ8Cj4gkZ2nK9ZhSgAp7NC6636/preview" width="640" height="480" allow="autoplay"></iframe>
            </div>
<div id="video3" class="video-container hidden">
            <h1 class="video-title">(part1) حل واجب حصة 3</h1>
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1Tf4neobTgDj7nXd9WoUXwNYMLJC-7FJE/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div> 
            <h1 class="video-title">(part2)</h1>
          <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1nHPcJfPX1cuC_Quy52RqciSkQZ1UWBdx/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          
            <h1 class="video-title">الاجابات</h1>

           <iframe src="https://drive.google.com/file/d/13xgvtm1WuqO5FdtAp9kE7QaOPKQ5BXAA/preview" width="640" height="480" allow="autoplay"></iframe>
            </div>
<div id="video4" class="video-container hidden">
            <h1 class="video-title">شرح حصة 3 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1K23MDswnSetWJRpvkhgbdzAF9HEp6syq/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>

      <h1 class="video-title">شرح حصة 3 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1f0f8Q3hTneh5tnT1piVaIe4xE8EceBHg/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
</div>

  <div id="video6" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 5 (part 1)</h1>  
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/16TMFaBOfkIB6F14NACeqYGnNmQPrFkOh/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        
<h1 class="video-title">حل واجب حصة 5 (part 2)
</h1>  <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1VWTzWJ8il2QNceP29XdzYdTEXDL8wYUj/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
 </div>
             <h1 class="video-title">الاجابات</h1>

<iframe src="https://drive.google.com/file/d/1JjdpQ3-YY9JcR4PIFD6qFRCiE7skqFKQ/preview" width="640" height="480" allow="autoplay"></iframe>
 </div>
 
<div id="video7" class="video-container hidden">
    <h1 class="video-title">lecture 1 exercises</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1MGm9pT1T2Wme-MO9iMe-b7sKpYvcj3Gw/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    </div>
<div id="video8" class="video-container hidden">
    <h1 class="video-title">lecture 2 exercises</h1>

    <h1 class="video-title">    part 1     </h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/13L0ifCf-T6YGnpCwavxXPB-RVbVHmg8P/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
    <h1 class="video-title">       part 2          </h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1PSEE0hTo8j8sKnyiA7n7L5th61yxb7yj/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
    <h1 class="video-title">        part 3         </h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1dKYEF4dDpvMqNJ_mCLGpPDSholq7R5Rm/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    </div>
<div id="video9" class="video-container hidden">
    <h1 class="video-title">lecture 3 exercises</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1_hfwKKYNdY6J3wgDQS9vJqbYpQ_g6n45/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    </div>
<div id="video10" class="video-container hidden">
    <h1 class="video-title">lecture 4 exercises</h1>
    <h1 class="video-title">part 1</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1hqTGYDwSqnWtFqKUfZVr4mLWXVAtMzCy/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
    <h1 class="video-title">part 2</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1ccLtf7KaafkEQTxzgIYIBfMn7Jhwyb3d/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    </div>
<div id="video11" class="video-container hidden">
            <h1 class="video-title"> حل واجب حصة 6</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1V34aIAOPGhUdRksC7kgEQ8l0s8u1NLhK/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1bN0w4hN1q92ukBL2N0_4RluI5As7aBiW/preview" width="640" height="480" allow="autoplay"></iframe>
    </div>
           <div id="video12" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 7 (part 1)</h1>
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/14YFJTqTwknrrSuBAJKzWgI4k3d63omkK/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title"> (part 2)</h1>
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1abKZL-6MOzBIhGAso84HrkwWTgFNPDd-/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title"> (part 3)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/16b6LqFdMhUW4JtC_JmXpzgk-_0SFt80y/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1sjiK-D-vn9evR84D9cJ7CMoBaU-nzz2z/preview" width="640" height="480" allow="autoplay"></iframe>
</div>

<div id="video13" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 8 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/165_d1qEaXzl_128dgX4f5Z8PzLNC3I0N/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 8 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1WJ-WTJ39JMBCsqpqaZpC1zM7TIVXA4Fz/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1SSYWj0_0sMPXp0brrPFoIQ7NWlwdRJba/preview" width="640" height="480" allow="autoplay"></iframe>
</div>

<div id="video14" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 9 (part 1)</h1>
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1dy9Ze_jxwiPP1NfFo8n2HqPQqzqMrHWj/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 9 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/12gBF4QqYN6Fie-9Nc8Z4SHkODm4zU2cn/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1OyhK-zJZ4BGafDeZzrE3AOB-qHGaitYn/preview" width="640" height="480" allow="autoplay"></iframe>
</div>

<div id="video15" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 10 (part 1)</h1>
            <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1TCtZ7qxH-mOzrFLkCrI8peKhF6SPnk9d/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 10 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1E8yhjJ-b0D2wm-0IR6v54GPxQfYHrbGQ/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
             <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1nugUrE7M23qVk3y_sp4eNvAyzmLVUgjH/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video16" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 11 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1Rb-r7OXwGlfM8kUTwu_eoyUBIAYKF8rq/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 11 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1Zrk4bfFucA3nwa77cSjYEdK-NEAPDO_W/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 11 (part 3)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1DqwIeC3-J1zOyLF_LzDOh9rCMQIlLmBS/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">Answers</h1>
<iframe src="https://drive.google.com/file/d/1ISxN0O1eIpt-WckUFLr7IOBsRykMERUk/preview" width="640" height="480" allow="autoplay"></iframe>
</div>

<div id="video17" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 12 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1P8QDspeIW6rc5ciD5GXSNu2hErRsz55L/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 12 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1q9eGKbtTZGuzqPGeLwgRZZtWGTkNEAjr/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 12 (part 1)</h1>
<iframe src="https://drive.google.com/file/d/1rGc_5pkLjnaDM3CCZwXR-Pzgsb0JFcZ2/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video18" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 15 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1Do8m1xQ-tEn7U4_5xAtKNjZ2VOHiw5xU/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
            <h1 class="video-title">حل واجب حصة 15 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1JQV3sNeHpJswUg0ebNniRR9CcwO3VTWC/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
            <h1 class="video-title">حل واجب حصة 15 (part 3)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1FRCVhqYZlRqCLw9XLiEpaPCSlKc22Kzn/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">Answers</h1>
<iframe src="https://drive.google.com/file/d/1StpthZHyd_pxX8Znd8jCIGeeYsdcPoXe/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video19" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 16 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1zgNhFXQY7pO6fbNFBVh_ClAfG5P12J0O/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 16 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1EEKW1SvwYJDpFfWzfay2hCushhiXUP1v/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
            <h1 class="video-title">حل واجب حصة 16 (part 3)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1NUJF2103h1BTxWlhtVUuhZsUwraul30M/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">Answers</h1>
<iframe src="https://drive.google.com/file/d/1Fo2A56VlE0SuhmVKQxWoG1LJzjRRIKZA/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video20" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 17 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1okTYOXI6vh2za5NDNZyOQHxshAODWqmU/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 17 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1PgYZv__rwa_sYhJFrT4K2JQaKS4qWRwT/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
             <h1 class="video-title">Answers</h1>
<iframe src="https://drive.google.com/file/d/1Zk1zi9uj3edaCsU_J7o5Yb73NZgXbksC/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video21" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 18 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1_LEoc0bVmKS0Zi-D6t7rJ7lJcvivsezI/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 18 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/19QeFa6xHPPIfQ1O8WJ3jpxeQi84hUD_J/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
             <h1 class="video-title">Answers</h1>
<iframe src="https://drive.google.com/file/d/1FFTo3auvao_OL0Yb6l9iquZHaE0OKQ_6/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video22" class="video-container hidden">
            <h1 class="video-title">حل واجب حصة 19 (part 1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1IpxleKUMyBld3Dov8aiIi5L4JKL9pi0d/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
            <h1 class="video-title">حل واجب حصة 19 (part 2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/15Zz9Rh_lSXMdokdjd8TXiRoZwtMfjlKE/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
             <h1 class="video-title">Answers</h1>
<iframe src="https://drive.google.com/file/d/1E0W6UhgP9od65djtNdSB6dPHAdM4-ki1/preview" width="640" height="480" allow="autoplay"></iframe>
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
        const userDetails = {
            'admin.mora': { name: 'administrator', icon: 'https://i.ibb.co/7KQqmM3/download.png'},
            //private
            '16075': { name: 'امنية ايمن ', icon: 'https://api.multiavatar.com/a1b9a98b131af9380c.svg'},
             '70126': { name: 'مازن محمد', icon: 'https://api.multiavatar.com/988a824d7b64800149.svg'},
            '16840': { name: 'سما ابراهيم', icon: 'https://api.multiavatar.com/e736fdd76d2f8bb555.svg'},
            '15032': { name: 'تسنيم محمد', icon: 'https://api.multiavatar.com/1eae35ecc479f6edd1.svg'},
            '88105': { name: 'سندي عصام', icon: 'https://api.multiavatar.com/9b8b2ae7d917ccd9ce.svg'},
            '72137': { name: 'رودينا ايمن', icon: 'https://api.multiavatar.com/240315fc1890fd05ae.svg'},
            '80135': { name: 'محمد اشرف', icon: 'https://api.multiavatar.com/f84f24bcc7b72eebf0.svg'},
            '80650': { name: 'احمد ايمن رأفت', icon: 'https://api.multiavatar.com/5504deeeaae32c00b6.svg'},
            '23069': { name: 'يوسف حسن ', icon: 'https://api.multiavatar.com/76d730110bb25b52e5.svg'},
            '66908': { name: 'احمد محمد عبداللطيف', icon: 'https://api.multiavatar.com/c91bc1e60640f2bd7a.svg'},
            '69756': { name: 'احمد ياسر', icon: 'https://api.multiavatar.com/e60abda884983d5404.svg'},
            '50808': { name: 'احمد حسين', icon: 'https://api.multiavatar.com/390264ffe38ec2ed41.svg'},
            '84536': { name: 'زياد خالد', icon: 'https://api.multiavatar.com/4a955a93363ada217b.svg'},
            '41596': { name: 'نورالدين هيثم', icon: 'https://api.multiavatar.com/cbfb555bf65d9c5b93.svg'},
            '28411': { name: 'رحيق سيد', icon: 'https://api.multiavatar.com/098db318e1715a48dd.svg'},
            '73057': { name: 'عمر هاني', icon: 'https://api.multiavatar.com/5423b44a5f0baed737.svg'},
            '35804': { name: 'ريم خالد', icon: 'https://api.multiavatar.com/3dbc9c4373c16bf197.svg'},
            '69897': { name: 'اروى احمد', icon: 'https://api.multiavatar.com/e71c17c25671802202.svg'},
            '44746': { name: 'سعيد سعد', icon: 'https://api.multiavatar.com/94a0dd6577ca3c7291.svg'},
            '80546': { name: 'مازن احمد', icon: 'https://api.multiavatar.com/94a0dd6577ca3c7291.svg' },
            '21428': { name: 'محمد احمد', icon: 'https://api.multiavatar.com/Guadalajara.svg'},




            '52434o': { name: 'فارس ايمن', icon: 'https://api.multiavatar.com/f4fd82c786f12ce4c0.svg'},
            '11633': { name: 'يوسف ايمن ابوضيف', icon: 'https://api.multiavatar.com/f4fd82c786f12ce4c0.svg'},
            '25695': { name: 'فيرا عصام عدلي', icon: 'https://api.multiavatar.com/2969b18bac7b3cec76.svg'},
            '63855o': { name: 'عبدالرحمن محمود عبدالحسيب', icon: 'https://api.multiavatar.com/f0a9ab062cd811e549.svg'},
            '25654o': { name: 'اسلام محمد شعراوي ', icon: 'https://api.multiavatar.com/3a565be8bfd4e264e4.svg'},
            '25343o': { name: 'يوسف محمود يحيي', icon: 'https://api.multiavatar.com/9b840c355db11594e1.svg'},
            '28126o': { name: 'يوسف محمد', icon: 'https://api.multiavatar.com/9b840c355db11594e1.svg'},
            '56193': { name: 'حبيبة محمد', icon: 'https://api.multiavatar.com/19b4a93ea61f0b650e.svg'},
            '75516o': { name: 'حنين مصطفى', icon: 'https://api.multiavatar.com/ad62e7d97f6967fc85.svg'},
            '53336o': { name: 'مريم اشرف', icon: 'https://api.multiavatar.com/2969b18bac7b3cec76.svg'},
            '48389': { name: 'سندس صلاح', icon: 'https://api.multiavatar.com/36aa46f54891ced0b5.svg'},
            '28354o': { name: 'مريم احمد', icon: 'https://api.multiavatar.com/cd15833a17efc52a72.svg'},
            '75539o': { name: 'جنى طارق', icon: 'https://api.multiavatar.com/eb9203245d22ab2c3f.svg'},
            '89089o': { name: 'جنى محمد', icon: 'https://api.multiavatar.com/9359ac6f0b88e61eb6.svg'},
            '41292o': { name: 'مريم سعيد', icon: 'https://api.multiavatar.com/2947fd65b9978407f2.svg'},
            '32532': { name: 'مريم عاطف', icon: 'https://api.multiavatar.com/f90923036c611bd66d.svg'},
            '30223o': { name: 'سيف الدين تامر', icon: 'https://api.multiavatar.com/7995823da6025e8a33.svg'},
            '20608o': { name: 'زياد احمد', icon: 'https://api.multiavatar.com/4db29acccc604fe610.svg'},
            '48392o': { name: 'عمار اشرف', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '82128o': { name: 'زياد إيهاب', icon: 'https://api.multiavatar.com/f84f24bcc7b72eebf0.svg'},
            '89303o': { name: 'حمدي محمد ', icon: 'https://api.multiavatar.com/9b840c355db11594e1.svg' },
            '32546o': { name: 'لوجين وائل ', icon: 'https://api.multiavatar.com/20ba7ccc9a755d9743.svg' },
            '23756o': { name: 'ضحى محمد', icon: 'https://api.multiavatar.com/2422f12d6e1bb1d40b.svg' },
            '67084o': { name: 'هنا سعد', icon: 'https://api.multiavatar.com/12de69a625c83e5ca8.svg' },
            '23849': { name: 'فرح عماد', icon: 'https://api.multiavatar.com/098db318e1715a48dd.svg'},
            '81463': { name: 'احمد ناجح', icon: 'https://api.multiavatar.com/5160ab1a42287f8bde.svg'},
            '85459': { name: 'يوسف محمد عبدالفتاح', icon: 'https://api.multiavatar.com/5160ab1a42287f8bde.svg'},
            '73431o': { name: 'سلمى محمد السيد', icon: 'https://api.multiavatar.com/098db318e1715a48dd.svg'},
            '19153': { name: 'شهد سعيد', icon: 'https://api.multiavatar.com/098db318e1715a48dd.svg'},
            '41688o': { name: 'اروى مصطفى', icon: 'https://api.multiavatar.com/2969b18bac7b3cec76.svg'},
            '94452o': { name: 'دنيا كمال', icon: 'https://api.multiavatar.com/20ba7ccc9a755d9743.svg'},
            '22030': { name: 'حبيبه احمد عبدالرؤوف', icon: 'https://api.multiavatar.com/098db318e1715a48dd.svg'},
            '68450': { name: 'ملك اشرف', icon: 'https://api.multiavatar.com/12de69a625c83e5ca8.svg'},
            '06764': { name: 'زينب محمد على', icon: 'https://api.multiavatar.com/12de69a625c83e5ca8.svg'},
            '95464o': { name: 'عمرو طارق', icon: 'https://api.multiavatar.com/5160ab1a42287f8bde.svg'},
            '92758': { name: 'مازن عبدالوهاب', icon: 'https://api.multiavatar.com/f4fd82c786f12ce4c0.svg'},
            '97510o': { name: 'مهند خالد عبدالفتاح', icon: 'https://api.multiavatar.com/5160ab1a42287f8bde.svg'},
            '41729': { name: 'مؤمن ايهاب فؤاد', icon: 'https://api.multiavatar.com/f1e1a5a8905966f75e.svg'},
            '15290': { name: 'محمد عمرو عبدالوهاب', icon: 'https://api.multiavatar.com/19e5045f1a5f9b62e1.svg'},
            '04596': { name: 'احمد سامح سعيد', icon: 'https://api.multiavatar.com/f2d71bd78f373f11c4.svg'},
            '08724': { name: 'عبدالوهاب عبدالرحمن السيد', icon: 'https://api.multiavatar.com/234e2181c7d72e4201.svg'},
            '19734': { name: 'كريم عبدالمنعم', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '56302': { name: 'ياسين محمد اسامه', icon: 'https://api.multiavatar.com/5160ab1a42287f8bde.svg'},
            '28417': { name: 'يوسف ابراهيم محمد', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '91846': { name: 'سارة عماد وجدي', icon: 'https://api.multiavatar.com/20ba7ccc9a755d9743.svg'},
            '45176o': { name: 'عبدالرحمن محمد محمود', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '81376o': { name: 'محمود طارق محروس', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '64159o': { name: 'زياد محمد رمضان', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '75183o': { name: 'معاذ عيسى محمد عيسى', icon: 'https://api.multiavatar.com/f2d71bd78f373f11c4.svg'},
            '68294o': { name: 'يسري محمد', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '75014': { name: 'نورا احمد مصطفى', icon: 'https://api.multiavatar.com/20ba7ccc9a755d9743.svg'},
            '48273': { name: 'احمد حسن توفيق', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '19385': { name: 'عمر جلال العرابي', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '57429': { name: 'باسل محمد العرابي', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '62831': { name: 'عبدالرحمن مصطفى', icon: 'https://api.multiavatar.com/f2d71bd78f373f11c4.svg'},
            '31957': { name: 'عبدالكريم مدحت', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '64743': { name: 'محمد صلاح احمد', icon: 'https://api.multiavatar.com/c8313188a97258e27c.svg'},
            '43198': { name: 'محمد احمد سلامه', icon: 'https://api.multiavatar.com/f2d71bd78f373f11c4.svg'},
            '99': { name: 'Teto', icon: 'https://api.multiavatar.com/7995823da6025e8a33.svg' }
        };

    const activeUsers = {};

    function login() {
        const username = document.getElementById('username').value.trim();
        const videoHeading = document.getElementById('video-heading');
        const userIcon = document.getElementById('user-icon');
        const userName = document.getElementById('user-name');

        if (username === '') {
            alert('Please enter a username.');
            return;
        }

        if (userDetails[username]) {
            if (Object.keys(activeUsers).length > 0) {
                alert('Another user is already logged in. Please log out first.');
                return;
            }

            activeUsers[username] = true;
            document.getElementById('login-container').classList.add('hidden');
            document.getElementById('video-container').classList.remove('hidden');

            const userDetail = userDetails[username];
            videoHeading.innerHTML = 'The Process platform';
            userIcon.src = userDetail.icon;  // Set user's icon
            userName.textContent = userDetail.name;  // Set user's name

            if (['admin.mora', '99', '16840 ', '28411', '15032'].includes(username)) {
                const examItem = document.createElement('li');
                examItem.textContent = 'حل الامتحان';
                examItem.onclick = () => showVideo('examVideo');

const menuList = document.querySelector('#video-menu ul');
                menuList.insertBefore(examItem, menuList.firstChild); // Move "حل الامتحان" to the top           
                }

            // Replace numeric username with a placeholder or masked string
            document.getElementById('username').value = '********'; 
        } else {
            alert('Invalid username');
        }
    }

    function handleEnterKey(event) {
        if (event.key === 'Enter') {
            login();
        }
    }

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


