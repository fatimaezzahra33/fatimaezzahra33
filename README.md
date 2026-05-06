<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Fatima-Ezzahra El Abbas | Web Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet"/>
    <style>
        *{margin:0;padding:0;box-sizing:border-box;}
        :root{
            --gold:#C9A84C;--gold2:#E8C97A;--cream:#FAF7F2;--ink:#1A1510;--ink2:#2E2720;
            --warm:#6B5C4E;--warm-light:#A89080;--card:#FFFFFF;--card-bg:#F5F0E8;
            --border:rgba(201,168,76,0.18);--border2:rgba(201,168,76,0.35);
        }
        html{scroll-behavior:smooth;}
        body{background:var(--cream);color:var(--ink);font-family:'Outfit',sans-serif;overflow-x:hidden;cursor:none;}
        
        /* Cursor Styling */
        .cursor{position:fixed;width:10px;height:10px;background:var(--gold);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);}
        .cursor-follower{position:fixed;width:36px;height:36px;border:1.5px solid var(--gold);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:transform .1s ease-out;opacity:.4;}

        nav{position:fixed;top:0;left:0;right:0;z-index:200;padding:1.4rem 5rem;display:flex;align-items:center;justify-content:space-between;transition:all .4s;}
        nav.scrolled{background:rgba(250,247,242,0.94);backdrop-filter:blur(20px);box-shadow:0 1px 0 var(--border);padding:0.8rem 5rem;}
        .nav-logo{font-family:'Cormorant Garamond',serif;font-size:1.5rem;color:var(--ink);font-weight:600;text-decoration:none;}
        .nav-logo span{color:var(--gold);}
        .nav-links{display:flex;gap:2.5rem;list-style:none;}
        .nav-links a{color:var(--warm);text-decoration:none;font-size:.8rem;letter-spacing:.1em;text-transform:uppercase;font-weight:500;transition:color .3s;position:relative;}
        .nav-links a::after{content:'';position:absolute;bottom:-3px;left:0;width:0;height:1px;background:var(--gold);transition:width .3s;}
        .nav-links a:hover{color:var(--gold);}
        .nav-links a:hover::after{width:100%;}
        .nav-right{display:flex;gap:.8rem;align-items:center;}
        .nav-icon{width:36px;height:36px;border:1px solid var(--border2);border-radius:50%;display:flex;align-items:center;justify-content:center;color:var(--warm);text-decoration:none;transition:all .3s;}
        .nav-icon:hover{border-color:var(--gold);color:var(--gold);background:rgba(201,168,76,.06);}

        /* HERO */
        #home{min-height:100vh;display:grid;grid-template-columns:1fr 1fr;}
        .hero-left{display:flex;flex-direction:column;justify-content:center;padding:8rem 4rem 4rem 5rem;}
        .eyebrow{display:flex;align-items:center;gap:.8rem;margin-bottom:2rem;opacity:0;animation:fadeUp .9s .2s forwards;}
        .eyebrow-line{width:40px;height:1px;background:var(--gold);}
        .eyebrow-text{font-size:.7rem;letter-spacing:.2em;text-transform:uppercase;color:var(--gold);font-weight:500;}
        .hero-name{font-family:'Cormorant Garamond',serif;font-size:clamp(3rem,5vw,5rem);font-weight:300;line-height:1.05;margin-bottom:.5rem;opacity:0;animation:fadeUp .9s .35s forwards;}
        .hero-name strong{font-weight:700;display:block;}
        .hero-name em{font-style:italic;color:var(--gold);}
        .hero-sub{font-size:.95rem;color:var(--warm);margin-bottom:1.5rem;letter-spacing:.03em;opacity:0;animation:fadeUp .9s .5s forwards;}
        .hero-desc{font-size:.92rem;color:var(--warm);line-height:1.9;max-width:410px;margin-bottom:2.5rem;font-weight:300;opacity:0;animation:fadeUp .9s .65s forwards;}
        .hero-btns{display:flex;gap:1rem;flex-wrap:wrap;opacity:0;animation:fadeUp .9s .8s forwards;}
        .btn-gold{background:var(--gold);color:var(--ink);padding:.85rem 2rem;font-size:.82rem;font-weight:600;letter-spacing:.08em;text-transform:uppercase;text-decoration:none;border-radius:2px;transition:all .2s;}
        .btn-gold:hover{transform:translateY(-2px);box-shadow:0 12px 40px rgba(201,168,76,.35);}
        .btn-outline{border:1px solid var(--border2);color:var(--ink);padding:.85rem 2rem;font-size:.82rem;font-weight:500;letter-spacing:.06em;text-transform:uppercase;text-decoration:none;border-radius:2px;transition:all .2s;}
        .btn-outline:hover{border-color:var(--gold);color:var(--gold);}
        .hero-stats{display:flex;gap:3rem;margin-top:3.5rem;padding-top:2.5rem;border-top:1px solid var(--border);opacity:0;animation:fadeUp .9s .95s forwards;}
        .stat-num{font-family:'Cormorant Garamond',serif;font-size:2.8rem;font-weight:600;color:var(--ink);line-height:1;}
        .stat-label{font-size:.7rem;color:var(--warm-light);text-transform:uppercase;letter-spacing:.1em;margin-top:.3rem;}

        /* HERO RIGHT */
        .hero-right{position:relative;overflow:hidden;background:var(--ink2);}
        .hero-img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;object-position:center top;opacity:.7;mix-blend-mode:luminosity;}
        .hero-overlay{position:absolute;inset:0;background:linear-gradient(to top,rgba(26,21,16,.88) 0%,rgba(26,21,16,.15) 60%,transparent 100%);}
        .photo-deco1{position:absolute;top:2.5rem;right:2.5rem;width:100px;height:100px;border-top:1.5px solid var(--gold);border-right:1.5px solid var(--gold);opacity:.35;z-index:2;}
        .photo-deco2{position:absolute;bottom:7rem;left:2.5rem;width:70px;height:70px;border-bottom:1.5px solid var(--gold);border-left:1.5px solid var(--gold);opacity:.25;z-index:2;}
        .hero-photo-info{position:absolute;bottom:3rem;left:3rem;right:3rem;z-index:3;}
        .photo-name{font-family:'Cormorant Garamond',serif;font-size:1.15rem;color:rgba(255,255,255,.85);font-style:italic;margin-bottom:.5rem;}
        .photo-tag{display:inline-flex;align-items:center;gap:.5rem;background:rgba(201,168,76,.15);border:1px solid rgba(201,168,76,.35);color:var(--gold2);font-size:.7rem;letter-spacing:.12em;text-transform:uppercase;padding:.3rem .85rem;border-radius:50px;}
        .tag-dot{width:6px;height:6px;background:#6ee7b7;border-radius:50%;animation:pulse 2s infinite;}

        /* SECTION COMMONS */
        .sec{padding:8rem 5rem;}
        .section-header{text-align:center;margin-bottom:4.5rem;}
        .sec-label{font-size:.7rem;letter-spacing:.2em;text-transform:uppercase;color:var(--gold);display:flex;align-items:center;justify-content:center;gap:1rem;margin-bottom:.9rem;}
        .sec-label::before,.sec-label::after{content:'';width:28px;height:1px;background:var(--gold);}
        .sec-title{font-family:'Cormorant Garamond',serif;font-size:clamp(2.2rem,4vw,3.4rem);font-weight:300;line-height:1.1;}
        .sec-title strong{font-weight:700;}

        /* PROJECTS GRID & FILTER */
        .proj-filter{display:flex;gap:.5rem;justify-content:center;margin-bottom:3rem;}
        .f-btn{padding:.48rem 1.3rem;border-radius:50px;font-size:.76rem;letter-spacing:.07em;text-transform:uppercase;font-weight:500;cursor:pointer;border:1px solid var(--border2);background:transparent;color:var(--warm);transition:all .2s;font-family:'Outfit',sans-serif;}
        .f-btn.active,.f-btn:hover{background:var(--gold);color:var(--ink);border-color:var(--gold);}
        .proj-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.4rem;max-width:1200px;margin:0 auto;}
        .p-card{background:var(--card);border:1px solid var(--border);border-radius:3px;overflow:hidden;transition:all .3s;}
        .p-card.hidden { display: none; }
        .p-card:hover{transform:translateY(-5px);box-shadow:0 20px 55px rgba(0,0,0,.09);}
        .p-img{height:185px;overflow:hidden;position:relative;background:var(--card-bg);}
        .p-img img{width:100%;height:100%;object-fit:cover;transition:transform .5s;display:block;}
        .p-badge{position:absolute;top:9px;right:9px;font-size:.63rem;letter-spacing:.09em;text-transform:uppercase;padding:.25rem .65rem;border-radius:50px;font-weight:600;}
        .b-wp{background:rgba(33,117,155,.1);color:#21759B;border:1px solid rgba(33,117,155,.2);}
        .b-sh{background:rgba(96,191,72,.09);color:#3a7520;border:1px solid rgba(96,191,72,.2);}
        .p-body{padding:1.2rem 1.4rem;}
        .p-name{font-weight:600;font-size:.93rem;color:var(--ink);margin-bottom:.3rem;}
        .p-desc{font-size:.78rem;color:var(--warm);line-height:1.7;margin-bottom:.9rem;font-weight:300;}
        .p-link{display:inline-flex;align-items:center;gap:.35rem;font-size:.76rem;font-weight:500;color:var(--gold);text-decoration:none;letter-spacing:.04em;transition:gap .2s;}
        .p-link:hover{gap:.6rem;}

        /* SERVICES */
        .srv-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.8rem;max-width:1100px;margin:0 auto;}
        .srv-card{padding:2.5rem 2rem;border:1px solid var(--border);border-radius:3px;background:var(--card);position:relative;overflow:hidden;transition:all .3s;}
        .srv-card:hover{transform:translateY(-5px);box-shadow:0 20px 60px rgba(0,0,0,.07);}

        /* SKILLS */
        #skills{background:var(--ink2);position:relative;overflow:hidden;}
        #skills .sec-title{color:var(--cream);}
        .sk-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:2px;max-width:1100px;margin:3.5rem auto 0;}
        .sk-row{display:flex;align-items:center;justify-content:space-between;padding:1.4rem 1.8rem;background:rgba(255,255,255,.025);border:1px solid rgba(255,255,255,.04);}
        .sk-level{font-family:'Cormorant Garamond',serif;font-size:1.05rem;color:var(--gold);font-style:italic;}

        /* CONTACT & FOOTER */
        #contact{background:var(--cream);text-align:center;}
        .contact-email{font-family:'Cormorant Garamond',serif;font-size:clamp(1.4rem,2.8vw,2.6rem);color:var(--ink);text-decoration:none;display:block;margin:1.8rem 0;transition:color .3s;}
        footer{background:var(--ink2);padding:2rem 5rem;display:flex;justify-content:space-between;align-items:center;color:rgba(255,255,255,0.4);font-size:0.8rem;}

        /* ANIMATIONS */
        .reveal{opacity:0;transform:translateY(30px);transition:all .8s ease-out;}
        .reveal.visible{opacity:1;transform:translateY(0);}
        @keyframes fadeUp{from{opacity:0;transform:translateY(22px);}to{opacity:1;transform:translateY(0);}}
        @keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(110,231,183,.5);}50%{box-shadow:0 0 0 6px rgba(110,231,183,0);}}

        @media(max-width:960px){
            #home{grid-template-columns:1fr;}
            .hero-right{height:50vh;}
            nav{padding:1rem 2rem;}
            .nav-links{display:none;}
            .srv-grid, .proj-grid, .sk-grid{grid-template-columns:1fr;}
            .sec{padding:5rem 2rem;}
        }
    </style>
