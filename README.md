<!DOCTYPE html>
<html lang="el">
<head>
  <meta charset="UTF-8">
  <title>Νέστορας - Προσωπική Σελίδα</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #e8f0fe;
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
      max-width: 800px;
      margin: auto;
    }

    #main-content {
      display: none;
    }

    button {
      padding: 0.7rem 1.5rem;
      font-size: 1rem;
      border-radius: 0.5rem;
      border: none;
      background-color: #007bff;
      color: white;
      cursor: pointer;
      margin: 0.5rem;
      transition: background-color 0.3s;
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

    .panellinies-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 1rem;
    }

    .panellinies-buttons button {
      flex: 1 1 150px;
      background-color: #28a745;
    }

    .panellinies-buttons button:hover {
      background-color: #1e7e34;
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

    <!-- Θέματα Πανελληνίων -->
    <button onclick="togglePanellinies()">Θέματα Πανελληνίων</button>
    <div id="panellinies" class="section" style="display: none;">
      <h3>📄 Θέματα Πανελληνίων</h3>
      <div class="panellinies-buttons">
        <button onclick="window.open('assets/panellinies/2020.pdf')">Θέματα 2020</button>
        <button onclick="window.open('assets/panellinies/2021.pdf')">Θέματα 2021</button>
        <button onclick="window.open('assets/panellinies/2022.pdf')">Θέματα 2022</button>
        <button onclick="window.open('assets/panellinies/2023.pdf')">Θέματα 2023</button>
        <button onclick="window.open('assets/panellinies/2024.pdf')">Θέματα 2024</button>
      </div>
    </div>

  </div>

  <script>
    // Κωδικός πρόσβασης
    window.onload = function() {
      const secretCode = "1234"; // Βάλε εδώ τον δικό σου κωδικό
      const userInput = prompt("Εισάγετε τον κωδικό πρόσβασης:");

      if (userInput === secretCode) {
        document.getElementById("main-content").style.display = "block";
      } else {
        document.body.innerHTML = "<h1>⛔ Πρόσβαση απορρίφθηκε</h1><p>Λάθος κωδικός.</p>";
      }
    };

    function toggleDegrees() {
      const section = document.getElementById("degrees");
      section.style.display = (section.style.display === "none") ? "block" : "none";
    }

    function toggleGrades() {
      const section = document.getElementById("grades");
      section.style.display = (section.style.display === "none") ? "block" : "none";
    }

    function togglePanellinies() {
      const section = document.getElementById("panellinies");
      section.style.display = (section.style.display === "none") ? "block" : "none";
    }
  </script>

</body>
</html>

