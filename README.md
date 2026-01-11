[index.html](https://github.com/user-attachments/files/24551467/index.html)
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Startseite</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      min-height: 100vh;
      background: linear-gradient(135deg, #1d2671, #c33764);
      display: flex;
      justify-content: center;
      align-items: center;
      color: #fff;
    }

    .container {
      width: 95%;
      max-width: 1000px;
    }

    h1 {
      text-align: center;
      margin-bottom: 30px;
      font-size: 2.5rem;
    }

    .menu {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      grid-auto-rows: 1fr;
      gap: 20px;
    }

    .card {
      position: relative;
      background: rgba(255, 255, 255, 0.15);
      border-radius: 16px;
      padding: 25px;
      text-align: center;
      cursor: pointer;
      transition: transform 0.3s, background 0.3s, box-shadow 0.3s;
      display: flex;
      flex-direction: column;
      justify-content: center;
      min-height: 180px;
    }

    .card:hover {
      transform: translateY(-8px);
      background: rgba(255, 255, 255, 0.25);
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
    }

    .card h2 {
      margin-bottom: 10px;
    }

    .card p {
      opacity: 0.9;
    }

    /* ❓ Fragezeichen */
    .help-icon {
      position: absolute;
      top: 12px;
      right: 12px;
      width: 28px;
      height: 28px;
      border-radius: 50%;
      background: rgba(0,0,0,0.5);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      cursor: pointer;
    }

    /* 🏗 In Bearbeitung */
    .card.construction {
      cursor: not-allowed;
      background: repeating-linear-gradient(
        45deg,
        rgba(255, 200, 0, 0.18),
        rgba(255, 200, 0, 0.18) 10px,
        rgba(0, 0, 0, 0.25) 10px,
        rgba(0, 0, 0, 0.25) 20px
      );
      border: 2px dashed rgba(255, 200, 0, 0.6);
    }

    .card.construction:hover {
      transform: none;
      box-shadow: none;
    }

    .construction-icon {
      font-size: 2.2rem;
      margin-bottom: 12px;
    }

    .construction-label {
      margin-top: 10px;
      font-size: 0.85rem;
      letter-spacing: 1px;
      opacity: 0.85;
    }

    /* Overlay */
    .overlay {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.6);
      display: none;
      justify-content: center;
      align-items: center;
      z-index: 2000;
    }

    .overlay.active {
      display: flex;
    }

    .info-box {
      background: #1e1e2f;
      padding: 25px;
      border-radius: 16px;
      max-width: 420px;
      width: 90%;
      text-align: center;
      box-shadow: 0 15px 40px rgba(0,0,0,0.5);
    }

    .info-box h3 {
      margin-bottom: 15px;
    }

    .info-box button {
      margin-top: 20px;
      padding: 10px 16px;
      border: none;
      border-radius: 8px;
      background: #ffffff22;
      color: white;
      cursor: pointer;
    }

    /* Hamburger */
    .hamburger {
      position: fixed;
      top: 20px;
      right: 20px;
      width: 30px;
      cursor: pointer;
      z-index: 1001;
    }

    .chillig-glow {
  color: #4dffb2;
  text-shadow: 0 0 8px #4dffb2, 0 0 18px #4dffb2;
  font-weight: bold;
}

.mid-glow {
  color: #ffd24d;
  text-shadow: 0 0 8px #ffd24d, 0 0 18px #ffd24d;
  font-weight: bold;
}

.cooked-glow {
  color: #ff5c5c;
  text-shadow: 0 0 8px #ff5c5c, 0 0 18px #ff5c5c;
  font-weight: bold;
}


    .hamburger span {
      display: block;
      height: 4px;
      background: white;
      margin: 6px 0;
      border-radius: 4px;
    }

    .side-menu {
      position: fixed;
      top: 0;
      right: -280px;
      width: 260px;
      height: 100vh;
      background: rgba(0,0,0,0.9);
      padding: 30px 20px;
      transition: right 0.4s ease;
      z-index: 1000;
    }

    .side-menu.active {
      right: 0;
    }

    .explain-separator {
  border: none;
  height: 1px;
  background: rgba(255,255,255,0.25);
  margin: 10px 0;
}

.extra-mode {
  color: #ff9f43;
  text-shadow: 0 0 10px #ff9f43, 0 0 20px #ff9f43;
  font-weight: bold;
}


    .back-bar {
      margin-top: auto;
      padding: 14px;
      text-align: center;
      background: #ffffff22;
      border-radius: 10px;
      cursor: pointer;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <div class="hamburger" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </div>

  <div id="sideMenu" class="side-menu">
    <h2>⚙ Optionen</h2>
    <div class="back-bar" onclick="toggleMenu()">Menü schliessen</div>
  </div>

  <div class="container">
    <h1>Meine Spiele & Apps</h1>

    <div class="menu">

      <!-- SPIEL -->
      <div class="card" onclick="location.href='spiele/spiel1.html'">
        <div class="help-icon" onclick="openInfo(event)">?</div>
        <h2>1–10</h2>
        <p>Wer wird Cooked?</p>
      </div>

      <!-- IN BEARBEITUNG -->
      <div class="card construction">
        <div class="construction-icon">🚧</div>
        <h2>In Bearbeitung</h2>
        <p>Hier entsteht etwas Neues</p>
        <div class="construction-label">COMING SOON</div>
      </div>

    </div>
  </div>

  <div id="overlay" class="overlay">
    <div class="info-box">
      <h3>Spiel-Erklärung</h3>

      <!-- 🔽 TEXT HIER ÄNDERN 🔽 -->
<p>
  In diesem Spiel geht es darum, wer eine <strong>Pflichtaufgabe</strong> bekommt,
  die am Ende auch erledigt werden muss.<br><br>

  Wer diese Person ist, wird durch ein <strong>Zufallsprinzip</strong> bestimmt.
  Später sieht die ausgewählte Person ihre Pflichtaufgabe
  und es wird <strong>erneut zufällig</strong> entschieden,
  ob sie diese Aufgabe wirklich machen muss.<br><br>

  Dabei gilt:<br><br>

  <span class="chillig-glow">Chillig</span> → hohe Chance, es machen zu müssen  
  <br>(1 zu 5)<br><br>

  <span class="mid-glow">Mid</span> → mittlere Chance  
  <br>(1 zu 7)<br><br>

  <span class="cooked-glow">Cooked</span> → niedrige Chance, es machen zu müssen  
  <br>(1 zu 10)<br><br>

  <hr class="explain-separator"><br>

  <strong class="extra-mode">🔥 Extra spannend</strong><br><br>

  In diesem Modus müssen die <strong>anderen Spieler erraten</strong>,
  welche Pflichtaufgabe der Auserwählte erhalten hat.<br><br>

  👉 <strong>Schaffen sie es</strong>, die Aufgabe richtig zu erraten,
  muss der Auserwählte <strong>erneut das Zufallsprinzip</strong> nutzen
  und bekommt eine <strong>neue Aufgabe</strong>.
</p>


      <!-- 🔼 TEXT HIER ÄNDERN 🔼 -->

      <button onclick="closeInfo()">Schliessen</button>
    </div>
  </div>

  <script>
    function toggleMenu() {
      document.getElementById("sideMenu").classList.toggle("active");
    }

    function openInfo(event) {
      event.stopPropagation();
      document.getElementById("overlay").classList.add("active");
    }

    function closeInfo() {
      document.getElementById("overlay").classList.remove("active");
    }
  </script>

</body>
</html>
