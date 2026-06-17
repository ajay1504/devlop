<!--
  ============================================================
  GLASSMORPHISM PORTFOLIO — single file, no build step
  ------------------------------------------------------------
  TO MAKE IT YOURS, replace the placeholders below:
   1. <title> and the meta description
   2. Brand initials in the nav  ........... "MC"
   3. Hero name / role / tagline  .......... search "Ajay Prajapati"
   4. Stats strip numbers
   5. About paragraph + skill tags
   6. The six project cards (title, blurb, tags, links)
   7. Contact email + social links
  Tip: do a find-and-replace for "Ajay Prajapati" and "ajay@" first.
  ============================================================
-->
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Maya Chen — Product Designer</title>
<meta name="description" content="Product & interaction designer crafting calm, useful interfaces." />
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
<style>
:root{
  --bg:#08080f;
  --violet:#6d28d9;
  --cyan:#0891b2;
  --magenta:#c026d3;
  --glass:rgba(255,255,255,.055);
  --glass-strong:rgba(255,255,255,.09);
  --glass-border:rgba(255,255,255,.12);
  --glass-border-hi:rgba(255,255,255,.28);
  --text:#f4f4fa;
  --muted:#9a9ab4;
  --display:"Space Grotesk",sans-serif;
  --body:"Inter",sans-serif;
  --mono:"JetBrains Mono",monospace;
  --radius:22px;
}

*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{
  font-family:var(--body);
  background:var(--bg);
  color:var(--text);
  line-height:1.6;
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
}

