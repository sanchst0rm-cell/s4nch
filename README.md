<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SANCH — Archivo &amp; Universo</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,500;0,600;1,400&family=IBM+Plex+Mono:wght@400;500;600&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #08080a;
      --surface: #101014;
      --surface-2: #16161c;
      --ink: #f4f2ee;
      --muted: #a6a3ad;
      --line: rgba(244, 242, 238, 0.14);
      --red: #b81d24;
      --red-bright: #e02833;
      --blue: #1f6fff;
      --pink: #ff4fa3;
      --font-sans: 'Space Grotesk', sans-serif;
      --font-mono: 'IBM Plex Mono', monospace;
      --font-serif: 'Cormorant Garamond', serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      background: var(--bg);
      color: var(--ink);
      font-family: var(--font-sans);
    }

    body {
      background:
        radial-gradient(circle at 12% 8%, rgba(31, 111, 255, 0.13), transparent 36%),
        radial-gradient(circle at 88% 18%, rgba(184, 29, 36, 0.16), transparent 38%),
        radial-gradient(circle at 75% 78%, rgba(255, 79, 163, 0.09), transparent 36%),
        var(--bg);
      color: var(--ink);
      line-height: 1.5;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img, video {
      display: block;
      max-width: 100%;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .container {
      width: min(1140px, 92vw);
      margin: 0 auto;
    }

    /* Header */
    header {
      position: sticky;
      top: 0;
      z-index: 40;
      background: rgba(8, 8, 10, 0.84);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--line);
    }

    .nav-wrap {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      padding: 0.9rem 0;
    }

    .brand {
      display: inline-flex;
      align-items: center;
      gap: 0.65rem;
      font-weight: 700;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      font-size: 1rem;
    }

    .brand-mark {
      width: 30px;
      height: 30px;
      border: 1px solid var(--line);
      border-radius: 4px;
      overflow: hidden;
      background: #141418;
      flex-shrink: 0;
    }

    .brand-tag {
      font-family: var(--font-mono);
      font-size: 0.7rem;
      color: var(--pink);
      letter-spacing: 0.08em;
    }

    nav {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      font-family: var(--font-mono);
      font-size: 0.76rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      color: var(--muted);
    }

    nav a:hover {
      color: var(--ink);
    }

    /* Hero */
    .hero {
      padding: 4.5rem 0 3.2rem;
      border-bottom: 1px solid var(--line);
    }

    .kicker {
      font-family: var(--font-mono);
      font-size: 0.76rem;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      color: var(--blue);
      margin-bottom: 0.9rem;
    }

    h1 {
      font-size: clamp(2.8rem, 8vw, 6.2rem);
      line-height: 0.96;
      letter-spacing: -0.03em;
      text-transform: uppercase;
      margin-bottom: 1.2rem;
    }

    h1 span {
      color: var(--red-bright);
    }

    .hero-copy {
      max-width: 64ch;
      color: var(--muted);
      font-size: 1.04rem;
      margin-bottom: 1.8rem;
    }

    .btn-row {
      display: flex;
      flex-wrap: wrap;
      gap: 0.85rem;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.78rem 1.25rem;
      font-family: var(--font-mono);
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      border: 1px solid var(--line);
      background: var(--surface);
      color: var(--ink);
      cursor: pointer;
      transition: transform 0.18s ease, border-color 0.18s ease, background 0.18s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
      border-color: var(--ink);
    }

    .btn-primary {
      background: var(--red);
      border-color: var(--red);
    }

    .btn-primary:hover {
      background: var(--red-bright);
      border-color: var(--red-bright);
    }

    /* Sections */
    section {
      padding: 3.8rem 0;
      border-bottom: 1px solid var(--line);
    }

    .sec-head {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 0.8rem;
      margin-bottom: 1.8rem;
    }

    h2 {
      font-size: clamp(1.65rem, 3.6vw, 2.5rem);
      text-transform: uppercase;
      letter-spacing: -0.02em;
    }

    .sec-meta {
      font-family: var(--font-mono);
      font-size: 0.76rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.1em;
    }

    /* Bio & Influences */
    .about-grid {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 1.5rem;
    }

    .card {
      background: var(--surface);
      border: 1px solid var(--line);
      padding: 1.4rem;
    }

    .card p + p {
      margin-top: 0.85rem;
    }

    .card p {
      color: var(--muted);
    }

    .editorial-quote {
      font-family: var(--font-serif);
      font-style: italic;
      font-size: 1.35rem;
      color: var(--ink) !important;
      margin-bottom: 0.8rem;
    }

    .chips {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-top: 1rem;
    }

    .chip {
      font-family: var(--font-mono);
      font-size: 0.74rem;
      padding: 0.36rem 0.65rem;
      border: 1px solid var(--line);
      background: var(--surface-2);
      color: var(--ink);
    }

    /* Coming Soon (2 Projects) */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 1.5rem;
    }

    .project-card {
      background: var(--surface);
      border: 1px solid var(--line);
      padding: 1.5rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 1.25rem;
    }

    .project-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 0.75rem;
      font-family: var(--font-mono);
      font-size: 0.72rem;
      text-transform: uppercase;
      letter-spacing: 0.1em;
    }

    .badge-co {
      color: var(--blue);
    }

    .badge-ses {
      color: var(--pink);
    }

    .project-card h3 {
      font-size: 1.65rem;
      text-transform: uppercase;
      margin: 0.45rem 0 0.65rem;
    }

    .project-card p {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .mini-gallery {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 0.6rem;
    }

    .mini-frame {
      aspect-ratio: 4 / 5;
      background: var(--surface-2);
      border: 1px solid var(--line);
      overflow: hidden;
    }

    /* Carrusel */
    .carousel {
      position: relative;
      background: var(--surface);
      border: 1px solid var(--line);
      overflow: hidden;
    }

    .carousel-track {
      display: flex;
      transition: transform 0.35s ease;
    }

    .slide {
      min-width: 100%;
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      align-items: stretch;
    }

    .slide-media {
      aspect-ratio: 16 / 10;
      background: #050507;
      max-height: 460px;
    }

    .slide-caption {
      padding: 1.8rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 0.7rem;
      border-left: 1px solid var(--line);
    }

    .slide-num {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--red-bright);
      letter-spacing: 0.12em;
    }

    .slide-caption h3 {
      font-size: 1.4rem;
      text-transform: uppercase;
    }

    .slide-caption p {
      color: var(--muted);
      font-size: 0.94rem;
    }

    .carousel-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0.85rem 1.2rem;
      border-top: 1px solid var(--line);
      background: var(--surface-2);
    }

    .dots {
      display: flex;
      gap: 0.45rem;
    }

    .dot {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      border: 1px solid var(--ink);
      background: transparent;
      cursor: pointer;
    }

    .dot.active {
      background: var(--red-bright);
      border-color: var(--red-bright);
    }

    /* Portadas & Arte */
    .art-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 1rem;
    }

    .art-card {
      background: var(--surface);
      border: 1px solid var(--line);
      overflow: hidden;
    }

    .art-thumb {
      aspect-ratio: 1 / 1;
      background: var(--surface-2);
    }

    .art-meta {
      padding: 0.8rem;
    }

    .art-meta strong {
      display: block;
      font-size: 0.9rem;
      text-transform: uppercase;
    }

    .art-meta span {
      font-family: var(--font-mono);
      font-size: 0.72rem;
      color: var(--muted);
    }

    /* Galería General */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(5, minmax(0, 1fr));
      gap: 0.75rem;
    }

    .gallery-item {
      aspect-ratio: 4 / 5;
      background: var(--surface);
      border: 1px solid var(--line);
      overflow: hidden;
    }

    /* Clips & VHS */
    .videos-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 1rem;
    }

    .video-card {
      background: var(--surface);
      border: 1px solid var(--line);
      overflow: hidden;
      display: flex;
      flex-direction: column;
    }

    .video-frame {
      aspect-ratio: 9 / 16;
      background: #050507;
    }

    .video-meta {
      padding: 0.75rem;
      font-family: var(--font-mono);
      font-size: 0.72rem;
      color: var(--muted);
      word-break: break-word;
    }

    /* Contact & QRs */
    .contact-grid {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 1.5rem;
      align-items: start;
    }

    .qr-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1rem;
    }

    .qr-box {
      background: var(--surface);
      border: 1px solid var(--line);
      padding: 0.9rem;
      text-align: center;
      display: block;
      transition: transform 0.18s ease, border-color 0.18s ease;
    }

    .qr-box:hover {
      transform: translateY(-2px);
      border-color: var(--ink);
    }

    .qr-img {
      aspect-ratio: 1 / 1;
      margin-bottom: 0.65rem;
      border: 1px solid var(--line);
      overflow: hidden;
    }

    .qr-box span {
      font-family: var(--font-mono);
      font-size: 0.72rem;
      color: var(--muted);
      display: block;
    }

    /* Agradecimientos */
    .credits-box {
      background: var(--surface);
      border: 1px solid var(--line);
      padding: 1.8rem;
      display: grid;
      gap: 1rem;
    }

    .credits-box p {
      color: var(--muted);
      font-size: 0.98rem;
      max-width: 72ch;
    }

    .credits-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.55rem;
    }

    .credit-tag {
      font-family: var(--font-mono);
      font-size: 0.76rem;
      padding: 0.38rem 0.72rem;
      border: 1px solid var(--line);
      background: var(--surface-2);
      color: var(--ink);
    }

    .credit-tag.highlight {
      border-color: rgba(255, 79, 163, 0.45);
      color: var(--pink);
    }

    footer {
      padding: 2rem 0 2.8rem;
      font-family: var(--font-mono);
      font-size: 0.76rem;
      color: var(--muted);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1rem;
    }

    @media (max-width: 960px) {
      .gallery-grid {
        grid-template-columns: repeat(3, minmax(0, 1fr));
      }
      .videos-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
    }

    @media (max-width: 860px) {
      .about-grid,
      .projects-grid,
      .slide,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .slide-caption {
        border-left: none;
        border-top: 1px solid var(--line);
      }

      .art-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
    }

    @media (max-width: 520px) {
      .art-grid,
      .qr-grid,
      .gallery-grid,
      .videos-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav-wrap">
      <a href="#top" class="brand">
        <span class="brand-mark">
          <img src="img/WhatsApp Image 2026-11-22 at 12.58.10.jpeg" alt="Logo SANCH" />
        </span>
        <span>SANCH</span>
        <span class="brand-tag">// ARCHIVO</span>
      </a>
      <nav>
        <a href="#bio">Bio</a>
        <a href="#coming-soon">Coming Soon</a>
        <a href="#universo">Universo</a>
        <a href="#arte">Arte</a>
        <a href="#galeria">Galería</a>
        <a href="#clips">Clips</a>
        <a href="#contacto">Contacto</a>
        <a href="#agradecimientos">Créditos</a>
      </nav>
    </div>
  </header>

  <main id="top">
    <section class="hero">
      <div class="container">
        <p class="kicker">Producción independiente en REAPER · Géneros abiertos · Bitácora visual</p>
        <h1>SANCH <span>//</span> CO2027 &amp; SESIONES</h1>
        <p class="hero-copy">
          Proyecto musical y archivo personal construido desde el proceso real: madrugadas en REAPER, controladores MIDI, libretas, calle, escuela y bocetos que no pasan por filtro comercial.
        </p>
        <div class="btn-row">
          <a href="#coming-soon" class="btn btn-primary">Ver Coming Soon</a>
          <a href="https://on.soundcloud.com/z0E8w54EnT9iT2VSHH" target="_blank" rel="noopener noreferrer" class="btn">SoundCloud</a>
          <a href="https://untitled.stream/library/project/dXDLftPcKgPc1XdxYsfVB" target="_blank" rel="noopener noreferrer" class="btn">Untitled</a>
          <a href="https://instagram.com/S4N_CHXX" target="_blank" rel="noopener noreferrer" class="btn">Instagram</a>
          <a href="mailto:sanch.st0rm@gmail.com" class="btn">Correo</a>
        </div>
      </div>
    </section>

    <section id="bio">
      <div class="container">
        <div class="sec-head">
          <h2>Identidad &amp; Referencias</h2>
          <span class="sec-meta">01 / BIOGRAFÍA</span>
        </div>
        <div class="about-grid">
          <div class="card">
            <p class="editorial-quote">“No separo lo que vivo de lo que grabo; cada carpeta, nota o sesión es parte del mismo registro.”</p>
            <p>
              Soy SANCH. Produzco en REAPER abriendo el abanico de géneros según lo que pida cada idea, mezclando experimentación en el DAW, instrumentación casera y vivencias cotidianas que van tomando forma en <strong>Co2027</strong> y <strong>Sesiones</strong>.
            </p>
            <p>
              Este espacio funciona como archivo directo y bitácora visual sin adornos innecesarios.
            </p>
          </div>
          <div class="card">
            <p><strong>Referencias que resuenan:</strong></p>
            <div class="chips">
              <span class="chip">NSQK</span>
              <span class="chip">Wos</span>
              <span class="chip">Latin Mafia</span>
              <span class="chip">Easykid</span>
              <span class="chip">Jaze</span>
              <span class="chip">Kanye West</span>
              <span class="chip">Kevis &amp; Maykyy</span>
              <span class="chip">Álvaro Díaz</span>
              <span class="chip">Ca7riel &amp; Paco Amoroso</span>
              <span class="chip">Akrilla</span>
              <span class="chip">Bad Bunny</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="coming-soon">
      <div class="container">
        <div class="sec-head">
          <h2>Coming Soon</h2>
          <span class="sec-meta">02 / DOS PROYECTOS EN MARCHA</span>
        </div>
        <div class="projects-grid">
          <article class="project-card">
            <div>
              <div class="project-top">
                <span class="badge-co">Proyecto 01 · Co2027</span>
                <span>Class of 2027</span>
              </div>
              <h3>Co2027</h3>
              <p>
                Crónica sonora y visual nacida de la etapa escolar, las amistades, las caminatas y las experiencias propias y de terceros que empujan el crecimiento personal y creativo.
              </p>
            </div>
            <div class="mini-gallery">
              <div class="mini-frame">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (1).jpeg" alt="Co2027 archivo 1" />
              </div>
              <div class="mini-frame">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (2).jpeg" alt="Co2027 archivo 2" />
              </div>
              <div class="mini-frame">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (3).jpeg" alt="Co27 archivo 3" />
              </div>
            </div>
            <div class="btn-row">
              <a href="https://on.soundcloud.com/z0E8w54EnT9iT2VSHH" target="_blank" rel="noopener noreferrer" class="btn">Escuchar en SoundCloud</a>
              <a href="#contacto" class="btn">Seguir avance</a>
            </div>
          </article>

          <article class="project-card">
            <div>
              <div class="project-top">
                <span class="badge-ses">Proyecto 02 · Sesiones</span>
                <span>Demos &amp; Beats</span>
              </div>
              <h3>Sesiones</h3>
              <p>
                Espacio para beats, pruebas de mezcla, cortes, automatizaciones y bocetos en bruto que nacen en el estudio y viven en Untitled antes de decidir su destino final.
              </p>
            </div>
            <div class="mini-gallery">
              <div class="mini-frame">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (4).jpeg" alt="Sesiones archivo 1" />
              </div>
              <div class="mini-frame">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (5).jpeg" alt="Sesiones archivo 2" />
              </div>
              <div class="mini-frame">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (6).jpeg" alt="Sesiones archivo 3" />
              </div>
            </div>
            <div class="btn-row">
              <a href="https://untitled.stream/library/project/dXDLftPcKgPc1XdxYsfVB" target="_blank" rel="noopener noreferrer" class="btn btn-primary">Abrir en Untitled</a>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="universo">
      <div class="container">
        <div class="sec-head">
          <h2>Cómo Construyo Este Universo</h2>
          <span class="sec-meta">03 / CARRUSEL DE PROCESO</span>
        </div>
        <div class="carousel" id="carousel">
          <div class="carousel-track" id="carouselTrack">
            <div class="slide">
              <div class="slide-media">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (7).jpeg" alt="Universo slide 1" />
              </div>
              <div class="slide-caption">
                <span class="slide-num">SLIDE 01 / 04</span>
                <h3>Estudio &amp; Sesiones</h3>
                <p>El punto de partida diario: armar capas, probar sonidos y mover ideas hasta que algo empieza a tomar forma.</p>
              </div>
            </div>

            <div class="slide">
              <div class="slide-media">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (8).jpeg" alt="Universo slide 2" />
              </div>
              <div class="slide-caption">
                <span class="slide-num">SLIDE 02 / 04</span>
                <h3>Bitácora y espacio</h3>
                <p>Objetos, notas y momentos alrededor del trabajo diario donde se mezclan ideas pendientes y pausas.</p>
              </div>
            </div>

            <div class="slide">
              <div class="slide-media">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (9).jpeg" alt="Universo slide 3" />
              </div>
              <div class="slide-caption">
                <span class="slide-num">SLIDE 03 / 04</span>
                <h3>Estética y dirección</h3>
                <p>Referencias visuales que conectan lo que suena con el tono crudo y directo del proyecto.</p>
              </div>
            </div>

            <div class="slide">
              <div class="slide-media">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (10).jpeg" alt="Universo slide 4" />
              </div>
              <div class="slide-caption">
                <span class="slide-num">SLIDE 04 / 04</span>
                <h3>Escucha y proceso</h3>
                <p>Capturas y registros que acompañan el pulso y la evolución de SANCH.</p>
              </div>
            </div>
          </div>

          <div class="carousel-controls">
            <div class="btn-row">
              <button type="button" class="btn" id="prevBtn">Anterior</button>
              <button type="button" class="btn" id="nextBtn">Siguiente</button>
            </div>
            <div class="dots" id="carouselDots" aria-label="Indicadores de diapositiva"></div>
          </div>
        </div>
      </div>
    </section>

    <section id="arte">
      <div class="container">
        <div class="sec-head">
          <h2>Portadas &amp; Arte</h2>
          <span class="sec-meta">04 / PIEZAS VISUALES</span>
        </div>
        <div class="art-grid">
          <article class="art-card">
            <div class="art-thumb">
              <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (11).jpeg" alt="Arte 01" />
            </div>
            <div class="art-meta">
              <strong>Pieza 01</strong>
              <span>Portada / Visual</span>
            </div>
          </article>

          <article class="art-card">
            <div class="art-thumb">
              <img src="img/WhatsApp Image 2026-11-22 at 12.58.11.jpeg" alt="Arte 02" />
            </div>
            <div class="art-meta">
              <strong>Pieza 02</strong>
              <span>Arte / Identidad</span>
            </div>
          </article>

          <article class="art-card">
            <div class="art-thumb">
              <img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (1).jpeg" alt="Arte 03" />
            </div>
            <div class="art-meta">
              <strong>Pieza 03</strong>
              <span>Boceto / Gráfica</span>
            </div>
          </article>

          <article class="art-card">
            <div class="art-thumb">
              <img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (2).jpeg" alt="Arte 04" />
            </div>
            <div class="art-meta">
              <strong>Pieza 04</strong>
              <span>Archivo Visual</span>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="galeria">
      <div class="container">
        <div class="sec-head">
          <h2>Galería General</h2>
          <span class="sec-meta">05 / 75 IMÁGENES DEL ARCHIVO</span>
        </div>
        <div class="gallery-grid">
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (3).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (4).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (5).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (6).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (7).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (8).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (9).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (10).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (11).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (12).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (13).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.11 (14).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13.jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (1).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (2).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (3).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (4).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (5).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (6).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (7).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (8).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (9).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (10).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (11).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (12).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (13).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (14).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (15).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (16).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (17).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (18).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (19).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (20).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (21).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (22).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (23).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (24).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (25).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (26).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (27).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (28).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (29).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (30).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (31).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (32).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (33).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (34).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (35).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (36).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (37).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (38).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (39).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (40).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (41).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (42).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (43).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (44).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (45).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (46).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (47).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (48).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (49).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (50).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (51).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (52).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (53).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (54).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (55).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (56).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (57).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (58).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (59).jpeg" alt="Galería SANCH" /></div>
          <div class="gallery-item"><img src="img/WhatsApp Image 2026-11-22 at 12.58.13 (60).jpeg" alt="Galería SANCH" /></div>
        </div>
      </div>
    </section>

    <section id="clips">
      <div class="container">
        <div class="sec-head">
          <h2>Clips &amp; Videos</h2>
          <span class="sec-meta">06 / 8 VIDEOS DEL ARCHIVO</span>
        </div>
        <div class="videos-grid">
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13.mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13.mp4</div>
          </article>
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13 (1).mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13 (1).mp4</div>
          </article>
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13 (2).mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13 (2).mp4</div>
          </article>
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13 (3).mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13 (3).mp4</div>
          </article>
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13 (4).mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13 (4).mp4</div>
          </article>
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13 (5).mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13 (5).mp4</div>
          </article>
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13 (6).mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13 (6).mp4</div>
          </article>
          <article class="video-card">
            <div class="video-frame"><video src="img/WhatsApp Video 2026-11-22 at 12.58.13 (7).mp4" controls muted playsinline preload="metadata"></video></div>
            <div class="video-meta">WhatsApp Video 2026-11-22 at 12.58.13 (7).mp4</div>
          </article>
        </div>
      </div>
    </section>

    <section id="contacto">
      <div class="container">
        <div class="sec-head">
          <h2>Contacto &amp; Enlaces</h2>
          <span class="sec-meta">07 / CONEXIÓN DIRECTA</span>
        </div>
        <div class="contact-grid">
          <div class="card">
            <p><strong>SoundCloud:</strong> <a href="https://on.soundcloud.com/z0E8w54EnT9iT2VSHH" target="_blank" rel="noopener noreferrer">Perfil oficial de SANCH</a></p>
            <p><strong>Demos &amp; Sesiones:</strong> <a href="https://untitled.stream/library/project/dXDLftPcKgPc1XdxYsfVB" target="_blank" rel="noopener noreferrer">Proyecto en Untitled</a></p>
            <p><strong>Instagram:</strong> <a href="https://instagram.com/S4N_CHXX" target="_blank" rel="noopener noreferrer">@S4N_CHXX</a></p>
            <p><strong>Correo directo:</strong> <a href="mailto:sanch.st0rm@gmail.com">sanch.st0rm@gmail.com</a></p>
            <div class="btn-row" style="margin-top: 1.2rem;">
              <a href="https://on.soundcloud.com/z0E8w54EnT9iT2VSHH" target="_blank" rel="noopener noreferrer" class="btn btn-primary">Ir a SoundCloud</a>
              <a href="https://untitled.stream/library/project/dXDLftPcKgPc1XdxYsfVB" target="_blank" rel="noopener noreferrer" class="btn">Ir a Untitled</a>
              <a href="https://instagram.com/S4N_CHXX" target="_blank" rel="noopener noreferrer" class="btn">Ir a Instagram</a>
              <a href="mailto:sanch.st0rm@gmail.com" class="btn">Mandar correo</a>
            </div>
          </div>

          <div class="qr-grid">
            <a href="https://on.soundcloud.com/z0E8w54EnT9iT2VSHH" target="_blank" rel="noopener noreferrer" class="qr-box">
              <div class="qr-img">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (2).jpeg" alt="Acceso SoundCloud SANCH" />
              </div>
              <strong>SoundCloud</strong>
              <span>Tracks &amp; Perfil</span>
            </a>
            <a href="https://untitled.stream/library/project/dXDLftPcKgPc1XdxYsfVB" target="_blank" rel="noopener noreferrer" class="qr-box">
              <div class="qr-img">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (4).jpeg" alt="Acceso Untitled / Sesiones" />
              </div>
              <strong>Untitled</strong>
              <span>Sesiones &amp; Demos</span>
            </a>
            <a href="https://instagram.com/S4N_CHXX" target="_blank" rel="noopener noreferrer" class="qr-box">
              <div class="qr-img">
                <img src="img/WhatsApp Image 2026-11-22 at 12.58.10 (1).jpeg" alt="Acceso Instagram SANCH" />
              </div>
              <strong>Instagram</strong>
              <span>@S4N_CHXX</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <section id="agradecimientos">
      <div class="container">
        <div class="sec-head">
          <h2>Agradecimientos</h2>
          <span class="sec-meta">08 / CRÉDITOS PERSONALES</span>
        </div>
        <div class="credits-box">
          <p class="editorial-quote">“Nada de esto existiría sin quienes sostienen cada paso fuera y dentro del estudio.”</p>
          <p>
            Gracias de corazón a mi mamá, a mi papá, a mi hermana y a toda mi familia por estar siempre. A mis amigos <strong>Alexa, Iker, Pedro y Gabriel</strong>, a los amigos del <strong>5MJ</strong> por las historias, la compañía y la vibra de cada día, y especialmente a <strong>ustedes que están leyendo esto</strong> y se toman el tiempo de entrar a este archivo.
          </p>
          <div class="credits-list">
            <span class="credit-tag">Mamá</span>
            <span class="credit-tag">Papá</span>
            <span class="credit-tag">Hermana</span>
            <span class="credit-tag">Familia</span>
            <span class="credit-tag">Alexa</span>
            <span class="credit-tag">Iker</span>
            <span class="credit-tag">Pedro</span>
            <span class="credit-tag">Gabriel</span>
            <span class="credit-tag">Amigos del 5MJ</span>
            <span class="credit-tag highlight">Ustedes que lo leen</span>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container" style="display:flex; justify-content:space-between; flex-wrap:wrap; gap:1rem; width:100%;">
      <span>SANCH · sanch.st0rm@gmail.com</span>
      <span>Co2027 &amp; Sesiones · Archivo personal</span>
    </div>
  </footer>

  <script>
    const track = document.getElementById('carouselTrack');
    const slides = Array.from(track.children);
    const prevBtn = document.getElementById('prevBtn');
    const nextBtn = document.getElementById('nextBtn');
    const dotsWrap = document.getElementById('carouselDots');
    let index = 0;

    slides.forEach((_, idx) => {
      const dot = document.createElement('button');
      dot.type = 'button';
      dot.className = 'dot' + (idx === 0 ? ' active' : '');
      dot.setAttribute('aria-label', `Ir a diapositiva ${idx + 1}`);
      dot.addEventListener('click', () => goToSlide(idx));
      dotsWrap.appendChild(dot);
    });

    const dots = Array.from(dotsWrap.children);

    function goToSlide(newIndex) {
      index = (newIndex + slides.length) % slides.length;
      track.style.transform = `translateX(-${index * 100}%)`;
      dots.forEach((dot, i) => dot.classList.toggle('active', i === index));
    }

    prevBtn.addEventListener('click', () => goToSlide(index - 1));
    nextBtn.addEventListener('click', () => goToSlide(index + 1));
  </script>
</body>
</html> 
