<!DOCTYPE html>
<html lang="sv">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Injoy Kaffekopp</title>
  <meta name="description" content="Unika kaffekoppar för alla kaffeälskare – Injoy Kaffekopp.">
  <style>
    body {
      font-family: "Segoe UI", Arial, sans-serif;
      margin: 0;
      background: #f3f4f6;
      color: #463327;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }
    header {
      width: 100%;
      background: linear-gradient(90deg, #835438 55%, #edeae3 100%);
      color: #fff;
      padding: 2em 0 1em 0;
      text-align: center;
      box-shadow: 0 2px 12px rgba(0,0,0,0.11);
    }
    nav ul {
      list-style: none;
      display: flex;
      justify-content: center;
      gap: 2em;
      padding: 0;
      margin: 1em 0 0 0;
    }
    nav a {
      text-decoration: none;
      color: #fff;
      font-weight: bold;
      transition: color 0.2s;
    }
    nav a:hover {
      color: #ffd6a0;
    }
    main {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
      gap: 2em;
      padding: 2em;
      max-width: 1200px;
      width: 98%;
      margin: 0 auto;
      flex: 1;
    }
    .carousel-wrapper {
      grid-column: 1 / -1;
      justify-self: center;
      width: 90%;
      max-width: 650px;
      margin: 1em auto 2em auto;
      border-radius: 15px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.08);
      background: #fff;
      overflow: hidden;
    }
    .carousel {
      position: relative;
      width: 100%;
      height: 320px;
      background: #000;
    }
    .carousel img {
      width: 100%;
      height: 320px;
      object-fit: cover;
      display: block;
      transition: opacity 0.4s;
    }
    .carousel-btn {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(255,255,255,0.8);
      border: none;
      color: #835438;
      font-size: 2rem;
      padding: 0.3em 0.7em;
      cursor: pointer;
      z-index: 2;
      transition: background 0.2s;
      border-radius: 7px;
      outline: none;
    }
    .carousel-btn.left { left: 10px; }
    .carousel-btn.right { right: 10px; }
    .carousel-btn:active { background: #ffd6a0; }
    /* Produktkort med flexbox */
    .products {
      display: flex;
      flex-direction: column;
      gap: 2em;
      width: 100%;
    }
    .product-card {
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 2px 12px rgba(0,0,0,0.09);
      overflow: hidden;
      display: flex;
      flex-direction: row;
      align-items: stretch;
      transition: transform 0.2s;
    }
    .product-card:hover { transform: scale(1.025); }
    .product-img {
      min-width: 140px;
      width: 140px;
      height: 140px;
      object-fit: cover;
      border-right: 2px solid #f3f4f6;
    }
    .product-info {
      padding: 1em 1.3em;
      display: flex;
      flex-direction: column;
      justify-content: center;
      flex: 1;
    }
    .product-info h3 { margin: 0 0 0.3em 0; color: #835438;}
    .product-info p { margin:0 0 0.8em 0;}
    .buy-btn {
      align-self: flex-start;
      background: #835438;
      color: #fff;
      padding: 0.6em 1.3em;
      border: none;
      border-radius: 7px;
      font-size: 1em;
      cursor: pointer;
      font-weight: bold;
      transition: background 0.2s;
      margin-top: auto;
    }
    .buy-btn:hover {background: #b4754d;}
    .contact, .about {
      grid-column: 1 / -1;
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.07);
      margin-top: 1.4em;
      padding: 2em;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
      text-align: center;
    }
    .contact h2, .about h2 { color: #835438; margin-top:0;}
    @media (max-width: 700px) {
      .carousel img { height:190px;}
      main {padding: 1em;}
      .product-img {width:80px;height:80px;}
      .product-info h3 {font-size: 1.03em;}
      nav ul {gap:1em; font-size:0.95em;}
    }
  </style>
</head>
<body>
  <header>
    <h1>Injoy Kaffekopp</h1>
    <p>Unika koppar – glädje med varje kaffe!</p>
    <nav>
      <ul>
        <li><a href="#produkter">Produkter</a></li>
        <li><a href="#om">Om oss</a></li>
        <li><a href="#kontakt">Kontakt</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <!-- Bildspel / carousel -->
    <section class="carousel-wrapper" aria-label="Bildspel med kaffekoppar">
      <div class="carousel">
        <button class="carousel-btn left" onclick="prevSlide()" aria-label="Föregående bild">&#10094;</button>
        <img id="slide-img" src="images/kaffe1.jpg" alt="Kaffekopp 1" loading="lazy">
        <button class="carousel-btn right" onclick="nextSlide()" aria-label="Nästa bild">&#10095;</button>
      </div>
    </section>
    <!-- Produkter -->
    <section id="produkter" class="products">
      <article class="product-card">
        <img class="product-img" src="images/kaffe2.jpg" alt="Keramisk Kaffekopp" loading="lazy">
        <div class="product-info">
          <h3>Keramisk Kaffekopp</h3>
          <p>Modern design, perfekt för varma drycker. Diskmaskinssäker och miljövänlig.</p>
          <button class="buy-btn">Köp nu</button>
        </div>
      </article>
      <article class="product-card">
        <img class="product-img" src="images/kaffe3.jpg" alt="Resekopp med lock" loading="lazy">
        <div class="product-info">
          <h3>Resekopp med lock</h3>
          <p>Smidig på språng, håller drycken varm extra länge.</p>
          <button class="buy-btn">Köp nu</button>
        </div>
      </article>
      <article class="product-card">
        <img class="product-img" src="images/kaffe4.jpg" alt="Retro Kaffemugg" loading="lazy">
        <div class="product-info">
          <h3>Retro Kaffemugg</h3>
          <p>Nostalgi på hög nivå, rustik och tålig med sentimental design.</p>
          <button class="buy-btn">Köp nu</button>
        </div>
      </article>
    </section>
    <section id="om" class="about">
      <h2>Om Injoy Kaffekopp</h2>
      <p>Vi älskar kaffe och koppar med känsla! Våra produkter är skapade för att sätta en extra guldkant på din fikastund – oavsett om du är hemma, på resande fot, eller bjuder in vänner.<br>
      Unika designer, ekologiska material och alltid mycket kärlek i varje kopp.</p>
    </section>
    <section id="kontakt" class="contact">
      <h2>Kontakt</h2>
      <form name="kontaktform" method="POST">
        <p>
          <label for="namn">Namn</label><br>
          <input type="text" id="namn" name="namn" required autocomplete="name">
        </p>
        <p>
          <label for="epost">E-post</label><br>
          <input type="email" id="epost" name="epost" required autocomplete="email">
        </p>
        <p>
          <label for="meddelande">Meddelande</label><br>
          <textarea id="meddelande" name="meddelande" rows="4" required></textarea>
        </p>
        <button type="submit" class="buy-btn">Skicka</button>
      </form>
      <p style="margin-top:1em; font-size: 0.9em; color:#827168;">
        eller maila oss på <a href="mailto:info@injoykaffekopp.se">info@injoykaffekopp.se</a>
      </p>
    </section>
  </main>
  <footer style="width:100%; text-align:center; padding:1.5em 0 0.9em 0; font-size: 0.9em; color: #a58b73;">
    &copy; 2025 Injoy Kaffekopp — Webbplats byggd enligt moderna webbstandarder.
  </footer>
  <script>
    // Bildspel med egna bilder
    const slides = [
      { url: "imageshttps://www.google.com/imgres?imgurl=https://www.shutterstock.com/image-vector/coffee-house-enjoy-your-icon-260nw-2167674461.jpg&imgrefurl=https://www.shutterstock.com/image-vector/coffee-house-enjoy-your-icon-logo-2167674461&h=280&w=260&tbnid=-QOvI6kfs1NNbM&source=sa.im&tbnh=280&tbnw=260&usg=AI4_-kRaNHKaSNnXlwVZzDIh7IcUongFxA&vet=1&docid=XsrbBLcpG-QoAM/kaffe1.jpg", alt: "Kaffekopp 1" },
      { url: "images/khttps://www.google.com/imgres?imgurl=https://thumbs.dreamstime.com/b/espresso-pastry-cafe-evening-outdoor-courtyard-lights-dessert-relax-ambiance-389113985.jpg&imgrefurl=https://www.dreamstime.com/photos-images/enjoy-cup-coffee-shop-night.html&h=449&w=800&tbnid=uaKkYEyF2BOIVM&source=sa.im&tbnh=415&tbnw=739&usg=AI4_-kRLXYpG2RjzH3H9UMVa4yGedUPgkQ&vet=1&docid=OcFDl1OkNuoeGMaffe2.jpg", alt: "Kaffekopp 2" },
      { url: "images/kaffehttps://www.google.com/imgres?imgurl=https://www.shutterstock.com/image-photo/group-friends-sharing-coffee-food-600nw-2627473971.jpg&imgrefurl=https://www.shutterstock.com/search/coffee-shop-landscape&h=400&w=600&tbnid=SoNCCEhrWxoa-M&source=sa.im&tbnh=400&tbnw=600&usg=AI4_-kS4FUbJs0Kx8qPrIbYvVTru3v0ovg&vet=1&docid=yrlPifDGpUfRsM3.jpg", alt: "Kaffekopp 3" },
      { url: "images/kaffe4.jpg", https://www.google.com/imgres?imgurl=https://thumbs.dreamstime.com/b/espresso-pastry-cafe-evening-outdoor-courtyard-lights-dessert-relax-ambiance-389113985.jpg&imgrefurl=https://www.dreamstime.com/photos-images/enjoy-cup-coffee-shop-night.html&h=449&w=800&tbnid=uaKkYEyF2BOIVM&source=sa.im&tbnh=415&tbnw=739&usg=AI4_-kRLXYpG2RjzH3H9UMVa4yGedUPgkQ&vet=1&docid=OcFDl1OkNuoeGMalt: "Kaffekopp 4" }
    ];
    let currentSlide = 0;
    function showSlide(index) {
      const img = document.getElementById('slide-img');
      img.src = slides[index].url;
      img.alt = slides[index].alt;
      currentSlide = index;
    }
    function nextSlide() {
      currentSlide = (currentSlide + 1) % slides.length;
      showSlide(currentSlide);
    }
    function prevSlide() {
      currentSlide = (currentSlide - 1 + slides.length) % slides.length;
      showSlide(currentSlide);
    }
    // Initial start
    window.onload = () => showSlide(0);
  </script>
</body>
</html>
