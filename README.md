<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Interface</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        .login-container {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            width: 350px;
            text-align: center;
        }

        h1 {
            font-size: 24px;
            color: #333;
            margin-bottom: 20px;
        }

        .input-field {
            position: relative;
            margin-bottom: 15px;
            text-align: left;
        }

        .input-field input {
            width: 100%;
            padding: 10px;
            padding-left: 30px;
            border: 2px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }

        .input-field i {
            position: absolute;
            left: 10px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 18px;
            color: #555;
        }

        .submit-btn {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }

        .submit-btn:hover {
            background-color: #45a049;
        }

        .panel-container {
            display: none;
            background-color: #1e1e1e;
            border-radius: 8px;
            padding: 20px;
            width: 300px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
            color: #fff;
            margin-top: 30px;
            transform: scale(0);
            animation: firework 1s ease-out forwards;
        }

        @keyframes firework {
            0% {
                transform: scale(0);
                opacity: 0;
                filter: blur(10px);
            }
            100% {
                transform: scale(1);
                opacity: 1;
                filter: blur(0);
            }
        }

        .panel-header {
            display: flex;
            justify-content: space-around;
            padding-bottom: 10px;
            border-bottom: 2px solid #444;
            margin-bottom: 15px;
        }

        .panel-header i {
            font-size: 24px;
            color: #ffbc00;
        }

        .panel-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 8px;
            background-color: #2a2a2a;
            border-radius: 4px;
            margin-bottom: 10px;
        }

        .panel-item span {
            font-size: 16px;
            color: #ccc;
        }

        .toggle-switch {
            position: relative;
            width: 40px;
            height: 20px;
            animation: colorCycle 1s infinite alternate;
        }

        .toggle-switch input {
            display: none;
        }

        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #444;
            transition: 0.4s;
            border-radius: 34px;
        }

        .slider:before {
            position: absolute;
            content: "";
            height: 14px;
            width: 14px;
            left: 3px;
            bottom: 3px;
            background-color: white;
            transition: 0.4s;
            border-radius: 50%;
        }

        input:checked + .slider {
            background-color: #ffbc00;
        }

        input:checked + .slider:before {
            transform: translateX(18px);
        }

        @keyframes colorCycle {
            0% {
                background-color: #ff4d4d;
            }
            25% {
                background-color: #4d94ff;
            }
            50% {
                background-color: #4dff7a;
            }
            75% {
                background-color: #ffb84d;
            }
            100% {
                background-color: #ff00ff;
            }
        }
    </style>
</head>
<body>

<!-- Login Form -->
<div class="login-container">
    <h1>Login</h1>
    <div class="input-field">
        <i class="fa fa-user"></i>
        <input type="text" id="username" placeholder="Enter Username" required>
    </div>
    <div class="input-field">
        <i class="fa fa-lock"></i>
        <input type="password" id="password" placeholder="Enter Password" required>
    </div>
    <button class="submit-btn" onclick="login()">Login</button>
</div>

<!-- Panel Content (Visible after login) -->
<div class="panel-container" id="panel">
    <div class="panel-header">
        <i>⚡</i>
        <i>🏠</i>
        <i>⚙️</i>
        <i>🗑️</i>
    </div>

    <div class="panel-content">
        <div class="panel-item">
            <span>AIMBOT</span>
            <label class="toggle-switch">
                <input type="checkbox" onchange="playSoundAndVibrate()">
                <span class="slider"></span>
            </label>
        </div>
        <div class="panel-item">
            <span>NO RECOIL</span>
            <label class="toggle-switch">
                <input type="checkbox" onchange="playSoundAndVibrate()">
                <span class="slider"></span>
            </label>
        </div>
        <div class="panel-item">
            <span>AIMFOV</span>
            <label class="toggle-switch">
                <input type="checkbox" onchange="playSoundAndVibrate()">
                <span class="slider"></span>
            </label>
        </div>
        <div class="panel-item">
            <span>ANTENA</span>
            <label class="toggle-switch">
                <input type="checkbox" onchange="playSoundAndVibrate()">
                <span class="slider"></span>
            </label>
        </div>
        <div class="panel-item">
            <span>AMBLOCK</span>
            <label class="toggle-switch">
                <input type="checkbox" onchange="playSoundAndVibrate()">
                <span class="slider"></span>
            </label>
        </div>
        <div class="panel-item">
            <span>ONLY RED</span>
            <label class="toggle-switch">
                <input type="checkbox" onchange="playSoundAndVibrate()">
                <span class="slider"></span>
            </label>
        </div>
    </div>
</div>

<!-- Sound File -->
<audio id="sound" src="https://www.soundjay.com/button/beep-07.wav"></audio>

<script src="https://kit.fontawesome.com/a076d05399.js"></script>
<script>
    function login() {
        var username = document.getElementById('username').value;
        var password = document.getElementById('password').value;
        
        if (username === "SHIHAB" && password === "12") {
            document.querySelector('.login-container').style.display = 'none';  // Hide login form
            document.getElementById('panel').style.display = 'block';  // Show panel
        } else {
            alert("Incorrect Username or Password");
        }
    }

    function playSoundAndVibrate() {
        var sound = document.getElementById('sound');
        sound.play();

        if (navigator.vibrate) {
            navigator.vibrate(200);  // Vibrate for 200ms
        }
    }
</script>
</body>
</html>
