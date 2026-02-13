theme: jekyll-theme-minimal
title: ptv-day's homepage
description: Welcome
<html lang="ro">
<head>
  <meta charset="UTF-8" />
  <title>Valentine 💖</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: Arial, sans-serif;
    }

    .card {
      position: relative;
      z-index: 2;
      background: white;
      padding: 30px 40px;
      border-radius: 16px;
      text-align: center;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    }

    h1 {
      margin-bottom: 10px;
    }

    .name {
      color: #e91e63;
      font-weight: bold;
    }

    button {
      padding: 10px 22px;
      font-size: 18px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      margin: 10px;
      transition: transform 0.2s ease;
    }

    #yes {
      background: #4CAF50;
      color: white;
    }

    #no {
      background: #f44336;
      color: white;
      position: absolute;
    }

    #msg {
      margin-top: 15px;
      font-size: 18px;
      color: #e91e63;
    }

    /* Inimioare */
    .heart {
      position: absolute;
      bottom: -20px;
      font-size: 20px;
      animation: floatUp linear forwards;
      opacity: 0.8;
    }

    @keyframes floatUp {
      from {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      to {
        transform: translateY(-110vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Virus,</h1>
    <h2>Petreci cu mine <br> Valentine’s Day? 💘</h2>
    <button id="yes">Yes</button>
    <button id="no">No</button>
    <div id="msg"></div>
  </div>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const msg = document.getElementById("msg");

    let scale = 1;

    // Mută și micșorează butonul "No"
    noBtn.addEventListener("mouseover", () => {
      scale -= 0.1;
      if (scale < 0.3) scale = 0.3;

      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 50);

      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
      noBtn.style.transform = `scale(${scale})`;
    });

    yesBtn.addEventListener("click", () => {
      msg.innerHTML = "Yay! 💖 Abia aștept, Virus! 😍";
    });

    // Creează inimioare animate
    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerText = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (3 + Math.random() * 3) + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 6000);
    }

    setInterval(createHeart, 400);
  </script>
</body>
</html>
