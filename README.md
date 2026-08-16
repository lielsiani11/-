# -<!DOCTYPE html>
<html lang="he" dir="rtl">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>החצר האחורית | אירועים בהוד השרון</title>

  <meta
    name="description"
    content="החצר האחורית - מתחם אירועים בוטיק בהוד השרון. חתונות, בר ובת מצווה, ימי הולדת ואירועי חברה."
  >

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link
    href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;500;600;700;800;900&family=Assistant:wght@300;400;500;600;700&display=swap"
    rel="stylesheet"
  >

  <style>

    /* =========================
       BASE
    ========================== */

    :root {
      --dark: #0b0d0b;
      --dark2: #121612;
      --cream: #f3efe6;
      --cream2: #e8e1d3;
      --green: #84906d;
      --light-green: #aeb89a;
      --text: #f8f5ee;
      --muted: #b7b9b2;
      --border: rgba(255,255,255,.13);
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: "Assistant", Arial, sans-serif;
      background: var(--dark);
      color: white;
      overflow-x: hidden;
    }

    body.menu-open {
      overflow: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      display: block;
      width: 100%;
    }

    button,
    input,
    select,
    textarea {
      font: inherit;
    }


    /* =========================
       NAVIGATION
    ========================== */

    .navbar {
      position: fixed;
      top: 0;
      right: 0;
      left: 0;

      z-index: 999;

      padding: 22px 5%;

      display: flex;
      align-items: center;
      justify-content: space-between;

      transition: .35s;
    }

    .navbar.scrolled {
      padding-top: 13px;
      padding-bottom: 13px;

      background: rgba(9,12,9,.88);
      backdrop-filter: blur(18px);

      border-bottom: 1px solid var(--border);
    }

    .logo {
      font-family: "Heebo";
      font-size: 28px;
      font-weight: 900;

      letter-spacing: -1px;
    }

    .logo span {
      color: var(--light-green);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 30px;

      font-size: 15px;
    }

    .nav-links a {
      opacity: .85;
      transition: .2s;
    }

    .nav-links a:hover {
      opacity: 1;
    }

    .nav-button {
      border: 1px solid rgba(255,255,255,.4);

      padding: 10px 18px;

      border-radius: 50px;
    }

    .menu-btn {
      display: none;
      width: 45px;
      height: 45px;

      border-radius: 50%;

      border: 1px solid var(--border);
      background: rgba(0,0,0,.25);
      color: white;

      font-size: 23px;
    }


    /* =========================
       HERO
    ========================== */

    .hero {
      min-height: 100svh;

      position: relative;

      display: flex;
      align-items: flex-end;

      background-image:
        linear-gradient(
          180deg,
          rgba(0,0,0,.12) 0%,
          rgba(0,0,0,.18) 45%,
          rgba(0,0,0,.85) 100%
        ),
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%97%D7%AA%D7%95%D7%A0%D7%95%D7%AA-2.d110a0.webp");

      background-size: cover;
      background-position: center;
    }

    .hero::before {
      content: "";

      position: absolute;
      inset: 0;

      background:
        radial-gradient(
          circle at 70% 35%,
          transparent,
          rgba(0,0,0,.22)
        );
    }

    .hero-content {
      position: relative;
      z-index: 3;

      width: min(1250px, 90%);

      margin: auto;

      padding-bottom: 8vh;
    }

    .hero-small {
      display: flex;
      align-items: center;
      gap: 12px;

      font-size: 13px;
      letter-spacing: 3px;

      color: #ddd8cc;

      margin-bottom: 16px;
    }

    .hero-small::before {
      content: "";

      height: 1px;
      width: 50px;

      background: #ddd8cc;
    }

    .hero h1 {
      font-family: "Heebo";

      font-weight: 800;

      font-size: clamp(62px, 10vw, 145px);

      line-height: .86;

      letter-spacing: -6px;

      margin: 0;

      max-width: 1000px;
    }

    .hero-bottom {
      margin-top: 30px;

      display: flex;
      justify-content: space-between;
      align-items: flex-end;

      gap: 30px;
    }

    .hero-text {
      font-size: clamp(19px, 2vw, 27px);

      line-height: 1.55;

      color: #e6e2d9;

      max-width: 610px;

      margin: 0;
    }


    /* =========================
       BUTTONS
    ========================== */

    .buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .btn {
      min-height: 52px;

      padding: 0 24px;

      display: inline-flex;
      justify-content: center;
      align-items: center;

      border-radius: 50px;

      font-weight: 700;

      transition: .25s;
    }

    .btn-primary {
      background: var(--cream);
      color: #101410;
    }

    .btn-primary:hover {
      background: white;

      transform: translateY(-2px);
    }

    .btn-outline {
      border: 1px solid rgba(255,255,255,.38);

      background: rgba(0,0,0,.1);
    }

    .btn-outline:hover {
      background: rgba(255,255,255,.12);
    }


    /* =========================
       TICKER
    ========================== */

    .ticker {
      background: #090b09;

      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);

      overflow: hidden;

      white-space: nowrap;
    }

    .ticker-inner {
      width: max-content;

      padding: 17px 0;

      animation: ticker 28s linear infinite;

      color: #bbbeb4;

      font-family: "Heebo";

      font-size: 14px;

      letter-spacing: 2px;
    }

    .ticker-inner span {
      margin: 0 22px;
    }

    .ticker-inner span::after {
      content: "✦";

      color: var(--green);

      margin-right: 42px;
    }

    @keyframes ticker {
      from {
        transform: translateX(0);
      }

      to {
        transform: translateX(50%);
      }
    }


    /* =========================
       GENERAL
    ========================== */

    section {
      padding: 120px 5%;
    }

    .container {
      width: min(1220px, 100%);

      margin: auto;
    }

    .eyebrow {
      color: #788164;

      font-size: 13px;

      letter-spacing: 2px;

      font-weight: 700;

      margin-bottom: 18px;
    }

    .title {
      margin: 0;

      font-family: "Heebo";

      font-size: clamp(43px, 6vw, 82px);

      line-height: .98;

      letter-spacing: -3px;
    }


    /* =========================
       ABOUT
    ========================== */

    .about {
      background: var(--cream);
      color: #141714;
    }

    .about-grid {
      display: grid;

      grid-template-columns: 1fr 1fr;

      gap: 90px;

      align-items: center;
    }

    .about-text {
      font-size: 20px;

      line-height: 1.9;

      color: #464b46;
    }

    .about-text strong {
      color: #111;
    }

    .facts {
      display: grid;

      grid-template-columns: repeat(3, 1fr);

      gap: 15px;

      margin-top: 36px;
    }

    .fact {
      border-top: 1px solid #bab4a9;

      padding-top: 18px;
    }

    .fact strong {
      display: block;

      font-size: 23px;

      margin-bottom: 5px;
    }

    .fact span {
      color: #686d68;

      font-size: 14px;
    }


    /* =========================
       BIG PHOTO
    ========================== */

    .big-photo-section {
      background: var(--cream);

      padding-top: 20px;
    }

    .big-photo {
      min-height: 75vh;

      border-radius: 32px;

      position: relative;

      overflow: hidden;

      background:
        linear-gradient(
          to top,
          rgba(0,0,0,.65),
          transparent 65%
        ),
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%9E%D7%99%D7%99-%D7%94%D7%95%D7%9C%D7%93%D7%AA2.d110a0.webp");

      background-position: center;
      background-size: cover;
    }

    .big-photo-text {
      position: absolute;

      bottom: 38px;
      right: 38px;

      max-width: 700px;
    }

    .big-photo-text h2 {
      font-family: "Heebo";

      font-size: clamp(36px, 6vw, 75px);

      line-height: .98;

      letter-spacing: -3px;

      margin: 0 0 12px;
    }

    .big-photo-text p {
      color: #e3e3dc;

      font-size: 19px;

      margin: 0;
    }


    /* =========================
       EVENTS
    ========================== */

    .events {
      background: var(--cream);
      color: #111511;

      padding-top: 30px;
    }

    .event-intro {
      display: flex;

      justify-content: space-between;

      gap: 30px;

      align-items: flex-end;

      margin-bottom: 50px;
    }

    .event-intro p {
      max-width: 450px;

      font-size: 18px;

      color: #5d635d;

      line-height: 1.8;

      margin: 0;
    }

    .events-grid {
      display: grid;

      grid-template-columns: 1.15fr .85fr;

      gap: 18px;
    }

    .event-card {
      min-height: 550px;

      border-radius: 28px;

      overflow: hidden;

      position: relative;

      background-position: center;
      background-size: cover;

      box-shadow: 0 24px 80px rgba(0,0,0,.15);
    }

    .event-card::before {
      content: "";

      position: absolute;
      inset: 0;

      background:
        linear-gradient(
          to top,
          rgba(0,0,0,.83),
          rgba(0,0,0,.05) 68%
        );
    }

    .event-content {
      position: absolute;

      z-index: 2;

      right: 28px;
      left: 28px;
      bottom: 28px;

      color: white;
    }

    .event-label {
      display: inline-flex;

      border: 1px solid rgba(255,255,255,.4);

      padding: 7px 13px;

      border-radius: 50px;

      font-size: 12px;

      margin-bottom: 14px;

      backdrop-filter: blur(8px);
    }

    .event-content h3 {
      margin: 0 0 8px;

      font-family: "Heebo";

      font-size: clamp(32px, 4vw, 52px);

      letter-spacing: -2px;

      line-height: 1;
    }

    .event-content p {
      margin: 0;

      color: #e0e0d8;

      font-size: 16px;

      line-height: 1.65;

      max-width: 480px;
    }

    .wedding {
      background-image:
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%97%D7%AA%D7%95%D7%A0%D7%95%D7%AA-2.d110a0.webp");
    }

    .batmitzvah {
      background-image:
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%91%D7%AA-%D7%9E%D7%A6%D7%95%D7%95%D7%942.d110a0.webp");
    }

    .barmitzvah {
      background-image:
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%91%D7%A8-%D7%A6%D7%95%D7%95%D7%94-1.d110a0.webp");
    }

    .company {
      background-image:
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%9B%D7%A0%D7%A1%D7%99%D7%9D1.d110a0.webp");
    }

    .birthday {
      background-image:
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%9E%D7%99%D7%99-%D7%94%D7%95%D7%9C%D7%93%D7%AA2.d110a0.webp");
    }

    .small-events {
      display: grid;

      grid-template-columns: repeat(3, 1fr);

      gap: 18px;

      margin-top: 18px;
    }

    .small-events .event-card {
      min-height: 410px;
    }

    .small-events .event-content h3 {
      font-size: 34px;
    }


    /* =========================
       EXPERIENCE
    ========================== */

    .experience {
      background: var(--dark);
    }

    .experience-head {
      display: flex;

      justify-content: space-between;

      align-items: flex-end;

      gap: 40px;

      margin-bottom: 60px;
    }

    .experience-head p {
      color: var(--muted);

      max-width: 450px;

      font-size: 18px;

      line-height: 1.8;
    }

    .process {
      display: grid;

      grid-template-columns: repeat(4,1fr);

      border-top: 1px solid var(--border);
    }

    .process-item {
      min-height: 250px;

      padding: 30px 22px;

      border-left: 1px solid var(--border);
    }

    .process-item:last-child {
      border-left: none;
    }

    .number {
      color: var(--green);

      font-size: 13px;

      margin-bottom: 60px;
    }

    .process-item h3 {
      font-size: 23px;

      margin: 0 0 12px;
    }

    .process-item p {
      color: #aaa;

      line-height: 1.7;

      margin: 0;
    }


    /* =========================
       GALLERY
    ========================== */

    .gallery {
      padding-top: 30px;

      background: var(--dark);
    }

    .gallery-title {
      margin-bottom: 45px;

      display: flex;

      justify-content: space-between;

      align-items: flex-end;

      gap: 25px;
    }

    .gallery-grid {
      display: grid;

      grid-template-columns: 1.3fr .7fr .7fr;

      grid-template-rows: 330px 330px;

      gap: 12px;
    }

    .gallery-item {
      border-radius: 22px;

      overflow: hidden;

      position: relative;

      cursor: pointer;
    }

    .gallery-item:first-child {
      grid-row: 1 / 3;
    }

    .gallery-item img {
      width: 100%;
      height: 100%;

      object-fit: cover;

      transition: .5s;
    }

    .gallery-item:hover img {
      transform: scale(1.05);
    }


    /* =========================
       REVIEWS
    ========================== */

    .reviews {
      background: var(--cream2);
      color: #151815;

      text-align: center;
    }

    .stars {
      color: #6e765c;

      font-size: 22px;

      letter-spacing: 7px;

      margin-bottom: 25px;
    }

    .review {
      max-width: 950px;

      margin: auto;

      font-family: "Heebo";

      font-size: clamp(26px, 4vw, 48px);

      line-height: 1.35;

      letter-spacing: -1.5px;
    }

    .review-person {
      margin-top: 25px;

      color: #686c66;
    }


    /* =========================
       CTA
    ========================== */

    .cta {
      min-height: 70vh;

      position: relative;

      display: flex;
      align-items: center;

      background:
        linear-gradient(
          90deg,
          rgba(0,0,0,.87),
          rgba(0,0,0,.23)
        ),
        url("https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%9B%D7%A0%D7%A1%D7%99%D7%9D1.d110a0.webp");

      background-position: center;
      background-size: cover;
    }

    .cta-content {
      max-width: 720px;
    }

    .cta h2 {
      font-family: "Heebo";

      font-size: clamp(45px,7vw,90px);

      letter-spacing: -4px;

      line-height: .95;

      margin: 0 0 22px;
    }

    .cta p {
      color: #ddd;

      font-size: 20px;

      line-height: 1.7;

      margin-bottom: 30px;
    }


    /* =========================
       CONTACT
    ========================== */

    .contact {
      background: #0b0e0b;
    }

    .contact-grid {
      display: grid;

      grid-template-columns: 1fr 1fr;

      gap: 80px;
    }

    .contact-description {
      color: #afb2aa;

      font-size: 18px;

      line-height: 1.8;

      max-width: 500px;
    }

    .contact-info {
      margin-top: 35px;

      display: flex;

      flex-direction: column;

      gap: 12px;
    }

    .contact-row {
      border-bottom: 1px solid var(--border);

      padding: 15px 0;

      display: flex;

      justify-content: space-between;

      gap: 15px;

      color: #d6d8d1;
    }

    .contact-row span:first-child {
      color: #7f827b;
    }

    .contact-card {
      background: #151a15;

      border: 1px solid var(--border);

      border-radius: 30px;

      padding: 35px;
    }

    .contact-card h3 {
      font-family: "Heebo";

      font-size: 32px;

      margin-top: 0;
    }

    .contact-card p {
      color: #aaa;

      line-height: 1.7;
    }

    .contact-buttons {
      display: grid;

      gap: 12px;

      margin-top: 28px;
    }

    .contact-buttons a {
      width: 100%;
    }


    /* =========================
       FOOTER
    ========================== */

    footer {
      background: #070907;

      border-top: 1px solid var(--border);

      padding: 35px 5%;
    }

    .footer-content {
      width: min(1220px,100%);

      margin: auto;

      display: flex;

      justify-content: space-between;

      align-items: center;

      flex-wrap: wrap;

      gap: 20px;
    }

    .footer-logo {
      font-family: "Heebo";

      font-size: 24px;

      font-weight: 800;
    }

    .footer-text {
      color: #858980;

      font-size: 13px;
    }


    /* =========================
       FLOATING PHONE
    ========================== */

    .floating-phone {
      position: fixed;

      left: 20px;
      bottom: 20px;

      width: 62px;
      height: 62px;

      border-radius: 50%;

      display: flex;
      justify-content: center;
      align-items: center;

      background: var(--cream);

      color: #101510;

      font-size: 24px;

      z-index: 998;

      box-shadow: 0 15px 40px rgba(0,0,0,.35);

      transition: .2s;
    }

    .floating-phone:hover {
      transform: translateY(-4px);
    }


    /* =========================
       ANIMATION
    ========================== */

    .reveal {
      opacity: 0;

      transform: translateY(35px);

      transition:
        opacity .85s ease,
        transform .85s ease;
    }

    .reveal.show {
      opacity: 1;

      transform: translateY(0);
    }


    /* =========================
       MOBILE MENU
    ========================== */

    .mobile-menu {
      position: fixed;

      z-index: 995;

      inset: 0;

      padding: 110px 28px 30px;

      background: rgba(8,11,8,.97);

      backdrop-filter: blur(20px);

      display: none;
    }

    .mobile-menu.active {
      display: flex;

      flex-direction: column;

      gap: 12px;
    }

    .mobile-menu a {
      font-family: "Heebo";

      font-size: 38px;

      font-weight: 600;

      border-bottom: 1px solid var(--border);

      padding: 12px 0;
    }


    /* =========================
       RESPONSIVE
    ========================== */

    @media(max-width: 900px) {

      .nav-links {
        display: none;
      }

      .menu-btn {
        display: block;
      }

      .hero h1 {
        letter-spacing: -4px;
      }

      .hero-bottom {
        flex-direction: column;

        align-items: flex-start;
      }

      .about-grid,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .events-grid {
        grid-template-columns: 1fr;
      }

      .small-events {
        grid-template-columns: 1fr;
      }

      .experience-head {
        display: block;
      }

      .process {
        grid-template-columns: 1fr 1fr;
      }

      .gallery-grid {
        grid-template-columns: 1fr 1fr;

        grid-template-rows: 400px 250px 250px;
      }

      .gallery-item:first-child {
        grid-column: 1 / 3;
        grid-row: auto;
      }

    }


    @media(max-width: 600px) {

      section {
        padding: 85px 18px;
      }

      .navbar {
        padding-left: 18px;
        padding-right: 18px;
      }

      .logo {
        font-size: 22px;
      }

      .hero-content {
        width: calc(100% - 36px);
      }

      .hero h1 {
        font-size: 61px;

        letter-spacing: -3px;

        line-height: .93;
      }

      .hero-small {
        font-size: 10px;
      }

      .hero-text {
        font-size: 18px;
      }

      .btn {
        width: 100%;
      }

      .buttons {
        width: 100%;
      }

      .title {
        font-size: 47px;
      }

      .facts {
        grid-template-columns: 1fr;
      }

      .big-photo {
        min-height: 620px;

        border-radius: 22px;
      }

      .big-photo-text {
        right: 22px;
        left: 22px;
        bottom: 25px;
      }

      .event-intro {
        display: block;
      }

      .event-intro p {
        margin-top: 20px;
      }

      .event-card {
        min-height: 520px;
      }

      .small-events .event-card {
        min-height: 430px;
      }

      .process {
        grid-template-columns: 1fr;
      }

      .process-item {
        border-left: none;
        border-bottom: 1px solid var(--border);
      }

      .number {
        margin-bottom: 30px;
      }

      .gallery-title {
        display: block;
      }

      .gallery-grid {
        display: grid;

        grid-template-columns: 1fr;

        grid-template-rows: repeat(5, 320px);
      }

      .gallery-item:first-child {
        grid-column: auto;
      }

      .contact-card {
        padding: 25px;
      }

    }

  </style>
