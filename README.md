# ghostgamezwebsite.github.io


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Locked Safe</title>
<style>
    body {
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #f8f9fa; /* Background color for the entire page */
    }

    .safe-container {
        position: relative;
        width: 250px;
        height: 300px;
        background-color: rgba(0, 0, 0, 0.5); /* Transparent background for the area around the safe */
        backdrop-filter: blur(5px); /* Optional: Adds a blur effect to the background */
        border-radius: 20px;
        padding: 20px;
    }

    .safe {
        width: 100%;
        height: 100%;
        background-color: rgba(51, 51, 51, 0.8); /* Transparent background for the safe */
        border: 2px solid #000;
        border-radius: 20px;
        position: relative;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        overflow: hidden;
        background-image: url('https://cdn.pixabay.com/photo/2014/11/18/23/42/rusty-539486_960_720.jpg');
        background-size: cover;
        background-repeat: no-repeat;
        transition: transform 0.2s;
    }

    .safe-container:hover .safe {
        transform: scale(1.05);
    }

    .dial {
        width: 70px;
        height: 70px;
        background-color: #555;
        border: 2px solid #000;
        border-radius: 50%;
        margin-bottom: 20px;
    }

    .input {
        width: 80%;
        padding: 5px;
        margin-bottom: 10px;
        box-sizing: border-box;
        text-align: center;
    }

    .button {
        padding: 8px 15px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        margin-top: 10px;
    }

    .message {
        color: #ff0000;
        font-size: 14px;
        margin-top: 10px;
    }

    .popup {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) scale(0);
        padding: 20px;
        background-color: #fff;
        border: 2px solid #007bff;
        border-radius: 5px;
        z-index: 1000;
        transition: transform 0.5s;
        text-align: center;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    }

    .popup-button {
        padding: 8px 15px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        margin-top: 10px;
    }

    .safe.unlocked .popup {
        transform: translate(-50%, -50%) scale(1);
    }

    .unlock-button {
        display: none;
    }

    .safe.incorrect {
        animation: explode 1s forwards;
    }

    @keyframes explode {
        0% { transform: scale(1); opacity: 1; }
        50% { transform: scale(1.5); opacity: 0.5; }
        100% { transform: scale(2); opacity: 0; }
    }
</style>
</head>
<body>
    <div class="safe-container">
        <div class="safe">
            <div class="dial"></div>
            <input type="text" class="input" placeholder="Enter code" id="codeInput">
            <button class="button" onclick="checkCode()">Check Code</button>
            <div class="message" id="message"></div>
            <button class="unlock-button" onclick="openAboutBlank()">Ghost Games 3</button>
        </div>
        <div id="popup" class="popup">
            <button class="popup-button" onclick="openGG3()">Ghost Games 3</button>
        </div>
    </div>
    <div id="tryAgainText" style="display:none; color:red; cursor:pointer;" onclick="showSafe()">Try Again Bozo</div>

    <script>
        function checkCode() {
            var codeInput = document.getElementById('codeInput');
            var message = document.getElementById('message');
            var safe = document.querySelector('.safe');
            var popup = document.getElementById('popup');
            var unlockButton = document.querySelector('.unlock-button');
            var tryAgainText = document.getElementById('tryAgainText');

            if (codeInput.value === '6969') {
                message.textContent = 'Safe unlocked!';
                safe.classList.add('unlocked');
                unlockButton.style.display = 'block';
            } else {
                message.textContent = 'Incorrect code. Try again.';
                safe.classList.add('incorrect');
                setTimeout(function() {
                    safe.classList.remove('incorrect');
                    safe.style.display = 'none';
                    tryAgainText.style.display = 'block';
                }, 1000); // Remove the safe after 1 second
            }
        }

        function openAboutBlank() {
            window.open('about:blank', '_blank');
        }

        function openGG3() {
            window.open('https://sites.google.com/online.houstonisd.org/gg3/home', '_blank');
        }

        function showSafe() {
            var safe = document.querySelector('.safe');
            var tryAgainText = document.getElementById('tryAgainText');
            safe.style.display = 'flex';
            tryAgainText.style.display = 'none';
        }
    </script>
</body>
</html>
