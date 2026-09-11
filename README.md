# olafsamu.github.io
willemijn-clicker
<!doctype html>
<html lang="nl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <meta name="theme-color" content="#007bff" />
  <title>Mijn Moderne Website</title>
  <style>
    :root{
      --bg: #f9f9f9;
      --card-bg: #ffffff;
      --text: #333;
      --muted: #666;
      --accent: #007bff;
      --accent-2: #00d2ff;
      --surface: #2c3e50;
      --radius: 8px;
      --container: 1100px;
      --gap: 1.5rem;
      --shadow: 0 4px 10px rgba(0,0,0,0.06);
      --transition: 0.2s ease;
      font-synthesis: none;
    }

    /* Basis + reset */
    *,*::before,*::after{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      line-height:1.6;
      color:var(--text);
      background:var(--bg);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    /* Visually-hidden helper */
    .sr-only{
      position:absolute!important;
      width:1px;height:1px;
      padding:0;margin:-1px;overflow:hidden;
      clip:rect(0 0 0 0);white-space:nowrap;border:0;
    }

    /* Skip link */
    .skip-link{
      position:fixed;
      left:1rem;
      top:0.75rem;
      background:#000;
      color:#fff;
      padding:0.5rem 0.75rem;
      border-radius:4px;
      z-index:9999;
      transform:translateY(-120%);
      transition:transform var(--transition);
      text-decoration:none;
      font-size:0.9rem;
    }
    .skip-link:focus{transform:none; outline:3px solid #fff}

    /* Header / nav */
    header{
      background:var(--card-bg);
      box-shadow:0 2px 10px rgba(0,0,0,0.06);
      position:sticky;top:0;z-index:1000;
    }
    .nav-inner{
      max-width:var(--container);
      margin:0 auto;
      padding:1rem 1.25rem;
      display:flex;
      align-items:center;
      gap:1rem;
      justify-content:space-between;
    }
    .logo{
      font-weight:700;
      color:var(--surface);
      text-decoration:none;
      display:inline-flex;
      align-items:center;
      gap:0.5rem;
      font-size:1.125rem;
    }

    /* Mobile menu button */
    .menu-btn{
      display:inline-flex;
      align-items:center;
      gap:0.5rem;
      background:none;
      border:0;
      color:var(--text);
      font-size:1rem;
      cursor:pointer;
    }
    .menu-btn:focus{outline:3px solid var(--accent); border-radius:6px; padding:2px}

    nav ul{
      list-style:none;
      display:flex;
      gap:var(--gap);
      align-items:center;
      margin:0;
      padding:0;
    }
    nav a{
      text-decoration:none;
      color:#555;
      font-weight:500;
      transition:color var(--transition);
    }
    nav a:hover, nav a:focus{color:var(--accent)}

    /* Responsive: hide desktop menu on small screens */
    .nav-links{display:flex}
    @media (max-width:740px){
      .nav-links{display:none; position:absolute; right:1rem; top:64px;
        background:var(--card-bg); padding:1rem; border-radius:8px; box-shadow:var(--shadow); flex-direction:column;}
      .nav-links.show{display:flex}
    }

    /* Hero */
    .hero{
      color:#fff;
      padding:4.5rem 1.25rem;
      text-align:center;
      background:linear-gradient(135deg,var(--accent),var(--accent-2));
      clip-path:ellipse(100% 100% at 50% 0%);
    }
    .container{max-width:var(--container); margin:0 auto; padding:0 1.25rem}

    .hero h1{
      font-size:clamp(1.8rem, 4vw, 2.8rem);
      margin-bottom:0.75rem;
      line-height:1.05;
    }
    .hero p{
      max-width:60ch;
      margin:0.5rem auto 1.5rem;
      font-size:clamp(1rem, 2.2vw, 1.125rem);
      color:rgba(255,255,255,0.95);
    }
    .btn{
      display:inline-block;
      background:#fff;color:var(--accent);
      padding:0.65rem 1.5rem;border-radius:999px;
      text-decoration:none;font-weight:700;
      transition:transform var(--transition), box-shadow var(--transition);
      box-shadow:0 6px 18px rgba(0,0,0,0.08);
    }
    .btn:focus{outline:3px solid rgba(255,255,255,0.3)}
    .btn:hover{transform:translateY(-4px)}

    /* Features */
    .features{
      margin:2.25rem auto;
      padding:0 1.25rem 3rem;
      display:grid;
      gap:1.5rem;
      grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
      max-width:var(--container);
    }
    .card{
      background:var(--card-bg);
      padding:1.5rem;
      border-radius:var(--radius);
      box-shadow:var(--shadow);
      text-align:center;
      transition:transform var(--transition), box-shadow var(--transition);
    }
    .card:hover{transform:translateY(-6px)}
    .card h3{color:var(--surface); margin-bottom:0.5rem}
    .card p{color:var(--muted); font-size:0.95rem}

    /* Footer */
    footer{
      background:var(--surface);
      color:#fff;
      text-align:center;
      padding:1.5rem 1rem;
      margin-top:2.5rem;
    }

    /* Focus-visible only (preferred) */
    :focus{outline:none}
    :focus-visible{outline:3px solid var(--accent); outline-offset:2px; border-radius:6px}

    /* Reduced motion */
    @media (prefers-reduced-motion:reduce){
      *{transition:none!important; animation:none!important}
    }
  </style>
</head>
<body>

  <a class="skip-link" href="#main">Sla navigatie over</a>

  <header>
    <div class="nav-inner">
      <a class="logo" href="#" aria-label="Mijn website - naar start">MijnLogo</a>

      <button class="menu-btn" id="menuBtn" aria-expanded="false" aria-controls="primary-navigation">
        <span aria-hidden="true">☰</span>
        <span class="sr-only">Navigatie openen</span>
      </button>

      <nav role="navigation" aria-label="Hoofdnavigatie">
        <ul id="primary-navigation" class="nav-links" data-visible="false">
          <li><a href="#">Home</a></li>
          <li><a href="#">Over ons</a></li>
          <li><a href="#diensten">Diensten</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main id="main" tabindex="-1">
    <section class="hero" aria-labelledby="hero-title">
      <div class="container">
        <h1 id="hero-title">Welkom op onze website</h1>
        <p>Wij bouwen moderne, snelle en gebruiksvriendelijke oplossingen voor al jouw digitale wensen.</p>
        <a class="btn" href="#diensten">Ontdek meer</a>
      </div>
    </section>

    <section class="features" id="diensten" aria-labelledby="diensten-title">
      <h2 id="diensten-title" class="sr-only">Onze diensten</h2>

      <div class="card" role="article" aria-labelledby="f1">
        <h3 id="f1">Snel &amp; Betrouwbaar</h3>
        <p>Onze oplossingen zijn geoptimaliseerd voor snelheid en maximale uptime.</p>
      </div>

      <div class="card" role="article" aria-labelledby="f2">
        <h3 id="f2">Modern Design</h3>
        <p>Een strak ontwerp dat op elk apparaat (mobiel, tablet, pc) perfect werkt.</p>
      </div>

      <div class="card" role="article" aria-labelledby="f3">
        <h3 id="f3">24/7 Support</h3>
        <p>Ons team staat altijd klaar om je te helpen met vragen of problemen.</p>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <p>&copy; 2026 Mijn Website. Alle rechten voorbehouden.</p>
    </div>
  </footer>

  <script>
    // Kleine, toegankelijke menu-toggle (houd eenvoudig en semantisch)
    (function(){
      const btn = document.getElementById('menuBtn');
      const nav = document.getElementById('primary-navigation');

      btn.addEventListener('click', () => {
        const expanded = btn.getAttribute('aria-expanded') === 'true';
        btn.setAttribute('aria-expanded', String(!expanded));
        nav.classList.toggle('show');
        // Update visible attribute for styling or tests
        nav.setAttribute('data-visible', String(!expanded));
      });

      // Sluit menu met Escape-toets
      document.addEventListener('keydown', (e) => {
        if(e.key === 'Escape' && nav.classList.contains('show')){
          btn.setAttribute('aria-expanded','false');
          nav.classList.remove('show');
          nav.setAttribute('data-visible','false');
          btn.focus();
        }
      });
    })();
  </script>
</body>
</html>