/* ---------- Aurora backdrop (what the glass refracts) ---------- */
.aurora{position:fixed;inset:0;z-index:-2;overflow:hidden;filter:blur(80px);opacity:.85}
.blob{position:absolute;border-radius:50%;mix-blend-mode:screen;animation:drift 22s ease-in-out infinite}
.blob.a{width:46vw;height:46vw;background:var(--violet);top:-10vh;left:-8vw}
.blob.b{width:42vw;height:42vw;background:var(--cyan);top:30vh;right:-10vw;animation-delay:-7s}
.blob.c{width:34vw;height:34vw;background:var(--magenta);bottom:-12vh;left:30vw;animation-delay:-13s;opacity:.7}
@keyframes drift{
  0%,100%{transform:translate(0,0) scale(1)}
  33%{transform:translate(6vw,8vh) scale(1.12)}
  66%{transform:translate(-5vw,4vh) scale(.92)}
}
/* grain so the dark areas aren't flat */
.grain{position:fixed;inset:0;z-index:-1;pointer-events:none;opacity:.04;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");}

/* cursor ambient glow */
.cursor-glow{position:fixed;width:520px;height:520px;border-radius:50%;pointer-events:none;z-index:0;
  background:radial-gradient(circle,rgba(124,58,237,.18),transparent 60%);
  transform:translate(-50%,-50%);transition:opacity .4s;opacity:0;mix-blend-mode:screen}

/* ---------- shared glass ---------- */
.glass{
  background:var(--glass);
  backdrop-filter:blur(18px) saturate(140%);
  -webkit-backdrop-filter:blur(18px) saturate(140%);
  border:1px solid var(--glass-border);
  border-radius:var(--radius);
  box-shadow:0 8px 40px rgba(0,0,0,.35), inset 0 1px 0 rgba(255,255,255,.08);
}

.wrap{max-width:1120px;margin:0 auto;padding:0 24px;position:relative;z-index:1}
.eyebrow{font-family:var(--mono);font-size:.72rem;letter-spacing:.18em;text-transform:uppercase;color:var(--muted)}

/* ---------- nav ---------- */
nav{position:fixed;top:18px;left:0;right:0;z-index:50;display:flex;justify-content:center}
.nav-inner{display:flex;align-items:center;gap:8px;padding:8px 8px 8px 18px;border-radius:999px}
.brand{font-family:var(--display);font-weight:700;letter-spacing:.04em;margin-right:auto;padding-right:18px;font-size:1.05rem}
.nav-links{display:flex;gap:4px}
.nav-links a{position:relative;color:var(--muted);text-decoration:none;font-size:.9rem;font-weight:500;padding:8px 14px;border-radius:999px;transition:color .25s,background .25s}
.nav-links a:hover,.nav-links a:focus-visible{color:var(--text);background:var(--glass-strong)}
.nav-cta{font-family:var(--body);font-weight:600;font-size:.88rem;color:#0a0a14;background:linear-gradient(135deg,#a78bfa,#22d3ee);border:none;border-radius:999px;padding:9px 18px;cursor:pointer;text-decoration:none;transition:transform .2s,box-shadow .25s}
.nav-cta:hover{transform:translateY(-1px);box-shadow:0 6px 24px rgba(124,58,237,.5)}

/* ---------- hero ---------- */
header{min-height:100vh;display:flex;align-items:center;padding:120px 0 60px}
.hero{max-width:760px}
.hero .eyebrow{display:inline-block;margin-bottom:22px;padding:8px 16px;border-radius:999px}
.hero h1{font-family:var(--display);font-weight:700;font-size:clamp(2.7rem,8vw,5.4rem);line-height:1.02;letter-spacing:-.02em;margin-bottom:22px}
.hero h1 .grad{background:linear-gradient(120deg,#c4b5fd,#67e8f9,#f0abfc);-webkit-background-clip:text;background-clip:text;color:transparent}
.hero p.lead{font-size:clamp(1.05rem,2.4vw,1.3rem);color:var(--muted);max-width:560px;margin-bottom:36px}
.hero-actions{display:flex;gap:14px;flex-wrap:wrap}
.btn{font-weight:600;font-size:.95rem;padding:14px 26px;border-radius:14px;text-decoration:none;cursor:pointer;transition:transform .2s,box-shadow .25s,background .25s;display:inline-flex;align-items:center;gap:9px}
.btn-primary{color:#0a0a14;background:linear-gradient(135deg,#a78bfa,#22d3ee);border:none}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 10px 34px rgba(124,58,237,.5)}
.btn-ghost{color:var(--text);background:var(--glass);border:1px solid var(--glass-border)}
.btn-ghost:hover{transform:translateY(-2px);border-color:var(--glass-border-hi);background:var(--glass-strong)}

/* ---------- stats strip ---------- */
.stats{display:grid;grid-template-columns:repeat(4,1fr);gap:18px;margin:0 auto 110px;padding:28px}
.stat{text-align:center}
.stat .num{font-family:var(--display);font-weight:700;font-size:clamp(1.6rem,4vw,2.4rem);background:linear-gradient(120deg,#c4b5fd,#67e8f9);-webkit-background-clip:text;background-clip:text;color:transparent}
.stat .label{font-size:.82rem;color:var(--muted);margin-top:4px}

/* ---------- sections ---------- */
section{padding:60px 0}
.sec-head{display:flex;align-items:baseline;gap:18px;margin-bottom:42px}
.sec-head h2{font-family:var(--display);font-weight:700;font-size:clamp(1.8rem,5vw,2.8rem);letter-spacing:-.01em}
.sec-head .eyebrow{white-space:nowrap}

/* about */
.about-grid{display:grid;grid-template-columns:1.4fr 1fr;gap:24px}
.about-card{padding:38px}
.about-card p{color:var(--muted);margin-bottom:16px}
.about-card p strong{color:var(--text);font-weight:600}
.skills-card{padding:38px;display:flex;flex-direction:column;gap:18px}
.skills-card h3{font-family:var(--display);font-size:1.05rem;font-weight:600}
.tags{display:flex;flex-wrap:wrap;gap:9px}
.tag{font-family:var(--mono);font-size:.76rem;color:var(--text);padding:7px 13px;border-radius:999px;background:var(--glass);border:1px solid var(--glass-border);transition:border-color .25s,transform .2s,background .25s}
.tag:hover{transform:translateY(-2px);border-color:var(--glass-border-hi);background:var(--glass-strong)}

/* projects */
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
.card{position:relative;padding:30px;text-decoration:none;color:inherit;overflow:hidden;transform-style:preserve-3d;transition:transform .35s cubic-bezier(.2,.7,.3,1),border-color .35s,box-shadow .35s}
.card::before{content:"";position:absolute;inset:0;border-radius:var(--radius);opacity:0;transition:opacity .35s;
  background:radial-gradient(380px circle at var(--mx,50%) var(--my,0%),rgba(255,255,255,.16),transparent 45%);pointer-events:none}
.card:hover::before{opacity:1}
.card:hover{border-color:var(--glass-border-hi);box-shadow:0 22px 60px rgba(0,0,0,.5),0 0 40px rgba(124,58,237,.12)}
.card .idx{font-family:var(--mono);font-size:.75rem;color:var(--muted);margin-bottom:auto}
.card .thumb{height:120px;border-radius:14px;margin-bottom:22px;background:linear-gradient(135deg,var(--c1),var(--c2));opacity:.9;transition:transform .4s}
.card:hover .thumb{transform:scale(1.03)}
.card h3{font-family:var(--display);font-size:1.25rem;font-weight:600;margin-bottom:10px;display:flex;align-items:center;justify-content:space-between}
.card h3 .arr{transition:transform .3s;opacity:.55}
.card:hover h3 .arr{transform:translate(4px,-4px);opacity:1}
.card p{color:var(--muted);font-size:.92rem;margin-bottom:18px}
.card .ctags{display:flex;flex-wrap:wrap;gap:7px}
.card .ctags span{font-family:var(--mono);font-size:.68rem;color:var(--muted);padding:4px 9px;border-radius:7px;background:rgba(255,255,255,.04);border:1px solid var(--glass-border)}

/* contact */
.contact{padding:64px 48px;text-align:center}
.contact h2{font-family:var(--display);font-weight:700;font-size:clamp(2rem,6vw,3.4rem);letter-spacing:-.02em;margin-bottom:16px}
.contact h2 .grad{background:linear-gradient(120deg,#c4b5fd,#67e8f9,#f0abfc);-webkit-background-clip:text;background-clip:text;color:transparent}
.contact p{color:var(--muted);max-width:480px;margin:0 auto 30px}
.socials{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-top:26px}
.socials a{font-size:.9rem;color:var(--muted);text-decoration:none;padding:10px 18px;border-radius:12px;background:var(--glass);border:1px solid var(--glass-border);transition:color .25s,transform .2s,border-color .25s}
.socials a:hover{color:var(--text);transform:translateY(-2px);border-color:var(--glass-border-hi)}

footer{text-align:center;padding:50px 0 40px;color:var(--muted);font-size:.85rem}
footer .mono{font-family:var(--mono)}

/* ---------- reveal animation ---------- */
.reveal{opacity:0;transform:translateY(26px);transition:opacity .7s ease,transform .7s cubic-bezier(.2,.7,.3,1)}
.reveal.in{opacity:1;transform:none}

/* ---------- responsive ---------- */
@media(max-width:880px){
  .nav-links{display:none}
  .about-grid{grid-template-columns:1fr}
  .grid{grid-template-columns:1fr 1fr}
  .stats{grid-template-columns:1fr 1fr;gap:24px}
}
@media(max-width:560px){
  .grid{grid-template-columns:1fr}
  .contact{padding:44px 24px}
}
@media(prefers-reduced-motion:reduce){
  *{animation:none!important;transition:none!important;scroll-behavior:auto}
  .reveal{opacity:1;transform:none}
}
</style>
</head>
<body>

<div class="aurora"><span class="blob a"></span><span class="blob b"></span><span class="blob c"></span></div>
<div class="grain"></div>
<div class="cursor-glow" id="glow"></div>

<!-- NAV -->
<nav>
  <div class="nav-inner glass">
    <span class="brand">MC</span>
    <div class="nav-links">
      <a href="#work">Work</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </div>
    <a href="#contact" class="nav-cta">Let's talk</a>
  </div>
</nav>

<!-- HERO -->
<header>
  <div class="wrap">
    <div class="hero">
      <span class="eyebrow glass">Product &amp; Interaction Designer</span>
      <h1>Hi, I'm <span class="grad">Maya Chen</span>. I design calm, useful interfaces.</h1>
      <p class="lead">I help teams turn messy problems into products people actually enjoy using — from first sketch to shipped pixel.</p>
      <div class="hero-actions">
        <a href="#work" class="btn btn-primary">View my work →</a>
        <a href="#contact" class="btn btn-ghost">Get in touch</a>
      </div>
    </div>
  </div>
</header>

<!-- STATS -->
<div class="wrap">
  <div class="stats glass reveal">
    <div class="stat"><div class="num">8+</div><div class="label">Years designing</div></div>
    <div class="stat"><div class="num">40+</div><div class="label">Products shipped</div></div>
    <div class="stat"><div class="num">12</div><div class="label">Happy clients</div></div>
    <div class="stat"><div class="num">3</div><div class="label">Design awards</div></div>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="wrap">
    <div class="sec-head reveal"><span class="eyebrow">01 — About</span><h2>A bit about me</h2></div>
    <div class="about-grid">
      <div class="about-card glass reveal">
        <p>I'm a product designer based in <strong>San Francisco</strong>, focused on the space where clarity meets craft. I care about the small details — the timing of a transition, the wording on an empty state — because that's where good products earn trust.</p>
        <p>Lately I've been working on <strong>fintech and developer tools</strong>, leading design end to end: research, flows, prototypes, and the polish that ships. I write a little code too, which keeps my handoffs honest.</p>
        <p>When I'm not designing, you'll find me bouldering, brewing pour-over, or redrawing maps of places I've never been.</p>
      </div>
      <div class="skills-card glass reveal">
        <h3>Toolkit</h3>
        <div class="tags">
          <span class="tag">Figma</span><span class="tag">Prototyping</span><span class="tag">Design systems</span>
          <span class="tag">User research</span><span class="tag">Motion</span><span class="tag">Webflow</span>
          <span class="tag">HTML/CSS</span><span class="tag">React</span><span class="tag">Framer</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- WORK -->
<section id="work">
  <div class="wrap">
    <div class="sec-head reveal"><span class="eyebrow">02 — Selected work</span><h2>Things I've built</h2></div>
    <div class="grid">

      <a href="#" class="card glass reveal" style="--c1:#7c3aed;--c2:#2563eb">
        <span class="idx">01</span>
        <div class="thumb"></div>
        <h3>Ledger <span class="arr">↗</span></h3>
        <p>A personal finance app that makes budgeting feel weightless. Led design from zero to launch.</p>
        <div class="ctags"><span>Mobile</span><span>Fintech</span><span>0→1</span></div>
      </a>

      <a href="#" class="card glass reveal" style="--c1:#0891b2;--c2:#22d3ee">
        <span class="idx">02</span>
        <div class="thumb"></div>
        <h3>Atlas <span class="arr">↗</span></h3>
        <p>Developer dashboard turning raw logs into stories. Built the component library behind it.</p>
        <div class="ctags"><span>Web</span><span>Dev tools</span><span>Design system</span></div>
      </a>

      <a href="#" class="card glass reveal" style="--c1:#db2777;--c2:#f97316">
        <span class="idx">03</span>
        <div class="thumb"></div>
        <h3>Bloom <span class="arr">↗</span></h3>
        <p>An onboarding flow that lifted activation by 38%. Research, flows, and the motion that sells it.</p>
        <div class="ctags"><span>Growth</span><span>UX</span><span>Motion</span></div>
      </a>

      <a href="#" class="card glass reveal" style="--c1:#16a34a;--c2:#22d3ee">
        <span class="idx">04</span>
        <div class="thumb"></div>
        <h3>Tempo <span class="arr">↗</span></h3>
        <p>Calendar reimagined around focus, not meetings. A side project that became a small cult favourite.</p>
        <div class="ctags"><span>Side project</span><span>Productivity</span></div>
      </a>

      <a href="#" class="card glass reveal" style="--c1:#9333ea;--c2:#ec4899">
        <span class="idx">05</span>
        <div class="thumb"></div>
        <h3>Northwind <span class="arr">↗</span></h3>
        <p>Brand and marketing site for a climate startup. Identity, illustration, and a fast little site.</p>
        <div class="ctags"><span>Branding</span><span>Web</span></div>
      </a>

      <a href="#" class="card glass reveal" style="--c1:#2563eb;--c2:#06b6d4">
        <span class="idx">06</span>
        <div class="thumb"></div>
        <h3>Signal <span class="arr">↗</span></h3>
        <p>A real-time analytics tool. Untangled a dense data product into something a human can read.</p>
        <div class="ctags"><span>Data</span><span>Enterprise</span></div>
      </a>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="wrap">
    <div class="contact glass reveal">
      <h2>Let's build something <span class="grad">worth using</span>.</h2>
      <p>Open to select freelance projects and full-time roles. The fastest way to reach me is a quick email.</p>
      <a href="mailto:maya@example.com" class="btn btn-primary">maya@example.com</a>
      <div class="socials">
        <a href="#">LinkedIn</a>
        <a href="#">Dribbble</a>
        <a href="#">GitHub</a>
        <a href="#">Read.cv</a>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="wrap"><span class="mono">© 2026 Maya Chen</span> · Designed &amp; built with care</div>
</footer>

<script>
// cursor ambient glow
const glow=document.getElementById('glow');
let raf=null;
window.addEventListener('pointermove',e=>{
  if(raf)return;
  raf=requestAnimationFrame(()=>{
    glow.style.left=e.clientX+'px';
    glow.style.top=e.clientY+'px';
    glow.style.opacity='1';
    raf=null;
  });
});

// glass cards: spotlight position + 3D tilt
document.querySelectorAll('.card').forEach(card=>{
  card.addEventListener('pointermove',e=>{
    const r=card.getBoundingClientRect();
    const px=(e.clientX-r.left)/r.width;
    const py=(e.clientY-r.top)/r.height;
    card.style.setProperty('--mx',px*100+'%');
    card.style.setProperty('--my',py*100+'%');
    const rx=(.5-py)*8, ry=(px-.5)*8;
    card.style.transform=`perspective(900px) rotateX(${rx}deg) rotateY(${ry}deg) translateY(-6px)`;
  });
  card.addEventListener('pointerleave',()=>{card.style.transform='';});
});

// scroll reveal
const io=new IntersectionObserver(es=>{
  es.forEach(en=>{if(en.isIntersecting){en.target.classList.add('in');io.unobserve(en.target);}});
},{threshold:.15});
document.querySelectorAll('.reveal').forEach((el,i)=>{
  el.style.transitionDelay=(i%3)*0.08+'s';
  io.observe(el);
});

// nav glass solidifies on scroll
const navInner=document.querySelector('.nav-inner');
addEventListener('scroll',()=>{
  navInner.style.background = scrollY>40 ? 'rgba(255,255,255,.09)' : 'rgba(255,255,255,.055)';
});
</script>
</body>
</html>
