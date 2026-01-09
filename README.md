<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>recrutement.f2kmultiservice</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f4f6f8;
  color: #333;
}

header {
  background: #8b0000;
  color: white;
  padding: 50px 20px;
  text-align: center;
}

.lang button {
  margin: 5px;
  padding: 6px 12px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

section {
  max-width: 1000px;
  margin: auto;
  padding: 40px 20px;
}

h2 {
  color: #8b0000;
}

.card, form {
  background: white;
  padding: 25px;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.08);
  margin-bottom: 25px;
}

input, textarea {
  width: 100%;
  padding: 10px;
  margin-bottom: 12px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

button.submit {
  width: 100%;
  padding: 12px;
  background: #8b0000;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

footer {
  background: #222;
  color: white;
  text-align: center;
  padding: 25px;
}

/* Boutons flottants */
.whatsapp, .facebook {
  position: fixed;
  right: 20px;
  color: white;
  padding: 14px 16px;
  border-radius: 50%;
  text-decoration: none;
  font-size: 20px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.3);
}

.whatsapp {
  bottom: 20px;
  background: #25D366;
}

.facebook {
  bottom: 80px;
  background: #1877F2;
}
</style>
</head>

<body>

<header>
  <h1>recrutement.f2kmultiservice</h1>
  <p id="subtitle">Recrutement international d’ambassadeurs</p>
  <div class="lang">
    <button onclick="setLang('fr')">FR</button>
    <button onclick="setLang('en')">EN</button>
  </div>
</header>

<section>
  <h2 id="aboutTitle">À propos</h2>
  <div class="card">
    <p id="aboutText">
      F2K MULTISERVICE recrute des ambassadeurs et ambassadrices dans le monde entier
      pour promouvoir ses services digitaux et administratifs.
    </p>
  </div>
</section>

<section>
  <h2 id="jobTitle">Offre – Ambassadeur</h2>
  <div class="card">
    <ul id="jobList">
      <li>🌍 Recrutement mondial</li>
      <li>💼 Travail flexible</li>
      <li>💰 Paiement à la commission</li>
      <li>📈 Nombre illimité</li>
    </ul>
  </div>
</section>

<section>
  <h2 id="applyTitle">Postuler maintenant</h2>

  <form onsubmit="sendEmail(event)">
    <input type="text" id="name" placeholder="Nom complet" required>
    <input type="email" id="email" placeholder="Adresse email" required>
    <input type="text" id="country" placeholder="Pays" required>
    <textarea id="motivation" placeholder="Votre motivation" required></textarea>

    <button class="submit" type="submit" id="submitBtn">
      Envoyer ma candidature
    </button>
  </form>
</section>

<footer>
  <p>© 2026 F2K MULTISERVICE</p>
</footer>

<!-- Boutons flottants -->
<a class="facebook" href="https://www.facebook.com/TOURNEVISboy" target="_blank">f</a>
<a class="whatsapp" href="#" onclick="openWhatsApp()">💬</a>

<script>
const texts = {
  fr: {
    subtitle: "Recrutement international d’ambassadeurs",
    aboutTitle: "À propos",
    aboutText: "F2K MULTISERVICE recrute des ambassadeurs et ambassadrices dans le monde entier pour promouvoir ses services.",
    jobTitle: "Offre – Ambassadeur",
    jobList: `
      <li>🌍 Recrutement mondial</li>
      <li>💼 Travail flexible</li>
      <li>💰 Paiement à la commission</li>
      <li>📈 Nombre illimité</li>
    `,
    applyTitle: "Postuler maintenant",
    submitBtn: "Envoyer ma candidature"
  },
  en: {
    subtitle: "International Ambassador Recruitment",
    aboutTitle: "About Us",
    aboutText: "F2K MULTISERVICE is recruiting ambassadors worldwide to promote its services.",
    jobTitle: "Ambassador Position",
    jobList: `
      <li>🌍 Worldwide recruitment</li>
      <li>💼 Flexible work</li>
      <li>💰 Commission-based payment</li>
      <li>📈 Unlimited positions</li>
    `,
    applyTitle: "Apply Now",
    submitBtn: "Send Application"
  }
};

function setLang(lang) {
  document.getElementById("subtitle").innerText = texts[lang].subtitle;
  document.getElementById("aboutTitle").innerText = texts[lang].aboutTitle;
  document.getElementById("aboutText").innerText = texts[lang].aboutText;
  document.getElementById("jobTitle").innerText = texts[lang].jobTitle;
  document.getElementById("jobList").innerHTML = texts[lang].jobList;
  document.getElementById("applyTitle").innerText = texts[lang].applyTitle;
  document.getElementById("submitBtn").innerText = texts[lang].submitBtn;
}

function sendEmail(e) {
  e.preventDefault();
  const name = document.getElementById("name").value;
  const email = document.getElementById("email").value;
  const country = document.getElementById("country").value;
  const motivation = document.getElementById("motivation").value;

  const subject = encodeURIComponent("Candidature Ambassadeur – F2K MULTISERVICE");
  const body = encodeURIComponent(
    "Nom : " + name +
    "\nEmail : " + email +
    "\nPays : " + country +
    "\n\nMotivation :\n" + motivation
  );

  window.location.href =
    "mailto:f2kservice@gmail.com?subject=" + subject + "&body=" + body;
}

function openWhatsApp() {
  const country = document.getElementById("country")?.value || "Non précisé";
  const message =
    "Bonjour, je souhaite devenir ambassadeur/ambassadrice de F2K MULTISERVICE.%0A" +
    "Pays : " + country;

  window.open(
    "https://wa.me/22958070708?text=" + message,
    "_blank"
  );
}
</script>

</body>
</html>
