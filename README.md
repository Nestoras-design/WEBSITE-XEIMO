<!DOCTYPE html>
<html lang="el">
<head>
  <meta charset="UTF-8">
  <title>Εγώ</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f0f0f0;
      margin: 0;
      padding: 2rem;
    }
    .profile-img {
      width: 200px;
      border-radius: 50%;
      margin-bottom: 1rem;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }
    .container {
      background-color: white;
      padding: 2rem;
      border-radius: 1rem;
      box-shadow: 0 0 20px rgba(0,0,0,0.1);
      max-width: 700px;
      margin: auto;
    }
    #main-content {
      display: none;
    }
    button {
      padding: 0.5rem 1rem;
      font-size: 1rem;
      border-radius: 0.5rem;
      border: none;
      background-color: #007bff;
      color: white;
      cursor: pointer;
      margin-top: 1rem;
    }
    button:hover {
      background-color: #0056b3;
    }
    .section {
      margin-top: 2rem;
      text-align: left;
    }
    ul {
      list-style-type: square;
      padding-left: 1.5rem;
    }
    .semester {
      margin-top: 1rem;
    }
  </style>
</head>
<body>

  <div class="container" id="main-content">
    <img src="nestoras.png" alt="Η φωτογραφία μου" class="profile-img">
    <h1>Γεια σου! Είμαι ο Νέστορας</h1>
    <p>Αυτή είναι η προσωπική μου σελίδα!</p>

    <!-- Πτυχία -->
    <button onclick="toggleDegrees()">Δες τα πτυχία μου</button>
    <div id="degrees" class="section" style="display: none;">
      <h3>📘 Πτυχία & Πιστοποιήσεις</h3>
      <ul>
        <li>🎓 Πτυχίο Πληροφορικής – Δημοκρίτειο Πανεπιστήμιο Θράκης</li>
        <li>🗣️ Lower ESB – Πιστοποίηση Αγγλικών</li>
        <li>💻 Πιστοποίηση MOOC – Πανεπιστήμιο Πειραιά</li>
      </ul>
    </div>

    <!-- Βαθμοί -->
    <button onclick="toggleGrades()">Βαθμοί</button>
    <div id="grades" class="section" style="display: none;">
      <h3>📊 Βαθμολογία ανά Εξάμηνο</h3>

      <div class="semester">
        <strong>1ο Εξάμηνο</strong>
        <ul>
          <li>Ψηφιακή Σχεδίαση – 8.5</li>
          <li>Μαθηματικά Ι – 7.0</li>
          <li>Θεωρίες Μάθησης – 9.0</li>
        </ul>
      </div>

      <div class="semester">
        <strong>2ο Εξάμηνο</strong>
        <ul>
          <li>Βάσεις Δεδομένων – 8.0</li>
          <li>Μαθηματικά ΙΙ – 6.5</li>
          <li>Οργάνωση Υπολογιστών – 9.2</li>
        </ul>
      </div>

      <div class="semester">
        <strong>3ο Εξάμηνο</strong>
        <ul>
          <li>Προηγμένες εφαρμογές Ψηφιακής σχεδίασης – 7.8</li>
          <li>Λειτουργικά Συστήματα – 8.4</li>
          <li>Αντικειμενοστραφής Προγραμματισμός – 9.5</li>
        </ul>
      </div>

      <div class="semester">
        <strong>4ο Εξάμηνο</strong>
        <ul>
          <li>Αναλογικά Συστήματα – 8.0</li>
          <li>Αντικειμενοστραφής Προγραμματισμός – 8.7</li>
          <li>Τεχνητή Νοημοσύνη – 9.0</li>
        </ul>
      </div>
    </div>
  </div>

  <script>
    // Κωδικός πρόσβασης
    window.onload = function() {
      const secretCode = "1234"; // 🔒 Εδώ βάλε τον δικό σου κωδικό
      const userInput = prompt("Εισάγετε τον κωδικό πρόσβασης:");

      if (userInput === secretCode) {
        document.getElementById("main-content").style.display = "block";
      } else {
        document.body.innerHTML = "<h1>⛔ Πρόσβαση απορρίφθηκε</h1><p>Λάθος κωδικός.</p>";
      }
    };

    // Εναλλαγή Πτυχίων
    function toggleDegrees() {
      const section = document.getElementById("degrees");
      section.style.display = (section.style.display === "none") ? "block" : "none";
    }

    // Εναλλαγή Βαθμών
    function toggleGrades() {
      const section = document.getElementById("grades");
      section.style.display = (section.style.display === "none") ? "block" : "none";
    }
  </script>

</body>
</html>
