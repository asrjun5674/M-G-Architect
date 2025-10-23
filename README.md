<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>M&G Architect — Unveiling architectural excellence</title>
<meta name="description" content="M&G Architect — portfolio showcasing iconic architecture, case studies and design thinking." />
<style>
  /* ================ Reset & base ================ */
  :root{
    --bg-light: #ffffff;
    --text-light: #0b1220;
    --muted-light: #6b7280;
    --accent: #e6b05a;
    --bg-dark: #071021;
    --card-dark: #071726;
    --text-dark: #e6eef6;
    --muted-dark: #9aa6b2;
    --maxw: 1200px;
    --radius:14px;
    --gap:20px;
    --ff-system: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  }
  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0;font-family:var(--ff-system);line-height:1.45;
    background:var(--bg-dark);color:var(--text-dark);
    -webkit-font-smoothing:antialiased;-moz-osx-font-smoothing:grayscale;
  }
  .wrap{max-width:var(--maxw);margin:0 auto;padding:0 20px}

  /* ===== Theme handling (light/dark) ===== */
  body.theme-dark{
    background:linear-gradient(180deg,#061021 0%, #071428 60%);
    color:var(--text-dark);
  }
  body.theme-light{
    background:var(--bg-light);
    color:var(--text-light);
  }

  /* ===== Header / Nav ===== */
  header{
    display:flex;align-items:center;justify-content:space-between;padding:22px 0;
    gap:12px;position:relative;z-index:40;
  }
  .brand{display:flex;align-items:center;gap:12px;text-decoration:none;color:inherit}
  .logo{
    width:64px;height:64px;border-radius:12px;display:grid;place-items:center;font-weight:800;
    background:linear-gradient(135deg,var(--accent),#ffcf94);color:#07202a;font-family: Georgia, serif;
    box-shadow:0 8px 26px rgba(0,0,0,0.35);
  }
  .brand .title{font-weight:800;font-size:18px;letter-spacing:0.4px}
  .brand .subtitle{font-size:12px;color:inherit;opacity:.75}

  nav{display:flex;gap:12px;align-items:center}
  nav a{color:inherit;text-decoration:none;padding:8px 12px;border-radius:10px;font-weight:600;opacity:.9}
  nav a:hover{opacity:1;background:rgba(255,255,255,0.03)}

  .controls{display:flex;gap:10px;align-items:center}
  .btn{
    background:var(--accent);color:#07202a;padding:10px 14px;border-radius:10px;font-weight:800;border:0;cursor:pointer;
  }
  .ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:8px 10px;border-radius:10px;cursor:pointer}

  /* ===== Hero (fullscreen) ===== */
  #hero{
    position:relative;height:100vh;min-height:560px;display:flex;align-items:center;justify-content:center;
    overflow:hidden;margin-bottom:40px;border-radius:0;
  }
  #hero .media{
    position:absolute;inset:0;overflow:hidden;z-index:0;
  }
  #hero img, #hero video{
    width:100%;height:100%;object-fit:cover;display:block;transform:scale(1.03);
    filter:contrast(.98) saturate(.95);
  }
  #hero .overlay{
    position:absolute;inset:0;background:linear-gradient(180deg, rgba(6,14,25,0.45), rgba(6,10,16,0.45));z-index:1;
  }
  #hero .content{
    position:relative;z-index:2;text-align:center;color:#fff;padding:20px;max-width:1100px;
    animation:fadeUp .9s ease;
  }
  #hero h1{font-size:clamp(28px,6vw,64px);margin:0 0 12px;line-height:1.02;letter-spacing:0.4px}
  #hero p{margin:0 0 18px;color:rgba(255,255,255,0.9);font-size:1.05rem}

  /* small control row in hero */
  .hero-controls{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin-top:12px}

  @keyframes fadeUp{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:none}}

  /* ===== Projects area ===== */
  section.projects{padding:48px 0}
  .projects-top{display:flex;align-items:end;justify-content:space-between;gap:12px;margin-bottom:22px}
  .projects-top h2{margin:0;font-size:28px}
  .view-switch{display:flex;gap:8px;align-items:center}

  /* grid */
  .grid{
    display:grid;gap:var(--gap);grid-template-columns:repeat(3,1fr);
  }
  .card{
    background:rgba(0,0,0,0.35);border-radius:var(--radius);overflow:hidden;cursor:pointer;position:relative;
    box-shadow:0 10px 30px rgba(2,6,23,0.5);
    transition:transform .28s ease, box-shadow .28s ease;
  }
  .card img{width:100%;height:260px;object-fit:cover;display:block}
  .card .meta{padding:14px}
  .card h3{margin:0 0 8px;font-size:18px}
  .card p{margin:0;color:rgba(255,255,255,0.85);opacity:.9}

  .card:hover{transform:translateY(-8px);box-shadow:0 22px 50px rgba(2,6,23,0.6)}

  /* horizontal showcase */
  .showcase{
    display:flex;gap:18px;overflow-x:auto;padding-bottom:12px;scroll-snap-type:x mandatory;
  }
  .showcase .card{min-width:86%;scroll-snap-align:center;flex:0 0 86%}
  .showcase .card img{height:64vh;max-height:700px;object-fit:cover}

  /* responsive */
  @media (max-width:1000px){
    .grid{grid-template-columns:repeat(2,1fr)}
    nav{display:none}
  }
  @media (max-width:640px){
    .grid{grid-template-columns:1fr}
    .showcase .card{min-width:92%}
    header{padding:14px 0}
    .brand .title{font-size:16px}
  }

  /* ===== Project modal / case study ===== */
  .modal{
    position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:linear-gradient(180deg, rgba(0,0,0,0.8), rgba(0,0,0,0.9));z-index:120;
  }
  .modal .sheet{
    width:min(1200px,96%);max-height:92vh;overflow:auto;background:rgba(6,10,16,0.96);border-radius:12px;padding:20px;color:var(--text-dark);
  }
  .modal .gallery{display:grid;grid-template-columns:1fr 380px;gap:18px}
  .modal .gallery img{width:100%;height:auto;border-radius:10px}
  .close-x{position:absolute;right:22px;top:22px;background:rgba(255,255,255,0.05);border:0;padding:8px;border-radius:10px;cursor:pointer;color:#fff}

  /* ===== Contact form ===== */
  section.contact{padding:48px 0;background:transparent}
  form.contact-form{max-width:680px;margin:0 auto;background:rgba(255,255,255,0.02);padding:22px;border-radius:10px}
  label{display:block;font-size:13px;margin-bottom:6px;color:rgba(255,255,255,0.9)}
  input,textarea,select{width:100%;padding:12px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit;margin-bottom:12px}
  input::placeholder, textarea::placeholder{opacity:.6}
  .small{font-size:13px;color:rgba(255,255,255,0.8)}

  /* footer */
  footer{padding:28px 0;text-align:center;color:rgba(255,255,255,0.7);margin-top:22px}

  /* theme light overrides */
  body.theme-light .card{background:linear-gradient(180deg,#fff,#fbfbfb);box-shadow:0 8px 28px rgba(12,16,20,0.06)}
  body.theme-light .card p{color:var(--muted-light)}
  body.theme-light .modal .sheet{background:#fff;color:var(--text-light)}
  body.theme-light form.contact-form{background:#fff;border:1px solid #eee;color:var(--text-light)}
  body.theme-light .close-x{color:var(--text-light)}
  body.theme-light nav a:hover{background:rgba(0,0,0,0.04)}
</style>
</head>
<body class="theme-dark">
  <div class="wrap">
    <header>
      <a class="brand" href="#hero">
        <div class="logo">M&amp;G</div>
        <div>
          <div class="title">M&amp;G Architect</div>
          <div class="subtitle">Unveiling architectural excellence</div>
        </div>
      </a>

      <nav aria-label="Primary">
        <a href="#projects">Projects</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>

      <div class="controls">
        <button id="themeToggle" class="ghost" title="Toggle theme">Light</button>
        <button id="videoToggle" class="ghost" title="Toggle hero video">Video</button>
        <button id="layoutToggle" class="ghost" title="Toggle projects layout">Showcase</button>
        <a class="btn" href="#projects">Discover</a>
      </div>
    </header>
  </div>

  <!-- HERO -->
  <main id="hero" aria-label="Intro hero">
    <div class="media" id="heroMedia">
      <!-- Video (optional) -->
      <video id="heroVideo" playsinline muted loop preload="metadata" style="display:none">
        <!-- Replace 'hero-video.mp4' with your hosted MP4 or remove the tag if you don't want a video -->
        <source src="hero-video.mp4" type="video/mp4">
        <!-- fallback image handled below -->
      </video>

      <!-- Large fallback image -->
      <img id="heroImg" alt="Featured project" src="https://source.unsplash.com/1920x1080/?architecture,building,city">
    </div>

    <div class="overlay" aria-hidden="true"></div>

    <div class="content">
      <h1>M&amp;G Architect</h1>
      <p>Unveiling architectural excellence &amp; design innovation — a project-first studio site to showcase buildings, process and ideas.</p>

      <div class="hero-controls">
        <a class="btn" href="#projects">View Projects</a>
        <a class="ghost" href="#about">Our Approach</a>
      </div>
    </div>
  </main>

  <!-- PROJECTS -->
  <section id="projects" class="projects wrap" aria-labelledby="projectsLabel">
    <div class="projects-top">
      <h2 id="projectsLabel">Selected Projects</h2>
      <div class="view-switch">
        <div class="small" style="margin-right:8px">Layout:</div>
        <button id="toGrid" class="ghost">Grid</button>
        <button id="toShowcase" class="ghost">Showcase</button>
      </div>
    </div>

    <!-- Grid container (default hidden when showcase active) -->
    <div id="gridView" class="grid">
      <!-- Project card 1 -->
      <article class="card" tabindex="0" data-id="p1" aria-label="Open project Cliffside Residence">
        <img src="https://source.unsplash.com/1200x800/?house,cliff" alt="Cliffside Residence">
        <div class="meta">
          <h3>Cliffside Residence</h3>
          <p class="small">A private residence balancing views, privacy and passive cooling strategies.</p>
        </div>
      </article>

      <article class="card" tabindex="0" data-id="p2" aria-label="Open project Glassframe Tower">
        <img src="https://source.unsplash.com/1200x800/?glass,building" alt="Glassframe Tower">
        <div class="meta">
          <h3>Glassframe Tower</h3>
          <p class="small">Commercial tower rethinking transparency and shading on a narrow urban lot.</p>
        </div>
      </article>

      <article class="card" tabindex="0" data-id="p3" aria-label="Open project Riverside Cultural Centre">
        <img src="https://source.unsplash.com/1200x800/?plaza,civic" alt="Riverside Cultural Centre">
        <div class="meta">
          <h3>Riverside Cultural Centre</h3>
          <p class="small">Public terraces and flexible gallery spaces reconnecting riverfront and city.</p>
        </div>
      </article>

      <!-- Add more cards as needed -->
    </div>

    <!-- Horizontal showcase (hidden by default) -->
    <div id="showcaseView" class="showcase" style="display:none">
      <article class="card" tabindex="0" data-id="p1">
        <img src="https://source.unsplash.com/2000x1200/?house,cliff" alt="Cliffside Residence large">
        <div class="meta">
          <h3>Cliffside Residence</h3>
          <p class="small">A private residence balancing views, privacy and passive cooling strategies.</p>
        </div>
      </article>

      <article class="card" tabindex="0" data-id="p2">
        <img src="https://source.unsplash.com/2000x1200/?glass,skyscraper" alt="Glassframe Tower large">
        <div class="meta">
          <h3>Glassframe Tower</h3>
          <p class="small">Commercial tower rethinking transparency and shading on a narrow urban lot.</p>
        </div>
      </article>

      <article class="card" tabindex="0" data-id="p3">
        <img src="https://source.unsplash.com/2000x1200/?gallery,architecture" alt="Riverside Cultural Centre large">
        <div class="meta">
          <h3>Riverside Cultural Centre</h3>
          <p class="small">Public terraces and flexible gallery spaces reconnecting riverfront and city.</p>
        </div>
      </article>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about" class="wrap" style="padding:36px 0">
    <h2 style="margin-top:0">About M&amp;G Architect</h2>
    <p class="small">M&amp;G Architect is a design studio dedicated to exemplary, context-driven architecture. We prioritize material intelligence, spatial sequencing, and environmentally responsible design. Our website is project-first — each work is presented as a case study to show concept, process and outcome.</p>
  </section>

  <!-- CONTACT (Formspree) -->
  <section id="contact" class="contact wrap" aria-labelledby="contactLabel" style="padding-bottom:48px">
    <h2 id="contactLabel">Get in touch</h2>
    <p class="small" style="text-align:center;max-width:900px;margin:8px auto 18px">For consultations, commissions or press, send us a brief note — we typically respond within 2–3 business days.</p>

    <form class="contact-form" action="https://formspree.io/f/xkgqdwdn" method="POST">
      <label for="name">Name</label>
      <input id="name" name="name" placeholder="Your full name" required>

      <label for="email">Email</label>
      <input id="email" name="_replyto" type="email" placeholder="you@domain.com" required>

      <label for="phone">Phone</label>
      <input id="phone" name="phone" placeholder="+91 9XXXXXXXXX">

      <label for="message">Message</label>
      <textarea id="message" name="message" rows="5" placeholder="Brief about the project, budget, timeline..." required></textarea>

      <!-- Optional hidden fields for Formspree / spam control -->
      <input type="hidden" name="_subject" value="New inquiry from M&G Architect site">
      <input type="text" name="_gotcha" style="display:none">

      <div style="display:flex;gap:12px;align-items:center;justify-content:center;margin-top:6px">
        <button type="submit" class="btn">Send Message</button>
        <div class="small" style="color:rgba(255,255,255,0.7)">Or email: info@mg-architect.example</div>
      </div>
    </form>
  </section>

  <footer class="wrap">
    <div style="display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap">
      <div class="small">© <span id="year"></span> M&amp;G Architect</div>
      <div class="small">Designed for presentation — Projects &amp; Case Studies</div>
    </div>
  </footer>

  <!-- Project Modal -->
  <div id="projectModal" class="modal" role="dialog" aria-hidden="true">
    <button class="close-x" id="closeModal" aria-label="Close project">✕</button>
    <div class="sheet" role="document" aria-labelledby="projTitle">
      <!-- content filled dynamically -->
      <div id="modalContent">
        <h2 id="projTitle">Project Title</h2>
        <div style="display:flex;gap:18px;flex-wrap:wrap">
          <div style="flex:1;min-width:320px">
            <img id="modalHero" src="" alt="" style="width:100%;border-radius:10px;margin-bottom:12px">
            <div id="modalGallery" style="display:flex;gap:8px;overflow-x:auto"></div>
          </div>
          <aside style="width:360px;min-width:260px">
            <h3 style="margin-top:0">Overview</h3>
            <p id="projDesc" class="small"></p>
            <h4>Key facts</h4>
            <ul id="projFacts" class="small"></ul>
          </aside>
        </div>
      </div>
    </div>
  </div>

<script>
  // ========== Utilities & initial setup ==========
  document.getElementById('year').textContent = new Date().getFullYear();

  const body = document.body;
  const themeToggle = document.getElementById('themeToggle');
  const videoToggle = document.getElementById('videoToggle');
  const layoutToggle = document.getElementById('layoutToggle');

  // Theme: toggle dark/light (persist using localStorage)
  let theme = localStorage.getItem('mg_theme') || 'dark';
  applyTheme(theme);
  function applyTheme(t){
    if(t === 'light'){ body.classList.remove('theme-dark'); body.classList.add('theme-light'); themeToggle.textContent='Dark'; }
    else { body.classList.remove('theme-light'); body.classList.add('theme-dark'); themeToggle.textContent='Light'; }
    localStorage.setItem('mg_theme', t);
  }
  themeToggle.addEventListener('click', ()=> { theme = (theme==='dark') ? 'light' : 'dark'; applyTheme(theme); });

  // Hero video toggle (shows video if a valid source is present)
  const heroVideo = document.getElementById('heroVideo');
  const heroImg = document.getElementById('heroImg');
  let videoOn = false;
  videoToggle.addEventListener('click', ()=>{
    // If video has a valid source, toggle it; otherwise show message to replace file
    const hasSource = heroVideo.querySelector('source') && heroVideo.querySelector('source').src;
    if(!hasSource){ alert('No hero video found. Replace the <source src=\"hero-video.mp4\"> with your video URL/file.'); return; }
    videoOn = !videoOn;
    heroVideo.style.display = videoOn ? 'block' : 'none';
    heroImg.style.display = videoOn ? 'none' : 'block';
    if(videoOn){ heroVideo.play().catch(()=>{/* autoplay may block on some browsers */}); videoToggle.textContent = 'Image'; }
    else{ heroVideo.pause(); videoToggle.textContent = 'Video'; }
  });

  // Layout toggle: show grid or showcase
  const gridView = document.getElementById('gridView');
  const showcaseView = document.getElementById('showcaseView');
  document.getElementById('toGrid').addEventListener('click', ()=> { gridView.style.display='grid'; showcaseView.style.display='none'; });
  document.getElementById('toShowcase').addEventListener('click', ()=> { gridView.style.display='none'; showcaseView.style.display='flex'; });

  // Also top-level layout toggle button (for convenience)
  layoutToggle.addEventListener('click', ()=>{
    const showingGrid = gridView.style.display !== 'none';
    if(showingGrid){ gridView.style.display='none'; showcaseView.style.display='flex'; layoutToggle.textContent='Grid'; }
    else { gridView.style.display='grid'; showcaseView.style.display='none'; layoutToggle.textContent='Showcase'; }
  });

  // Project modal data (example data; replace with your own)
  const projects = {
    p1: {
      id:'p1',
      title:'Cliffside Residence',
      desc:'A private residence that balances dramatic views with privacy and passive cooling strategies. The design uses terraced volumes and cross-ventilation to reduce mechanical cooling needs.',
      hero:'https://source.unsplash.com/1600x1000/?house,cliff',
      gallery:[
        'https://source.unsplash.com/1200x800/?interior,wood',
        'https://source.unsplash.com/1200x800/?exterior,terrace',
        'https://source.unsplash.com/1200x800/?architecture,view'
      ],
      facts:['Location: Coastal bluff','Area: 420 sqm','Status: Built • 2023']
    },
    p2: {
      id:'p2',
      title:'Glassframe Tower',
      desc:'A commercial tower rethinking transparency with an operable shading system and atrium-based ventilation. The façade uses a modular frame to reduce solar gain while maximizing daylight.',
      hero:'https://source.unsplash.com/1600x1000/?glass,skyscraper',
      gallery:['https://source.unsplash.com/1200x800/?façade,glass','https://source.unsplash.com/1200x800/?office,interior'],
      facts:['Location: Urban centre','Floors: 28','Status: Concept • 2024']
    },
    p3: {
      id:'p3',
      title:'Riverside Cultural Centre',
      desc:'A civic complex of galleries, terraces and flexible halls that reactivates the riverfront with cultural programming and public circulation routes.',
      hero:'https://source.unsplash.com/1600x1000/?gallery,architecture',
      gallery:['https://source.unsplash.com/1200x800/?public,plaza','https://source.unsplash.com/1200x800/?gallery,interior'],
      facts:['Location: Riverfront precinct','Area: 2,800 sqm','Status: Design • 2025']
    }
  };

  // Open modal on project card click / keypress
  const modal = document.getElementById('projectModal');
  const modalTitle = document.getElementById('projTitle');
  const modalDesc = document.getElementById('projDesc');
  const modalHero = document.getElementById('modalHero');
  const modalGallery = document.getElementById('modalGallery');
  const modalFacts = document.getElementById('projFacts');

  function openProject(id){
    const p = projects[id];
    if(!p) return;
    modalTitle.textContent = p.title;
    modalDesc.textContent = p.desc;
    modalHero.src = p.hero;
    modalGallery.innerHTML = '';
    p.gallery.forEach(src=>{
      const img = document.createElement('img');
      img.src = src; img.style.height='120px'; img.style.objectFit='cover'; img.style.borderRadius='8px';
      modalGallery.appendChild(img);
    });
    modalFacts.innerHTML = '';
    p.facts.forEach(f=> { const li = document.createElement('li'); li.textContent = f; modalFacts.appendChild(li); });
    modal.style.display = 'flex'; modal.setAttribute('aria-hidden','false');
    document.body.style.overflow = 'hidden';
  }

  // attach handlers to all cards
  document.querySelectorAll('.card[data-id]').forEach(card=>{
    card.addEventListener('click', ()=> openProject(card.dataset.id));
    card.addEventListener('keypress', (e)=> { if(e.key==='Enter') openProject(card.dataset.id);});
  });

  // close modal
  document.getElementById('closeModal').addEventListener('click', closeModal);
  modal.addEventListener('click', (e)=> { if(e.target===modal) closeModal(); });
  function closeModal(){ modal.style.display='none'; modal.setAttribute('aria-hidden','true'); document.body.style.overflow=''; }

  // Basic accessibility: close on ESC
  window.addEventListener('keydown', (e)=> { if(e.key === 'Escape'){ if(modal.style.display==='flex') closeModal(); } });

  // Contact form: graceful client-side validation (Formspree will handle sending)
  const contactForm = document.querySelector('form.contact-form');
  contactForm.addEventListener('submit', (e)=>{
    // minimal check
    const name = contactForm.querySelector('#name').value.trim();
    const email = contactForm.querySelector('#email').value.trim();
    const msg = contactForm.querySelector('#message').value.trim();
    if(!name || !email || !msg){ e.preventDefault(); alert('Please complete name, email and message before sending.'); return; }
    // otherwise allow form to submit to Formspree
    // Optionally show a small confirmation (Formspree will forward email)
    setTimeout(()=>{ alert('Thank you — your message is being sent.'); }, 80);
  });
</script>
</body>
</html>
