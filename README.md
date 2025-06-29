<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Global Server Access</title>
  <style>
    body {
      margin: 0;
      background-color: black;
      color: #00ff00;
      font-family: monospace;
      overflow: hidden;
    }

    .matrix-bg {
      position: fixed;
      width: 100%;
      height: 100%;
      z-index: -1;
      overflow: hidden;
    }

    canvas {
      display: block;
    }

    .content {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      z-index: 1;
    }

    .content h1 {
      font-size: 3rem;
      margin-bottom: 20px;
    }

    .content p {
      font-size: 1.2rem;
    }

    .form {
      margin-top: 20px;
    }

    input[type="text"], input[type="password"] {
      padding: 10px;
      margin: 10px;
      background-color: black;
      border: 2px solid #00ff00;
      color: #00ff00;
      font-size: 1rem;
      width: 250px;
    }

    .portal-btn {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: transparent;
      border: 2px solid #00ff00;
      color: #00ff00;
      font-size: 1rem;
      cursor: pointer;
    }

    .portal-btn:hover {
      background-color: #00ff00;
      color: black;
    }

    .progress {
      margin-top: 20px;
      font-size: 1.2rem;
    }

    .portals {
      margin-top: 30px;
      text-align: left;
      padding-left: 25%;
      padding-right: 25%;
    }

    .portals h3 {
      color: #00ff00;
    }

    .portals input {
      width: 100%;
      margin: 5px 0;
      padding: 10px;
      background: black;
      color: #00ff00;
      border: 1px solid #00ff00;
    }
  </style>
</head>
<body>
  <div class="matrix-bg">
    <canvas id="matrixCanvas"></canvas>
  </div>

  <div class="content">
    <p>Welcome to the encrypted portal for cross-chain blockchain ops and global server configuration. Enter Access.</p>

    <div class="form">
      <input type="text" placeholder="Enter 6 Digit Bank Access Code" maxlength="6"><br/>
      <input type="password" placeholder="Enter 4 Digit Authentication Pin" maxlength="4"><br/>
      <button class="portal-btn" onclick="showProgress()">Access Console</button>
    </div>

    <div class="progress" id="progressText"></div>

    <div class="portals" id="portals" style="display:none;">
      <h3>1.) Global Database Accounts for Visa</h3>
      <h3>2.) Global Database Accounts for Mastercard</h3>
      <h3>3.) Global Database Accounts for American Express</h3>
      <h3>4.) Loader Portal - Reload Visa, Mastercard, AMEX</h3>

      <input type="text" placeholder="Account Name">
      <input type="text" placeholder="Account Number">
      <input type="text" placeholder="Card Number">
      <input type="text" placeholder="Expiration (MM/YY)">
      <input type="text" placeholder="CVC">
      <input type="text" placeholder="Location">
      <input type="text" value="Balance: $900,000,000,000,000 USD" readonly>
    </div>
  </div>

  <script>
    // Falling letters
    const canvas = document.getElementById('matrixCanvas');
    const ctx = canvas.getContext('2d');

    canvas.height = window.innerHeight;
    canvas.width = window.innerWidth;

    let matrix = "ABCDEFGHIJKLMNOPQRSTUVWXYZ123456789@#$%^&*()*&^%".split("");
    let fontSize = 18;
    let columns = canvas.width / fontSize;

    let drops = [];
    for (let x = 0; x < columns; x++) drops[x] = 1;

    function drawMatrix() {
      ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = "#00FF00";
      ctx.font = fontSize + "px monospace";

      for (let i = 0; i < drops.length; i++) {
        let text = matrix[Math.floor(Math.random() * matrix.length)];
        ctx.fillText(text, i * fontSize, drops[i] * fontSize);
        if (drops[i] * fontSize > canvas.height && Math.random() > 0.975)
          drops[i] = 0;
        drops[i]++;
      }
    }

    setInterval(drawMatrix, 33);

    // Progress simulation
    function showProgress() {
      let progress = 0;
      let progressText = document.getElementById("progressText");
      let interval = setInterval(() => {
        progress += 2;
        progressText.textContent = `Processing: ${progress}%`;
        if (progress >= 100) {
          clearInterval(interval);
          progressText.textContent = "WELCOME BACK TETSUJIN! YOU ARE NOW CONNECTED TO THE GLOBAL BANKING SYSTEM. YOUR LAST LOG IN DATE WAS 65 MONTHS AND 24 DAYS AGO.";
          document.getElementById("portals").style.display = "block";
        }
      }, 100);
    }
  </script>
</body>
</html>
