<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Surprise</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
  <style>
    /* Basic Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(to top right, #FF5733, #FF3A1D);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
    color: #fff;
    text-align: center;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
}

.card {
    background-color: rgba(255, 255, 255, 0.1);
    padding: 40px;
    border-radius: 20px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
    max-width: 400px;
    width: 100%;
    backdrop-filter: blur(8px);
    transition: transform 0.3s ease;
}

.card:hover {
    transform: scale(1.05);
}

.title {
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 20px;
}

.input {
    padding: 12px 18px;
    margin: 12px 0;
    font-size: 16px;
    border: 1px solid #FFD700;
    border-radius: 8px;
    width: 100%;
    color: #fff;
    background: transparent;
}

.secret-btn {
    margin-top: 20px;
    padding: 12px 20px;
    background-color: #FFD700;
    border: none;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
    opacity: 0.7;
}

.secret-btn:hover {
    opacity: 1;
    background-color: #FF5733;
}

.video-container {
    display: none;
    margin-top: 30px;
    padding: 20px;
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.message {
    margin-top: 20px;
    font-size: 22px;
    font-weight: 500;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
}
  </style>
</head>
<body>
    <div class="container">
        <div class="card">
            <h1 class="title">🎉 Happy Birthday [Friend's Name]! 🎂</h1>
            <input type="text" id="name" class="input" placeholder="Enter your name...">
            <button onclick="generateMessage()" class="btn">Surprise Me!</button>
            <p id="birthdayMessage" class="message"></p>
            <button id="secretButton" class="secret-btn" onclick="showSpecialGift()">Uncover Surprise 🎁</button>
        </div>
        <div id="videoContainer" class="video-container"></div>
    </div>
    <script>
      function generateMessage() {
    const name = document.getElementById('name').value;
    const birthdayMessage = document.getElementById('birthdayMessage');

    if (name === '') {
        birthdayMessage.textContent = 'Please enter your name!';
        birthdayMessage.style.opacity = '1';
        return;
    }

    const messages = [
        `Happy Birthday, ${name}! 🎉🎂`,
        `May your day be filled with joy, ${name}! 🎁`,
        `Wishing you a fabulous year ahead, ${name}! 🥳`,
        `Cheers to another awesome year, ${name}! 🎉`
    ];

    const randomMessage = messages[Math.floor(Math.random() * messages.length)];
    birthdayMessage.textContent = randomMessage;
    birthdayMessage.style.opacity = '1';
}

// Show Special Gift (Hidden Video)
function showSpecialGift() {
    const videoContainer = document.getElementById('videoContainer');
    const video = document.createElement('video');
    video.src = 'your-video-link.mp4'; // Replace with your custom birthday video link
    video.controls = true;
    video.autoplay = true;
    video.classList.add('video');
    videoContainer.appendChild(video);
    videoContainer.style.display = 'block'; // Show the video container
    document.getElementById('secretButton').style.display = 'none'; // Hide the secret button after revealing
}
    </script>
</body>
</html>
