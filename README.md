
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Voltige Juan - Boutique de Chaussettes</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@700&family=Roboto&display=swap');

  body {
    font-family: 'Roboto', Arial, sans-serif;
    margin: 0;
    background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
    color: #222;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }
  header {
    background: #0d47a1;
    padding: 15px 30px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  }
  .logo {
    display: flex;
    align-items: center;
    color: white;
    font-family: 'Orbitron', sans-serif;
    font-size: 28px;
    font-weight: 900;
    letter-spacing: 1.2px;
    user-select: none;
  }
  .logo svg {
    width: 40px;
    height: 40px;
    margin-right: 10px;
    fill: #ff6f00;
    filter: drop-shadow(1px 1px 1px rgba(0,0,0,0.3));
    animation: pulse 3s infinite alternate;
  }
  @keyframes pulse {
    0% { fill: #ff6f00; }
    100% { fill: #ff9100; }
  }

  nav a {
    color: #ffe082;
    margin: 0 18px;
    text-decoration: none;
    font-weight: 600;
    font-size: 17px;
    position: relative;
    transition: color 0.3s ease;
  }
  nav a::after {
    content: '';
    position: absolute;
    width: 0%;
    height: 2px;
    bottom: -4px;
    left: 0;
    background: #ff6f00;
    transition: width 0.3s ease;
  }
  nav a:hover {
    color: #ffca28;
  }
  nav a:hover::after {
    width: 100%;
  }
  .search-box input {
    padding: 8px 16px;
    border-radius: 30px;
    border: none;
    width: 240px;
    font-size: 15px;
    outline: none;
    box-shadow: 0 0 8px rgba(255,255,255,0.5);
    transition: box-shadow 0.3s ease;
  }
  .search-box input:focus {
    box-shadow: 0 0 12px #ff6f00;
  }
  main {
    padding: 30px 20px 60px;
    max-width: 1100px;
    margin: auto;
    flex-grow: 1;
  }
  .produits {
    display: grid;
    grid-template-columns: repeat(auto-fill,minmax(280px,1fr));
    gap: 24px;
  }
  .carte {
    background-color: #ffffffdd;
    border-radius: 16px;
    box-shadow: 0 6px 20px rgba(0,0,0,0.12);
    padding: 18px;
    text-align: center;
    display: flex;
    flex-direction: column;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  .carte:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 30px rgba(0,0,0,0.18);
  }
  .carte img {
    width: 100%;
    border-radius: 14px;
    object-fit: cover;
    height: 210px;
    margin-bottom: 14px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  }
  .carte h2 {
    font-size: 20px;
    color: #0d47a1;
    margin: 10px 0 6px;
  }
  .carte p {
    margin: 5px 0;
    color: #37474f;
    flex-grow: 1;
    font-weight: 500;
  }
  .prix {
    font-size: 20px;
    color: #ff6f00;
    font-weight: 700;
    margin-bottom: 12px;
  }
  button {
    background: linear-gradient(45deg, #ff6f00, #ff9100);
    color: white;
    border: none;
    padding: 12px 20px;
    border-radius: 30px;
    cursor: pointer;
    font-size: 16px;
    font-weight: 700;
    letter-spacing: 0.05em;
    transition: background 0.35s ease, box-shadow 0.35s ease;
    box-shadow: 0 5px 12px rgba(255,111,0,0.6);
  }
  button:hover {
    background: linear-gradient(45deg, #ff9100, #ff6f00);
    box-shadow: 0 7px 18px rgba(255,145,0,0.8);
  }
  .notification {
    margin-top: 10px;
    font-size: 14px;
    color: #388e3c;
    min-height: 20px;
    font-weight: 600;
  }

  /* Sección opiniones */
  .avis-section {
    margin-top: 60px;
  }
  .avis-section h3 {
    text-align: center;
    color: #0d47a1;
    margin-bottom: 30px;
    font-size: 26px;
    font-weight: 900;
    letter-spacing: 1px;
  }
  .avis-list {
    max-width: 850px;
    margin: auto;
    display: flex;
    flex-direction: column;
    gap: 24px;
  }
  .avis {
    background: #fff;
    border-radius: 16px;
    padding: 22px 28px;
    box-shadow: 0 3px 18px rgba(0,0,0,0.12);
  }
  .avis p {
    font-style: italic;
    color: #455a64;
    margin: 12px 0;
    font-size: 17px;
  }
  .client {
    font-weight: 700;
    color: #0d47a1;
    font-size: 18px;
  }
  .etoiles {
    color: #f9a825;
    font-size: 22px;
  }

  /* Sección avis de célébrités */
  .celebrite-section {
    margin-top: 50px;
    background: #e3f2fd;
    padding: 32px 25px;
    border-radius: 18px;
    max-width: 950px;
    margin-left: auto;
    margin-right: auto;
    box-shadow: 0 6px 22px rgba(13,71,161,0.18);
  }
  .celebrite-section h3 {
    text-align: center;
    color: #1565c0;
    margin-bottom: 38px;
    font-size: 28px;
    font-weight: 900;
    letter-spacing: 1.2px;
  }
  .celebrite-list {
    display: flex;
    flex-direction: column;
    gap: 28px;
  }
  .celebrite {
    background: white;
    border-radius: 18px;
    padding: 22px 28px;
    box-shadow: 0 6px 22px rgba(21,101,192,0.25);
    transition: transform 0.3s ease;
  }
  .celebrite:hover {
    transform: scale(1.03);
    box-shadow: 0 10px 30px rgba(21,101,192,0.35);
  }
  .celebrite p {
    font-style: italic;
    color: #0d47a1;
    margin: 14px 0 16px;
    font-size: 17px;
  }
  .celebrite .client {
    font-weight: 900;
    color: #ff6f00;
    font-size: 20px;
    letter-spacing: 0.05em;
  }
  .celebrite .etoiles {
    color: #fbc02d;
    font-size: 24px;
  }

  footer {
    background: #0d47a1;
    color: #ffe082;
    text-align: center;
    padding: 18px 20px;
    font-weight: 700;
    letter-spacing: 0.05em;
    font-size: 15px;
    box-shadow: 0 -4px 12px rgba(0,0,0,0.15);
  }

  @media (max-width: 600px) {
    .produits {
      grid-template-columns: 1fr;
    }
    nav a {
      margin: 8px 10px;
      font-size: 15px;
    }
    .search-box input {
      width: 100%;
      margin-top: 10px;
    }
    header {
      justify-content: center;
      gap: 15px;
    }
    .logo {
      font-size: 24px;
    }
  }
</style>
</head>
<body>

<header>
  <div class="logo" aria-label="Logo Voltige Juan">
    <!-- Icono de rayo -->
    <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false" fill="currentColor">
      <path d="M7 2v11h3v9l7-12h-4l4-8z"/>
    </svg>
    Voltige Juan
  </div>

  <nav aria-label="Navigation principale">
    <a href="#">Accueil</a>
    <a href="#">Marché</a>
    <a href="#">Rechercher</a>
  </nav>

  <div class="search-box">
    <input type="search" placeholder="Rechercher des chaussettes..." aria-label="Recherche" />
  </div>
</header>

<main>
  <section class="produits" aria-label="Liste des chaussettes disponibles">
    <!-- Media 1 -->
    <article class="carte">
      <img src="https://i.imgur.com/0KfbZlz.png" alt="Chaussette AS avec ballons de football américain" />
      <h2>Chaussette AS - Football Américain</h2>
      <p>Couleur : Bleu & Noir avec ballons de football américain.</p>
      <p class="prix">29,99 €</p>
      <button onclick="ajouterAuPanier('Chaussette AS - Football Américain')">Ajouter au panier</button>
      <div class="notification" id="notif1"></div>
    </article>

    <!-- Media 2 -->
    <article class="carte">
      <img src="https://i.imgur.com/jUXfF28.png" alt="Chaussette Voltige Juan avec ballons de football américain et soccer" />
      <h2>Chaussette Voltige Juan</h2>
      <p>Couleurs : Bleu et Noir avec ballons de football américain et soccer.</p>
      <p class="prix">34,99 €</p>
      <button onclick="ajouterAuPanier('Chaussette Voltige Juan')">Ajouter au panier</button>
      <div class="notification" id="notif2"></div>
    </article>
  </section>

  <section class="avis-section" aria-label="Avis clients">
    <h3>Avis de nos clients</h3>
    <div class="avis-list">
      <div class="avis">
        <div class="etoiles">★★★★★</div>
        <p>“Les chaussettes Voltige Juan sont incroyablement confortables et stylées. J'adore le design sportif!”</p>
        <div class="client">- Camille L.</div>
      </div>
      <div class="avis">
        <div class="etoiles">★★★★★</div>
        <p>“Je recommande ces chaussettes à tous les amateurs de sport, surtout pour le football.”</p>
        <div class="client">- Marc D.</div>
      </div>
      <div class="avis">
        <div class="etoiles">★★★★★</div>
        <p>“Super qualité et livraison rapide. Le design avec les ballons est parfait pour mes entraînements.”</p>
        <div class="client">- Sophie R.</div>
      </div>
    </div>
  </section>

  <section class="celebrite-section" aria-label="Avis des célébrités">
    <h3>Ce que disent les célébrités</h3>
    <div class="celebrite-list">
      <div class="celebrite">
        <div class="etoiles">★★★★★</div>
        <p>“Les chaussettes Voltige Juan ont changé ma façon de m'entraîner. Le confort est inégalé.”</p>
        <div class="client">- Jean Dupont, Champion de football</div>
      </div>
      <div class="celebrite">
        <div class="etoiles">★★★★★</div>
        <p>“Stylées, confortables, et parfaites pour les sportifs comme moi.”</p>
        <div class="client">- Claire Moreau, Athlète professionnelle</div>
      </div>
      <div class="celebrite">
        <div class="etoiles">★★★★★</div>
        <p>“Voltige Juan combine style et performance. Je les recommande vivement.”</p>
        <div class="client">- Lucas Martin, Influenceur fitness</div>
      </div>
    </div>
  </section>
</main>

<footer>
  &copy; 2025 Voltige Juan. Tous droits réservés.
</footer>

<script>
  function ajouterAuPanier(nomProduit) {
    alert(nomProduit + " a été ajouté au panier. Pas de paiement requis !");
  }
</script>

</body>
</html>
