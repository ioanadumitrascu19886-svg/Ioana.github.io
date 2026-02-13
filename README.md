theme: jekyll-theme-minimal
title: ptv-day's homepage
description: Welcome
<!DOCTYPE html>
<html lang="ro">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Valentine Mini Games 💖</title>
  <style>
    body { font-family: system-ui, Arial, sans-serif; background:#0f1220; color:#fff; margin:0; }
    header { padding:20px; text-align:center; background:linear-gradient(135deg,#ff4d6d,#ff8fab); }
    .wrap { max-width:1000px; margin:0 auto; padding:20px; }
    .grid { display:grid; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); gap:16px; }
    .card { background:#171a2b; border-radius:14px; padding:16px; box-shadow:0 10px 25px rgba(0,0,0,.25); }
    .card h3 { margin:0 0 8px; }
    button { background:#ff4d6d; border:none; color:#fff; padding:10px 14px; border-radius:10px; cursor:pointer; }
    button:hover { opacity:.9; }
    .result { margin-top:10px; padding:10px; background:#0b0e1a; border-radius:10px; min-height:44px; }
    .hearts { display:flex; gap:10px; flex-wrap:wrap; }
    .heart { font-size:28px; cursor:pointer; transition:.2s; }
    .heart:hover { transform: scale(1.2); }
    footer { text-align:center; opacity:.7; padding:20px; }
  </style>
</head>
<body>
  <header>
    <h1>Valentine’s Day – Mini Joculețe 💘</h1>
    <p>Joacă rapid, romantic și fun – fără întrebări.</p>
  </header>

  <div class="wrap">
    <div class="grid">
      <!-- 1) Alege o inimă -->
      <div class="card">
        <h3>❤️ Alege o inimă</h3>
        <div class="hearts" id="hearts"></div>
        <div class="result" id="heartResult">Alege o inimă…</div>
      </div>

      <!-- 2) Roata iubirii -->
      <div class="card">
        <h3>🎡 Roata iubirii</h3>
        <button onclick="spinWheel()">Învârte roata</button>
        <div class="result" id="wheelResult"></div>
      </div>

      <!-- 3) Truth or Dare – doar Dare -->
      <div class="card">
        <h3>🔥 Dare (provocări)</h3>
        <button onclick="getDare()">Provocare</button>
        <div class="result" id="dareResult"></div>
      </div>

      <!-- 4) Love Dice -->
      <div class="card">
        <h3>🎲 Love Dice</h3>
        <button onclick="rollDice()">Dă cu zarul</button>
        <div class="result" id="diceResult"></div>
      </div>
    </div>
  </div>

  <footer>Făcut cu drag 💖</footer>

  <script>
    // 1) Alege o inimă
    const heartPrizes = [
      "Pupic 💋",
      "Îmbrățișare 30 sec 🤗",
      "Masaj 1 minut 💆‍♂️",
      "Selfie împreună 📸",
      "Surpriză dulce 🍬"
    ];
    const heartsEl = document.getElementById("hearts");
    const heartResult = document.getElementById("heartResult");
    for (let i = 0; i < 5; i++) {
      const span = document.createElement("span");
      span.className = "heart";
      span.textContent = "❤️";
      span.onclick = () => {
        const pick = heartPrizes[Math.floor(Math.random()*heartPrizes.length)];
        heartResult.textContent = "Ai nimerit: " + pick;
      };
      heartsEl.appendChild(span);
    }

    // 2) Roata iubirii
    const wheel = ["Pupic", "Îmbrățișare", "Dans 30 sec", "Compliment", "Masaj scurt"];
    function spinWheel() {
      const pick = wheel[Math.floor(Math.random()*wheel.length)];
      document.getElementById("wheelResult").textContent = "Roata a ales: " + pick + " 💖";
    }

    // 3) Dare only
    const dares = [
      "Ține-mă de mână 1 minut",
      "Spune ceva drăguț",
      "Îmbrățișează-mă",
      "Pupic pe frunte",
      "Fă o poză drăguță cu noi"
    ];
    function getDare() {
      const pick = dares[Math.floor(Math.random()*dares.length)];
      document.getElementById("dareResult").textContent = pick + " 😏";
    }

    // 4) Love Dice
    const dice = ["Pupic", "Îmbrățișare", "Mângâiere", "Dans", "Compliment", "Tu alegi 😏"];
    function rollDice() {
      const pick = dice[Math.floor(Math.random()*dice.length)];
      document.getElementById("diceResult").textContent = "A ieșit: " + pick;
    }
  </script>
</body>
</html>
