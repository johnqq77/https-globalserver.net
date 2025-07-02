
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

    .content, .features-slide {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      z-index: 1;
      width: 80%;
      max-width: 800px;
    }

    .form input {
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
      padding-left: 5%;
      padding-right: 5%;
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

    .features-slide {
      display: none;
      color: #00ff00;
      font-size: 1.1rem;
      line-height: 2;
      text-align: left;
    }

    .features-slide ul {
      list-style: none;
      padding-left: 0;
    }

    .features-slide ul li::before {
      content: "✅ ";
      color: #00ff00;
    }

    .feature-options ul {
      list-style: none;
      margin-top: 20px;
    }

    .feature-options ul li::before {
      content: "🔹 ";
    }
  </style>
</head>
<body>
  <div class="matrix-bg">
    <canvas id="matrixCanvas"></canvas>
  </div>

  <div class="content" id="loginSlide">
    <p>Welcome to the encrypted portal for cross-chain blockchain ops and global server configuration. Enter Access.</p>

    <div class="form">
      <input type="text" id="accessCode" placeholder="Enter 6 Digit Bank Access Code" maxlength="6" />
      <input type="password" id="authPin" placeholder="Enter 4 Digit Authentication Pin" maxlength="4" />
      <button class="portal-btn" onclick="startAccess()">Access Console</button>
    </div>

    <div class="progress" id="progressText"></div>
  </div>

  <div class="features-slide" id="featureSlide">
    <h2>✅ Features Included:</h2>
    <ul>
      <li>Fullscreen matrix-style background with green falling letters</li>
      <li>Console-style input form with glowing green border</li>
      <li>Access console with progress bar simulation</li>
      <li>After 100%, shows portals and fields</li>
      <li>All CSS and logic included in one file, production-ready</li>
    </ul>

    <div class="feature-options">
      <p>Let me know if you want to:</p>
      <ul>
        <li>🔴 Make the letters red instead of green</li>
        <li>🌐 Deploy it to your custom domain (GitHub Pages or Vercel)</li>
        <li>🎨 Add a student story, watermark, or audio background</li>
      </ul>
    </div>
  </div>

  <script>
    // Falling matrix background
    const canvas = document.getElementById('matrixCanvas');
    const ctx = canvas.getContext('2d');
    canvas.height = window.innerHeight;
    canvas.width = window.innerWidth;
    const matrix = "ABCDEFGHIJKLMNOPQRSTUVWXYZ123456789@#$%^&*()*&^%".split("");
    const fontSize = 18;
    const columns = canvas.width / fontSize;
    const drops = Array.from({ length: columns }).map(() => 1);

    function drawMatrix() {
      ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
      ctx.fillRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = "#00FF00";
      ctx.font = fontSize + "px monospace";

      for (let i = 0; i < drops.length; i++) {
        const text = matrix[Math.floor(Math.random() * matrix.length)];
        ctx.fillText(text, i * fontSize, drops[i] * fontSize);
        if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) drops[i] = 0;
        drops[i]++;
      }
    }

    setInterval(drawMatrix, 33);

    // Access logic
    function startAccess() {
      const access = document.getElementById('accessCode').value.trim();
      const pin = document.getElementById('authPin').value.trim();
      const progressText = document.getElementById("progressText");

      if (access.length === 6 && pin.length === 4) {
        let progress = 0;
        const interval = setInterval(() => {
          progress += 2;
          progressText.textContent = `Processing: ${progress}%`;
          if (progress >= 100) {
            clearInterval(interval);
            transitionToFeatureSlide();
          }
        }, 100);
      } else {
        alert("Please enter a 6-digit access code and 4-digit pin.");
      }
    }

    function transitionToFeatureSlide() {
      document.getElementById("loginSlide").style.display = "none";
      document.getElementById("featureSlide").style.display = "block";
    }

    // Trigger with Enter key
    document.addEventListener("keydown", function (e) {
      if (e.key === "Enter") startAccess();
🔒 Security Center
🔐 IP Mask: Enabled
🛰️ IP Trace: Rerouted via Asia Pacific Node
📡 Node Sync: 99.998% Operational
🕵️‍♂️ Cloaking: Active
🔁 OTP Code (Simulated): 372835
⏱️ Global Time Sync
7/2/2025, 4:53:41 PM
📍 Pacific Bank Grid Time
📡 Transaction Log Feed
[$4,000,000 withdrawn] [Ford BGC Taguig] [Date: 2020-01-04] [Status: Verified]
[$3,750,000 sent] [To: Hong Kong Reserve] [Date: 2020-01-03] [Status: Verified]
[$1,250,000 received] [From: Swiss Vault] [Date: 2020-01-02] [Status: Logged]
[$9,000,000 sent] [To: London Capital Pool] [Date: 2020-01-01] [Status: Cleared]
[$6,500,000 received] [From: Tokyo Exchange] [Date: 2019-12-28] [Status: Settled]
[$5,200,000 sent] [To: Cayman Holdings] [Date: 2019-12-25] [Status: Finalized]
[$4,500,000 received] [From: Berlin Proxy Node] [Date: 2019-12-21] [Status: Verified]
[$2,700,000 sent] [To: Abu Dhabi Treasury] [Date: 2019-12-18] [Status: Confirmed]
[$3,800,000 received] [From: Qatar Finance] [Date: 2019-12-15] [Status: Recorded]
[$1,300,000 sent] [To: BVI Gateway] [Date: 2019-12-12] [Status: Complete]

[$1,000,000 sent] [Destination: Panama] [Status: Encrypted]
[$500,000 received] [From: Cayman Vaults] [Status: Verified]
[$8,500,000 sent] [Destination: Malta] [Status: Processing]
[$250,000 received] [From: Zurich Node 22] [Status: Secured]
  
📥 Download Transaction History
💻 CryptoHost Bridge
Connected to BTCnet: node54.cryptohost.global

Bridge Status: LIVE

📈 System Sync & Uptime
Flow Rate: 842 tx/min
Data Load Latency: 15ms
Global Sync Uptime: 99.998%
    
    
    
    
    
    });
  </script>
</body>
</html>
