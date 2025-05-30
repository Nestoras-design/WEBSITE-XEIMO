<!DOCTYPE html>
<html lang="el">
<head>
  <meta charset="UTF-8" />
  <title>Εγώ</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f0f0;
      margin: 0;
      padding: 2rem;
      text-align: center;
    }
    .container {
      background-color: white;
      padding: 2rem;
      border-radius: 1rem;
      box-shadow: 0 0 20px rgba(0,0,0,0.1);
      max-width: 700px;
      margin: auto;
      position: relative;
    }
    .profile-img {
      width: 200px;
      border-radius: 50%;
      margin-bottom: 1rem;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }

    /* ΝΕΟ ΣΤΥΛ ΡΟΛΟΓΙΟΥ */
    #live-clock {
      position: absolute;
      top: 1rem;
      left: 1rem;
      font-size: 1rem;
      background: rgba(0, 123, 255, 0.1);
      color: #007bff;
      padding: 0.3rem 0.6rem;
      border-radius: 0.5rem;
      font-family: 'Courier New', monospace;
      letter-spacing: 2px;
      box-shadow: none;
      z-index: 1000;
    }

    .social-media {
      margin-top: 3rem;
    }
    .social-media button {
      background-color: #3b5998;
      color: white;
      font-size: 1.1rem;
      padding: 0.7rem 1.5rem;
      border-radius: 0.5rem;
      border: none;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    .social-media button:hover {
      background-color: #2d4373;
    }

    .menu-button {
      position: absolute;
      top: 1rem;
      right: 1rem;
      width: 50px;
      height: 50px;
      border: 2px solid #007bff;
      background-color: white;
      border-radius: 0.5rem;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }
    .menu-button div {
      width: 30px;
      height: 3px;
      background-color: #007bff;
      margin: 4px 0;
    }
    .menu {
      display: none;
      position: absolute;
      top: 70px;
      right: 1rem;
      background: white;
      border: 2px solid #007bff;
      border-radius: 0.5rem;
      box-shadow: 0 4px 12px rgba(0,123,255,0.2);
      z-index: 999;
    }
    .menu button {
      display: block;
      background: none;
      border: none;
      padding: 0.8rem 1rem;
      cursor: pointer;
      font-size: 1rem;
      color: #007bff;
      text-align: left;
      width: 100%;
    }
    .menu button:hover {
      background-color: #f0f8ff;
    }
    .section {
      display: none;
      margin-top: 2rem;
      text-align: left;
    }
    ul {
      list-style-type: square;
      padding-left: 1.5rem;
    }
  </style>
</head>
<body>

<!-- Το ρολόι πλέον είναι έξω από το container και πάνω αριστερά -->
<div id="live-clock">--:--:--</div>

<div class="container">
  <div class="menu-button" onclick="toggleMenu()">
    <div></div>
    <div></div>
    <div></div>
  </div>

  <div class="menu" id="menu">
    <button onclick="showSection('degrees')">Πτυχία</button>
    <button onclick="showSection('grades')">Βαθμοί</button>
    <button onclick="showSection('panellinies')">Θέματα Πανελληνίων</button>
    <button onclick="showSection('quiz')">Quiz</button>
  </div>

  <img src="nestoras.png" alt="Η φωτογραφία μου" class="profile-img">
  <h1>Γεια σου! Είμαι ο Νέστορας</h1>
  <p>Αυτή είναι η προσωπική μου σελίδα!</p>

  <div id="degrees" class="section">
    <h3>📘 Πτυχία & Πιστοποιήσεις</h3>
    <ul>
      <li>🎓 Πτυχίο Πληροφορικής – ΔΠΘ</li>
      <li>🗣️ Lower ESB – Αγγλικά</li>
      <li>💻 MOOC – Παν. Καναδά</li>
    </ul>
  </div>

  <div id="grades" class="section">
    <h3>📊 Βαθμολογία ανά Εξάμηνο</h3>
    <!-- περιεχόμενο εξαμήνων -->
  </div>

  <div id="panellinies" class="section">
    <button onclick="openPDF('2020')">2020</button>
    <button onclick="openPDF('2021')">2021</button>
    <button onclick="openPDF('2022')">2022</button>
    <button onclick="openPDF('2023')">2023</button>
    <button onclick="openPDF('2024')">2024</button>
  </div>

  <div id="quiz" class="section">
    <h3>🧠 Quiz Πληροφορικής Γ' Λυκείου</h3>
    <div id="quiz-container"></div>
    <div id="score"></div>
  </div>

  <div class="social-media">
    <h3>Το Facebook μου</h3>
    <button onclick="window.open('https://www.facebook.com/ntinanwntas.xeimwnopoylos/?locale=el_GR')">
      Facebook
    </button>
  </div>
</div>

<script>
  function updateClock() {
    const now = new Date();
    let h = now.getHours().toString().padStart(2, '0');
    let m = now.getMinutes().toString().padStart(2, '0');
    let s = now.getSeconds().toString().padStart(2, '0');
    document.getElementById('live-clock').textContent = `${h}:${m}:${s}`;
  }
  updateClock();
  setInterval(updateClock, 1000);

  function toggleMenu() {
    const menu = document.getElementById("menu");
    menu.style.display = (menu.style.display === "block") ? "none" : "block";
  }

  function showSection(id) {
    ['degrees', 'grades', 'panellinies', 'quiz'].forEach(section => {
      document.getElementById(section).style.display = (section === id) ? "block" : "none";
    });
    document.getElementById("menu").style.display = "none";
  }

  function openPDF(year) {
    window.open(`assets/panellinies/${year}.pdf`, '_blank');
  }

  const questions = [
    { q: "Η μεταβλητή μπορεί να έχει πολλαπλές τιμές ταυτόχρονα.", a: false },
    { q: "Ο αλγόριθμος πρέπει να έχει περατότητα.", a: true },
    { q: "Η εντολή 'ΓΡΑΨΕ' χρησιμοποιείται για έξοδο δεδομένων.", a: true },
    { q: "Το διάγραμμα ροής δεν χρησιμοποιεί ρόμβους.", a: false },
    { q: "Η αναδρομή είναι τεχνική επανάληψης.", a: true },
    { q: "Η στοίβα λειτουργεί με τη μέθοδο FIFO.", a: false },
    { q: "Ο πίνακας είναι μια δομή δεδομένων.", a: true },
    { q: "Η επιλογή είναι μια μορφή επανάληψης.", a: false },
   { q: "Η μεταγλώττιση εκτελεί άμεσα τον κώδικα.", a: false },
   { q: "Η ψευδογλώσσα είναι αυστηρά ορισμένη γλώσσα.", a: true },
  ];
  let currentQ = 0;
  let score = 0;

  function loadQuiz() {
    const container = document.getElementById("quiz-container");
    const scoreDiv = document.getElementById("score");
    if (currentQ < questions.length) {
      const q = questions[currentQ];
      container.innerHTML = `
        <p><strong>Ερώτηση ${currentQ + 1}:</strong> ${q.q}</p>
        <button onclick="answer(true)">Σωστό</button>
        <button onclick="answer(false)">Λάθος</button>
      `;
      scoreDiv.textContent = "";
    } else {
      container.innerHTML = "";
      scoreDiv.innerHTML = `<h4>Τελικό σκορ: ${score} / 10</h4>`;
      currentQ = 0;
      score = 0;
    }
  }

  function answer(ans) {
    if (questions[currentQ].a === ans) score++;
    currentQ++;
    loadQuiz();
  }

  document.querySelector("button[onclick=\"showSection('quiz')\"]").addEventListener("click", loadQuiz);
</script>
</body>
</html>