</head>
<body>

<div class="cursor" id="cur"></div>
<div class="cursor-follower" id="fol"></div>

<nav id="nav">
    <a href="#home" class="nav-logo">FE<span>.</span></a>
    <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
    <div class="nav-right">
        <a href="https://www.linkedin.com/in/fatimaezzahra-el-abbas/" target="_blank" class="nav-icon"><svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg></a>
    </div>
</nav>

<section id="home">
    <div class="hero-left">
        <div class="eyebrow"><span class="eyebrow-line"></span><span class="eyebrow-text">WordPress · Shopify · SEO Specialist</span></div>
        <h1 class="hero-name"><strong>Fatima-Ezzahra</strong><em>El Abbas</em></h1>
        <p class="hero-sub">Web Developer based in Casablanca, Morocco</p>
        <p class="hero-desc">I build websites that perform as beautifully as they look — 16+ live projects delivered across WordPress and Shopify.</p>
        <div class="hero-btns">
            <a href="#projects" class="btn-gold">View My Work</a>
            <a href="mailto:Fatimaezzahra.elabbas.dev@gmail.com" class="btn-outline">Contact Me</a>
        </div>
        <div class="hero-stats">
            <div><div class="stat-num">16+</div><div class="stat-label">Live Sites</div></div>
            <div><div class="stat-num">5</div><div class="stat-label">Internships</div></div>
            <div><div class="stat-num">3</div><div class="stat-label">Languages</div></div>
        </div>
    </div>
    <div class="hero-right">
        <img class="hero-img" src="images/fatima-photo.jpg" alt="Fatima-Ezzahra El Abbas" onerror="this.src='https://via.placeholder.com/800x1000?text=Fatima'"/>
        <div class="hero-overlay"></div>
        <div class="hero-photo-info">
            <div class="photo-name">Fatima-Ezzahra El Abbas</div>
            <div class="photo-tag"><span class="tag-dot"></span>Open to opportunities</div>
        </div>
    </div>