</head>


<body>

  <!-- NAV -->

  <nav class="navbar" id="navbar">

    <a href="#home" class="logo">
      החצר <span>האחורית</span>
    </a>

    <div class="nav-links">

      <a href="#about">
        המקום
      </a>

      <a href="#events">
        אירועים
      </a>

      <a href="#gallery">
        גלריה
      </a>

      <a href="#contact" class="nav-button">
        בדיקת תאריך
      </a>

    </div>

    <button
      class="menu-btn"
      id="menuBtn"
      aria-label="פתיחת תפריט"
    >
      ☰
    </button>

  </nav>


  <!-- MOBILE MENU -->

  <div class="mobile-menu" id="mobileMenu">

    <a href="#about">
      המקום
    </a>

    <a href="#events">
      אירועים
    </a>

    <a href="#gallery">
      גלריה
    </a>

    <a href="#contact">
      יצירת קשר
    </a>

  </div>


  <!-- HERO -->

  <section class="hero" id="home">

    <div class="hero-content">

      <div class="hero-small">
        THE BACKYARD · HOD HASHARON
      </div>

      <h1>
        לא עוד אירוע.<br>
        החוויה שלכם.
      </h1>

      <div class="hero-bottom">

        <p class="hero-text">
          גן אירועים בוטיק בלב השרון.
          טבע, בריכה, אוכל, מוזיקה ואווירה
          שבונים סביבכם.
        </p>

        <div class="buttons">

          <a
            href="tel:0772304718"
            class="btn btn-primary"
          >
            בדיקת תאריך פנוי ←
          </a>

          <a
            href="#events"
            class="btn btn-outline"
          >
            גלו את המקום
          </a>

        </div>

      </div>

    </div>

  </section>


  <!-- TICKER -->

  <div class="ticker">

    <div class="ticker-inner">

      <span>חתונות בוטיק</span>

      <span>בר מצווה</span>

      <span>בת מצווה</span>

      <span>אירועי חברה</span>

      <span>ימי הולדת</span>

      <span>בריכה מחוממת</span>

      <span>הוד השרון</span>

      <span>חתונות בוטיק</span>

      <span>בר מצווה</span>

      <span>בת מצווה</span>

      <span>אירועי חברה</span>

      <span>ימי הולדת</span>

      <span>בריכה מחוממת</span>

      <span>הוד השרון</span>

    </div>

  </div>


  <!-- ABOUT -->

  <section class="about" id="about">

    <div class="container about-grid">

      <div class="reveal">

        <div class="eyebrow">
          THE BACKYARD
        </div>

        <h2 class="title">
          אירוע שמרגיש<br>
          קצת אחרת.
        </h2>

      </div>


      <div class="reveal">

        <div class="about-text">

          <p>
            <strong>
              החצר האחורית
            </strong>
            היא מתחם אירועים בהוד השרון שמשלב
            טבע ויוקרה במקום אחד.
          </p>

          <p>
            חצר גדולה, בריכה,
            צמחייה חיה, אוכל איכותי
            ואפשרות לבנות כל אירוע
            בצורה שמתאימה בדיוק לכם.
          </p>

        </div>


        <div class="facts">

          <div class="fact">

            <strong>
              עד 200
            </strong>

            <span>
              חוגגים בחתונת בוטיק
            </span>

          </div>


          <div class="fact">

            <strong>
              בריכה
            </strong>

            <span>
              מקורה ומחוממת בחורף
            </span>

          </div>


          <div class="fact">

            <strong>
              הוד השרון
            </strong>

            <span>
              דרך הים 1
            </span>

          </div>

        </div>

      </div>

    </div>

  </section>


  <!-- BIG IMAGE -->

  <section class="big-photo-section">

    <div class="container">

      <div class="big-photo reveal">

        <div class="big-photo-text">

          <h2>
            מקום שגורם<br>
            לאנשים להישאר.
          </h2>

          <p>
            מהאור הראשון ועד השיר האחרון.
          </p>

        </div>

      </div>

    </div>

  </section>


  <!-- EVENTS -->

  <section class="events" id="events">

    <div class="container">

      <div class="event-intro">

        <div class="reveal">

          <div class="eyebrow">
            YOUR EVENT
          </div>

          <h2 class="title">
            אז מה<br>
            חוגגים?
          </h2>

        </div>


        <p class="reveal">

          לכל אירוע יש אופי אחר.

          החצר האחורית מאפשרת
          לבנות את המקום,
          האוכל והאווירה
          בהתאם לחגיגה שלכם.

        </p>

      </div>


      <div class="events-grid">


        <!-- WEDDING -->

        <article class="event-card wedding reveal">

          <div class="event-content">

            <span class="event-label">
              חתונות
            </span>

            <h3>
              חתונת בוטיק<br>
              בלי להרגיש באולם.
            </h3>

            <p>
              מתחם פתוח ואינטימי
              לחתונות של עד 200 חוגגים,
              עם חצר, בריכה וצמחייה חיה.
            </p>

          </div>

        </article>


        <!-- BAT MITZVAH -->

        <article class="event-card batmitzvah reveal">

          <div class="event-content">

            <span class="event-label">
              בת מצווה
            </span>

            <h3>
              ערב שהוא<br>
              כולו שלה.
            </h3>

            <p>
              מקום למסיבה,
              מוזיקה, בריכה,
              אוכל ואטרקציות.
            </p>

          </div>

        </article>

      </div>


      <div class="small-events">


        <!-- BAR MITZVAH -->

        <article class="event-card barmitzvah reveal">

          <div class="event-content">

            <span class="event-label">
              בר מצווה
            </span>

            <h3>
              אירוע<br>
              שלא שוכחים.
            </h3>

          </div>

        </article>


        <!-- CORPORATE -->

        <article class="event-card company reveal">

          <div class="event-content">

            <span class="event-label">
              חברות
            </span>

            <h3>
              לצאת קצת<br>
              מהמשרד.
            </h3>

          </div>

        </article>


        <!-- BIRTHDAY -->

        <article class="event-card birthday reveal">

          <div class="event-content">

            <span class="event-label">
              ימי הולדת
            </span>

            <h3>
              יש סיבה.<br>
              אז חוגגים.
            </h3>

          </div>

        </article>

      </div>

    </div>

  </section>


  <!-- EXPERIENCE -->

  <section class="experience">

    <div class="container">

      <div class="experience-head">

        <div class="reveal">

          <div class="eyebrow">
            THE EXPERIENCE
          </div>

          <h2 class="title">
            אתם חוגגים.<br>
            אנחנו דואגים לשאר.
          </h2>

        </div>


        <p class="reveal">

          מהרעיון הראשון
          ועד הרגע שבו האורח האחרון הולך הביתה.

          המטרה היא לייצר
          אירוע שמרגיש שלכם,
          ולא חבילת מדף.

        </p>

      </div>


      <div class="process">


        <div class="process-item reveal">

          <div class="number">
            01
          </div>

          <h3>
            מכירים
          </h3>

          <p>
            מבינים מי אתם
            ומה אתם באמת רוצים
            מהאירוע.
          </p>

        </div>


        <div class="process-item reveal">

          <div class="number">
            02
          </div>

          <h3>
            מתכננים
          </h3>

          <p>
            בונים את החלל,
            האווירה,
            האוכל והמוזיקה.
          </p>

        </div>


        <div class="process-item reveal">

          <div class="number">
            03
          </div>

          <h3>
            חוגגים
          </h3>

          <p>
            ביום האירוע
            אתם מגיעים ליהנות
            עם האורחים שלכם.
          </p>

        </div>


        <div class="process-item reveal">

          <div class="number">
            04
          </div>

          <h3>
            זוכרים
          </h3>

          <p>
            אנחנו רוצים שהאירוע
            ימשיך בשיחות
            גם ביום שאחרי.
          </p>

        </div>


      </div>

    </div>

  </section>


  <!-- GALLERY -->

  <section class="gallery" id="gallery">

    <div class="container">

      <div class="gallery-title">

        <div class="reveal">

          <div class="eyebrow">
            GALLERY
          </div>

          <h2 class="title">
            קצת מהחצר.
          </h2>

        </div>

      </div>


      <div class="gallery-grid">


        <div class="gallery-item reveal">

          <img
            loading="lazy"
            src="https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%97%D7%AA%D7%95%D7%A0%D7%95%D7%AA-2.d110a0.webp"
            alt="חתונה בחצר האחורית"
          >

        </div>


        <div class="gallery-item reveal">

          <img
            loading="lazy"
            src="https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%91%D7%AA-%D7%9E%D7%A6%D7%95%D7%95%D7%942.d110a0.webp"
            alt="בת מצווה בחצר האחורית"
          >

        </div>


        <div class="gallery-item reveal">

          <img
            loading="lazy"
            src="https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%91%D7%A8-%D7%A6%D7%95%D7%95%D7%94-1.d110a0.webp"
            alt="בר מצווה בחצר האחורית"
          >

        </div>


        <div class="gallery-item reveal">

          <img
            loading="lazy"
            src="https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%9B%D7%A0%D7%A1%D7%99%D7%9D1.d110a0.webp"
            alt="אירוע חברה בחצר האחורית"
          >

        </div>


        <div class="gallery-item reveal">

          <img
            loading="lazy"
            src="https://www.thebackyard.co.il/wp-content/uploads/2022/05/%D7%9E%D7%99%D7%99-%D7%94%D7%95%D7%9C%D7%93%D7%AA2.d110a0.webp"
            alt="יום הולדת בחצר האחורית"
          >

        </div>


      </div>

    </div>

  </section>


  <!-- REVIEW -->

  <section class="reviews">

    <div class="container reveal">

      <div class="stars">
        ★★★★★
      </div>

      <div class="review">

        “צוות של אלופים,
        שירותי,
        מקום מוקפד,
        אוכל מצוין.
        לא הפסקנו לקבל מחמאות.”

      </div>

      <div class="review-person">
        אידית ענבר · אורחת בחצר האחורית
      </div>

    </div>

  </section>


  <!-- CTA -->

  <section class="cta">

    <div class="container">

      <div class="cta-content reveal">

        <div class="eyebrow">
          YOUR DATE
        </div>

        <h2>
          יש לכם תאריך?<br>
          בואו נתחיל.
        </h2>

        <p>

          השיחה הראשונה היא פשוטה.

          מספרים לנו
          מה אתם מתכננים
          ואנחנו בודקים יחד
          איך הופכים את זה לאירוע.

        </p>


        <div class="buttons">

          <a
            class="btn btn-primary"
            href="tel:0772304718"
          >
            077-2304718 ☎
          </a>

          <a
            class="btn btn-outline"
            href="#contact"
          >
            פרטי המקום
          </a>

        </div>

      </div>

    </div>

  </section>


  <!-- CONTACT -->

  <section class="contact" id="contact">

    <div class="container contact-grid">


      <div class="reveal">

        <div class="eyebrow">
          CONTACT
        </div>

        <h2 class="title">
          נפגשים<br>
          בחצר?
        </h2>

        <p class="contact-description">

          רוצים לבדוק תאריך,
          להגיע לראות את המקום
          או לדבר על האירוע שלכם?

          אנחנו כאן.

        </p>


        <div class="contact-info">


          <a
            class="contact-row"
            href="tel:0772304718"
          >

            <span>
              טלפון
            </span>

            <strong>
              077-2304718
            </strong>

          </a>


          <a
            class="contact-row"
            href="https://maps.google.com/?q=דרך+הים+1+הוד+השרון"
            target="_blank"
          >

            <span>
              כתובת
            </span>

            <strong>
              דרך הים 1, הוד השרון
            </strong>

          </a>


          <div class="contact-row">

            <span>
              שעות
            </span>

            <strong>
              09:00–21:00
            </strong>

          </div>


          <div class="contact-row">

            <span>
              שבת
            </span>

            <strong>
              המקום אינו פעיל בשבת
            </strong>

          </div>


        </div>

      </div>


      <div class="contact-card reveal">

        <h3>
          בואו נדבר על האירוע שלכם
        </h3>

        <p>

          הדרך הכי מהירה
          לקבל פרטים
          ולבדוק זמינות
          היא פשוט להתקשר אלינו.

        </p>


        <div class="contact-buttons">

          <a
            href="tel:0772304718"
            class="btn btn-primary"
          >
            חייגו עכשיו · 077-2304718
          </a>


          <a
            href="https://maps.google.com/?q=דרך+הים+1+הוד+השרון"
            target="_blank"
            class="btn btn-outline"
          >
            ניווט למקום
          </a>

        </div>

      </div>


    </div>

  </section>


  <!-- FOOTER -->

  <footer>

    <div class="footer-content">

      <div class="footer-logo">
        החצר האחורית
      </div>

      <div class="footer-text">
        דרך הים 1, הוד השרון · 077-2304718
      </div>

      <div class="footer-text">
        © 2026 החצר האחורית
      </div>

    </div>

  </footer>


  <!-- FLOATING PHONE -->

  <a
    href="tel:0772304718"
    class="floating-phone"
    aria-label="התקשרו אלינו"
  >
    ☎
  </a>


  <!-- JAVASCRIPT -->

  <script>

    /* Navbar */

    const navbar =
      document.getElementById("navbar");

    window.addEventListener(
      "scroll",
      () => {

        if (window.scrollY > 40) {

          navbar.classList.add(
            "scrolled"
          );

        } else {

          navbar.classList.remove(
            "scrolled"
          );

        }

      }
    );


    /* Animations */

    const observer =
      new IntersectionObserver(

        entries => {

          entries.forEach(
            entry => {

              if (
                entry.isIntersecting
              ) {

                entry.target.classList.add(
                  "show"
                );

              }

            }
          );

        },

        {
          threshold: .12
        }

      );


    document
      .querySelectorAll(".reveal")
      .forEach(
        item =>
          observer.observe(item)
      );


    /* Mobile menu */

    const menuBtn =
      document.getElementById(
        "menuBtn"
      );

    const mobileMenu =
      document.getElementById(
        "mobileMenu"
      );


    menuBtn.addEventListener(
      "click",
      () => {

        mobileMenu.classList.toggle(
          "active"
        );

        document.body.classList.toggle(
          "menu-open"
        );

        if (
          mobileMenu.classList.contains(
            "active"
          )
        ) {

          menuBtn.innerHTML =
            "✕";

        } else {

          menuBtn.innerHTML =
            "☰";

        }

      }
    );


    document
      .querySelectorAll(
        ".mobile-menu a"
      )
      .forEach(
        link => {

          link.addEventListener(
            "click",
            () => {

              mobileMenu.classList.remove(
                "active"
              );

              document.body.classList.remove(
                "menu-open"
              );

              menuBtn.innerHTML =
                "☰";

            }
          );

        }
      );

  </script>

</body>
</html>