</section>

<section id="services" class="sec">
    <div class="section-header reveal">
        <div class="sec-label">What I offer</div>
        <h2 class="sec-title">My <strong>Services</strong></h2>
    </div>
    <div class="srv-grid">
        <div class="srv-card reveal">
            <div class="srv-name">WordPress Development</div>
            <p class="srv-desc">Custom themes, WooCommerce, and performance-first builds.</p>
        </div>
        <div class="srv-card reveal">
            <div class="srv-name">Shopify Store Setup</div>
            <p class="srv-desc">Conversion-focused e-commerce solutions and Liquid customization.</p>
        </div>
        <div class="srv-card reveal">
            <div class="srv-name">SEO & Performance</div>
            <p class="srv-desc">Technical audits and on-page optimization for maximum visibility.</p>
        </div>
    </div>
</section>

<section id="projects" class="sec">
    <div class="section-header reveal">
        <div class="sec-label">Live work</div>
        <h2 class="sec-title">Selected <strong>Projects</strong></h2>
    </div>
    <div class="proj-filter reveal">
        <button class="f-btn active" data-filter="all">All</button>
        <button class="f-btn" data-filter="wp">WordPress</button>
        <button class="f-btn" data-filter="sh">Shopify</button>
    </div>
    <div class="proj-grid" id="pg">
        <div class="p-card" data-t="wp">
            <div class="p-img">
                <img src="images/loghatouna.jpg" alt="Project" onerror="this.src='https://via.placeholder.com/400x250?text=WordPress+Site'">
                <span class="p-badge b-wp">WordPress</span>
            </div>
            <div class="p-body">
                <div class="p-name">Loghatouna</div>
                <p class="p-desc">Language learning platform with multilingual setup.</p>
                <a href="#" class="p-link">Visit Site →</a>
            </div>
        </div>
        <div class="p-card" data-t="sh">
            <div class="p-img">
                <img src="images/secretafricain.jpg" alt="Project" onerror="this.src='https://via.placeholder.com/400x250?text=Shopify+Store'">
                <span class="p-badge b-sh">Shopify</span>
            </div>
            <div class="p-body">
                <div class="p-name">Secret Africain</div>
                <p class="p-desc">E-commerce store for African artisan products.</p>
                <a href="#" class="p-link">Visit Site →</a>
            </div>
        </div>
    </div>
</section>

<section id="contact" class="sec">
    <div class="section-header reveal">
        <div class="sec-label">Get in touch</div>
        <h2 class="sec-title">Let's <strong>Collaborate</strong></h2>
    </div>
    <a href="mailto:Fatimaezzahra.elabbas.dev@gmail.com" class="contact-email">Fatimaezzahra.elabbas.dev@gmail.com</a>
</section>

<footer>
    <div class="f-logo">FE.</div>
    <div class="f-copy">&copy; 2024 Fatima-Ezzahra El Abbas. All rights reserved.</div>
</footer>

<script>
    // Cursor Logic
    const cur = document.getElementById('cur');
    const fol = document.getElementById('fol');
    document.addEventListener('mousemove', (e) => {
        cur.style.left = e.clientX + 'px';
        cur.style.top = e.clientY + 'px';
        fol.style.left = e.clientX + 'px';
        fol.style.top = e.clientY + 'px';
    });

    // Nav Scroll Effect
    window.addEventListener('scroll', () => {
        const nav = document.getElementById('nav');
        if(window.scrollY > 50) nav.classList.add('scrolled');
        else nav.classList.remove('scrolled');
    });

    // Project Filtering
    const filterBtns = document.querySelectorAll('.f-btn');
    const projects = document.querySelectorAll('.p-card');

    filterBtns.forEach(btn => {
        btn.addEventListener('click', () => {
            filterBtns.forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            const type = btn.getAttribute('data-filter');
            
            projects.forEach(p => {
                if(type === 'all' || p.getAttribute('data-t') === type) {
                    p.classList.remove('hidden');
                } else {
                    p.classList.add('hidden');
                }
            });
        });
    });

    // Reveal on Scroll
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if(entry.isIntersecting) entry.target.classList.add('visible');
        });
    }, { threshold: 0.1 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>

</body>
</html>
