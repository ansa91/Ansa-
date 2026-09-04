<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Cosmos — The Ultimate Space Explorer</title>

<meta name="description"
content="Explore the universe, Solar System, planets, stars, galaxies, black holes, astronauts, missions and the future of space exploration.">

<style>
/* =========================================================
   COSMOS SPACE WEBSITE
   Single-file HTML / CSS / JavaScript
   ========================================================= */

:root {
    --bg: #02030a;
    --bg2: #070b18;
    --panel: rgba(12, 18, 40, 0.78);
    --panel2: rgba(20, 28, 58, 0.7);
    --text: #f5f7ff;
    --muted: #a9b4d0;
    --line: rgba(255,255,255,.1);
    --accent: #7c8cff;
    --accent2: #55d6ff;
    --success: #6ef3b2;
    --danger: #ff6b9d;
    --max: 1200px;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    scroll-behavior: smooth;
}

html {
    scroll-padding-top: 80px;
}

body {
    font-family: Inter, Arial, Helvetica, sans-serif;
    background:
        radial-gradient(circle at 15% 10%, rgba(86,75,255,.16), transparent 30%),
        radial-gradient(circle at 85% 20%, rgba(0,210,255,.10), transparent 25%),
        var(--bg);
    color: var(--text);
    line-height: 1.7;
    overflow-x: hidden;
}

body.light {
    --bg: #eef3ff;
    --bg2: #ffffff;
    --panel: rgba(255,255,255,.78);
    --panel2: rgba(245,247,255,.9);
    --text: #10162d;
    --muted: #526078;
    --line: rgba(0,0,0,.1);
}

/* STARFIELD */
#stars,
#stars2 {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: -2;
}

#stars {
    background-image:
        radial-gradient(circle, rgba(255,255,255,.75) 1px, transparent 1px);
    background-size: 90px 90px;
    animation: starsMove 90s linear infinite;
}

#stars2 {
    background-image:
        radial-gradient(circle, rgba(130,180,255,.5) 1px, transparent 1px);
    background-size: 150px 150px;
    animation: starsMove 150s linear infinite reverse;
    opacity: .45;
}

@keyframes starsMove {
    from { transform: translateY(0); }
    to { transform: translateY(180px); }
}

/* NAVIGATION */
nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 72px;
    z-index: 1000;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 5%;
    background: rgba(2,3,10,.65);
    backdrop-filter: blur(18px);
    border-bottom: 1px solid var(--line);
}

.logo {
    display: flex;
    align-items: center;
    gap: 10px;
    font-weight: 900;
    font-size: 22px;
    letter-spacing: 1px;
}

.logo span {
    font-size: 28px;
}

nav ul {
    display: flex;
    list-style: none;
    gap: 25px;
}

nav a {
    color: var(--text);
    text-decoration: none;
    font-size: 14px;
    font-weight: 700;
    opacity: .85;
    transition: .25s;
}

nav a:hover {
    color: var(--accent2);
    opacity: 1;
}

.nav-buttons {
    display: flex;
    gap: 8px;
}

.icon-btn {
    width: 38px;
    height: 38px;
    border-radius: 50%;
    border: 1px solid var(--line);
    background: var(--panel);
    color: var(--text);
    cursor: pointer;
}

/* MOBILE MENU */
.menu-btn {
    display: none;
}

/* HERO */
.hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 120px 20px 70px;
    position: relative;
}

.hero-content {
    max-width: 1000px;
}

.badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    border: 1px solid rgba(124,140,255,.35);
    background: rgba(124,140,255,.09);
    border-radius: 999px;
    color: #aeb8ff;
    font-size: 13px;
    font-weight: 700;
    margin-bottom: 25px;
}

.hero h1 {
    font-size: clamp(52px, 9vw, 115px);
    line-height: .95;
    letter-spacing: -5px;
    margin-bottom: 28px;
    background: linear-gradient(100deg,#fff,#9ba9ff,#65e2ff);
    -webkit-background-clip: text;
    color: transparent;
}

.hero p {
    max-width: 760px;
    margin: auto;
    color: var(--muted);
    font-size: clamp(17px,2vw,21px);
}

.hero-actions {
    margin-top: 35px;
    display: flex;
    justify-content: center;
    gap: 12px;
    flex-wrap: wrap;
}

.btn {
    display: inline-block;
    padding: 13px 22px;
    border-radius: 12px;
    text-decoration: none;
    font-weight: 800;
    border: 1px solid var(--line);
    transition: .25s;
    cursor: pointer;
}

.btn-primary {
    color: white;
    background: linear-gradient(135deg,#6475ff,#3bc9ff);
    box-shadow: 0 15px 40px rgba(65,105,255,.22);
}

.btn-secondary {
    color: var(--text);
    background: var(--panel);
}

.btn:hover {
    transform: translateY(-3px);
}

/* FLOATING ORBIT */
.orbit {
    width: 260px;
    height: 260px;
    border: 1px solid rgba(100,150,255,.22);
    border-radius: 50%;
    position: absolute;
    right: 5%;
    bottom: 8%;
    opacity: .7;
}

.orbit::before {
    content: "🌍";
    position: absolute;
    width: 55px;
    height: 55px;
    display: grid;
    place-items: center;
    font-size: 36px;
    left: -27px;
    top: 102px;
    animation: orbitPlanet 9s linear infinite;
}

@keyframes orbitPlanet {
    from { transform: rotate(0deg) translateX(130px) rotate(0deg); }
    to { transform: rotate(360deg) translateX(130px) rotate(-360deg); }
}

/* GENERAL */
section {
    padding: 100px 5%;
}

.container {
    max-width: var(--max);
    margin: auto;
}

.section-label {
    color: var(--accent2);
    font-size: 13px;
    font-weight: 900;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 10px;
}

.section-title {
    font-size: clamp(34px,5vw,58px);
    line-height: 1.05;
    margin-bottom: 18px;
}

.section-intro {
    max-width: 760px;
    color: var(--muted);
    margin-bottom: 45px;
    font-size: 17px;
}

/* CARDS */
.grid {
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 20px;
}

.card {
    background: linear-gradient(
        145deg,
        rgba(255,255,255,.055),
        rgba(255,255,255,.018)
    );
    border: 1px solid var(--line);
    border-radius: 22px;
    padding: 28px;
    backdrop-filter: blur(12px);
    transition: .3s;
}

.card:hover {
    transform: translateY(-7px);
    border-color: rgba(120,150,255,.4);
    box-shadow: 0 20px 60px rgba(0,0,0,.25);
}

.card-icon {
    font-size: 42px;
    margin-bottom: 15px;
}

.card h3 {
    font-size: 23px;
    margin-bottom: 8px;
}

.card p {
    color: var(--muted);
}

.tag {
    display: inline-block;
    margin-top: 15px;
    padding: 5px 10px;
    border-radius: 999px;
    background: rgba(100,120,255,.12);
    color: #aeb8ff;
    font-size: 12px;
}

/* SOLAR SYSTEM */
.solar-system {
    position: relative;
    height: 540px;
    max-width: 900px;
    margin: 50px auto;
    display: grid;
    place-items: center;
}

.sun {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    background: radial-gradient(circle at 35% 35%,#fff5a6,#ffc52e,#ff7b00);
    box-shadow:
        0 0 45px #ffbd35,
        0 0 100px rgba(255,140,0,.35);
    display: grid;
    place-items: center;
    font-size: 45px;
    z-index: 4;
}

.planet-orbit {
    position: absolute;
    border: 1px solid rgba(150,170,255,.15);
    border-radius: 50%;
    animation: orbit 18s linear infinite;
}

.planet-orbit span {
    position: absolute;
    display: grid;
    place-items: center;
    border-radius: 50%;
}

.o1 { width:160px;height:160px; animation-duration:8s; }
.o2 { width:220px;height:220px; animation-duration:11s; }
.o3 { width:290px;height:290px; animation-duration:14s; }
.o4 { width:360px;height:360px; animation-duration:18s; }
.o5 { width:440px;height:440px; animation-duration:24s; }
.o6 { width:530px;height:530px; animation-duration:30s; }
.o7 { width:620px;height:620px; animation-duration:36s; }
.o8 { width:710px;height:710px; animation-duration:42s; }

.o1 span { top:-7px; left:50%; width:14px;height:14px;background:#aaa; }
.o2 span { top:-10px; left:50%; width:20px;height:20px;background:#d5a65a; }
.o3 span { top:-10px; left:50%; width:22px;height:22px;background:#5e9fff; }
.o4 span { top:-9px; left:50%; width:18px;height:18px;background:#d65c45; }
.o5 span { top:-17px; left:50%; width:34px;height:34px;background:#dca95d; }
.o6 span { top:-15px; left:50%; width:30px;height:30px;background:#d6c18b; }
.o7 span { top:-12px; left:50%; width:25px;height:25px;background:#83d5e8; }
.o8 span { top:-12px; left:50%; width:25px;height:25px;background:#4278dc; }

@keyframes orbit {
    from { transform: rotate(0); }
    to { transform: rotate(360deg); }
}

/* PLANET CARDS */
.planet-grid {
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:18px;
}

.planet {
    min-height:250px;
    cursor:pointer;
    overflow:hidden;
}

.planet-symbol {
    font-size:65px;
    margin-bottom:10px;
}

.planet small {
    color:var(--accent2);
}

/* INFO TABLE */
.info-table {
    width:100%;
    border-collapse:collapse;
    overflow:hidden;
    border-radius:18px;
}

.info-table th,
.info-table td {
    padding:15px;
    border-bottom:1px solid var(--line);
    text-align:left;
}

.info-table th {
    color:#aeb8ff;
    background:rgba(100,120,255,.08);
}

.info-table td {
    color:var(--muted);
}

/* FEATURE */
.feature {
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:30px;
    align-items:center;
}

.feature-box {
    min-height:380px;
    display:grid;
    place-items:center;
    border-radius:30px;
    border:1px solid var(--line);
    background:
        radial-gradient(circle,#17265d,transparent 55%),
        #060918;
    overflow:hidden;
}

.blackhole {
    width:190px;
    height:190px;
    border-radius:50%;
    background:#000;
    box-shadow:
        0 0 20px 10px #6c3cff,
        0 0 70px 25px rgba(255,77,189,.3);
    position:relative;
}

.blackhole::before {
    content:"";
    position:absolute;
    inset:-35px;
    border:14px solid transparent;
    border-top-color:#ff7cd8;
    border-bottom-color:#755cff;
    border-radius:50%;
    transform:rotate(-20deg);
}

/* TIMELINE */
.timeline {
    max-width:900px;
    margin:auto;
    position:relative;
}

.timeline::before {
    content:"";
    position:absolute;
    left:20px;
    top:0;
    bottom:0;
    width:2px;
    background:linear-gradient(var(--accent),var(--accent2));
}

.timeline-item {
    position:relative;
    padding-left:65px;
    margin-bottom:35px;
}

.timeline-dot {
    position:absolute;
    left:11px;
    top:5px;
    width:20px;
    height:20px;
    border-radius:50%;
    background:#67dfff;
    box-shadow:0 0 20px #67dfff;
}

.timeline-item h3 {
    color:#aeb8ff;
    font-size:21px;
}

/* FACTS */
.fact-grid {
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:15px;
}

.fact {
    text-align:center;
    padding:28px 15px;
    background:var(--panel);
    border:1px solid var(--line);
    border-radius:18px;
}

.fact strong {
    display:block;
    font-size:40px;
    color:var(--accent2);
}

/* SEARCH */
.search-wrap {
    max-width:700px;
    margin:0 auto 40px;
}

.search {
    width:100%;
    padding:17px 20px;
    border-radius:15px;
    border:1px solid var(--line);
    background:var(--panel);
    color:var(--text);
    outline:none;
    font-size:16px;
}

/* FAQ */
.faq {
    max-width:850px;
    margin:auto;
}

details {
    background:var(--panel);
    border:1px solid var(--line);
    border-radius:15px;
    margin-bottom:12px;
    padding:18px 20px;
}

summary {
    cursor:pointer;
    font-weight:800;
}

details p {
    color:var(--muted);
    padding-top:12px;
}

/* GLOSSARY */
.glossary {
    columns:2;
}

.glossary div {
    break-inside:avoid;
    padding:13px 0;
    border-bottom:1px solid var(--line);
}

.glossary b {
    color:#aeb8ff;
}

/* FOOTER */
footer {
    padding:70px 5% 30px;
    border-top:1px solid var(--line);
    background:rgba(0,0,0,.25);
}

.footer-grid {
    max-width:var(--max);
    margin:auto;
    display:grid;
    grid-template-columns:2fr 1fr 1fr;
    gap:40px;
}

footer h3 {
    margin-bottom:15px;
}

footer p,
footer li {
    color:var(--muted);
}

footer ul {
    list-style:none;
}

footer li {
    margin:7px 0;
}

.copyright {
    max-width:var(--max);
    margin:45px auto 0;
    padding-top:20px;
    border-top:1px solid var(--line);
    color:var(--muted);
    font-size:13px;
}

/* BACK TO TOP */
#top {
    position:fixed;
    right:20px;
    bottom:20px;
    width:45px;
    height:45px;
    border-radius:50%;
    border:1px solid var(--line);
    background:var(--panel);
    color:var(--text);
    cursor:pointer;
    opacity:0;
    pointer-events:none;
    transition:.3s;
    z-index:999;
}

#top.show {
    opacity:1;
    pointer-events:auto;
}

/* RESPONSIVE */
@media(max-width:1000px) {
    .planet-grid { grid-template-columns:repeat(2,1fr); }
    .grid { grid-template-columns:repeat(2,1fr); }
    .fact-grid { grid-template-columns:repeat(2,1fr); }
    .feature { grid-template-columns:1fr; }
    .orbit { display:none; }
}

@media(max-width:700px) {
    nav ul {
        position:absolute;
        top:72px;
        left:0;
        right:0;
        background:rgba(3,5,15,.97);
        display:none;
        flex-direction:column;
        padding:25px;
    }

    nav ul.open {
        display:flex;
    }

    .menu-btn {
        display:block;
    }

    .grid,
    .planet-grid,
    .fact-grid {
        grid-template-columns:1fr;
    }

    .solar-system {
        transform:scale(.55);
        margin:-40px auto;
        height:450px;
    }

    .glossary {
        columns:1;
    }

    .footer-grid {
        grid-template-columns:1fr;
    }

    section {
        padding:75px 5%;
    }

    .hero h1 {
        letter-spacing:-2px;
    }
}
</style>
</head>

<body>

<div id="stars"></div>
<div id="stars2"></div>

<!-- ======================================================
     NAVIGATION
====================================================== -->
<nav>
    <div class="logo">
        <span>🚀</span> COSMOS
    </div>

    <ul id="navLinks">
        <li><a href="#home">Home</a></li>
        <li><a href="#universe">Universe</a></li>
        <li><a href="#solar">Solar System</a></li>
        <li><a href="#planets">Planets</a></li>
        <li><a href="#missions">Missions</a></li>
        <li><a href="#facts">Facts</a></li>
    </ul>

    <div class="nav-buttons">
        <button class="icon-btn" id="themeBtn" title="Theme">☾</button>
        <button class="icon-btn menu-btn" id="menuBtn">☰</button>
    </div>
</nav>

<!-- ======================================================
     HERO
====================================================== -->
<header class="hero" id="home">

    <div class="hero-content">

        <div class="badge">
            ✦ THE ULTIMATE SPACE EXPLORER
        </div>

        <h1>Explore<br>the Cosmos</h1>

        <p>
            Space is vast, ancient and full of unanswered questions.
            Explore our Solar System, stars, galaxies, black holes,
            space missions and the future of human exploration.
        </p>

        <div class="hero-actions">
            <a class="btn btn-primary" href="#solar">
                Explore Solar System →
            </a>

            <a class="btn btn-secondary" href="#universe">
                Discover Universe
            </a>
        </div>

    </div>

    <div class="orbit"></div>

</header>

<!-- ======================================================
     UNIVERSE
====================================================== -->
<section id="universe">

<div class="container">

    <div class="section-label">01 / The Big Picture</div>

    <h2 class="section-title">
        What is the Universe?
    </h2>

    <p class="section-intro">
        The universe contains everything that exists: space, time,
        matter, energy, stars, planets, galaxies and the physical
        laws that govern them. Scientists estimate that the observable
        universe contains hundreds of billions of galaxies.
    </p>

    <div class="grid">

        <article class="card">
            <div class="card-icon">🌌</div>
            <h3>Galaxies</h3>
            <p>
                Galaxies are enormous systems containing stars, gas,
                dust, planets and dark matter. The Milky Way is the
                galaxy that contains our Solar System.
            </p>
            <span class="tag">COSMIC STRUCTURES</span>
        </article>

        <article class="card">
            <div class="card-icon">⭐</div>
            <h3>Stars</h3>
            <p>
                Stars are enormous spheres of hot plasma. Their energy
                is produced primarily through nuclear fusion in their
                cores.
            </p>
            <span class="tag">STELLAR SCIENCE</span>
        </article>

        <article class="card">
            <div class="card-icon">☁️</div>
            <h3>Nebulae</h3>
            <p>
                Nebulae are giant clouds of gas and dust. Some are
                regions where new stars form, while others are created
                by dying stars.
            </p>
            <span class="tag">STAR FORMATION</span>
        </article>

        <article class="card">
            <div class="card-icon">🕳️</div>
            <h3>Black Holes</h3>
            <p>
                A black hole is a region of spacetime with gravity
                strong enough that nothing that crosses its event
                horizon can escape.
            </p>
            <span class="tag">EXTREME GRAVITY</span>
        </article>

        <article class="card">
            <div class="card-icon">🌑</div>
            <h3>Dark Matter</h3>
            <p>
                Dark matter does not appear to emit or absorb light,
                but its gravitational influence can be observed in
                galaxies and larger cosmic structures.
            </p>
            <span class="tag">UNSEEN MATTER</span>
        </article>

        <article class="card">
            <div class="card-icon">⚡</div>
            <h3>Dark Energy</h3>
            <p>
                Dark energy is the name given to the unknown component
                associated with the accelerated expansion of the
                universe.
            </p>
            <span class="tag">COSMIC EXPANSION</span>
        </article>

    </div>
</div>
</section>

<!-- ======================================================
     BIG BANG
====================================================== -->
<section>

<div class="container">

    <div class="feature">

        <div>

            <div class="section-label">Origins</div>

            <h2 class="section-title">
                The Big Bang
            </h2>

            <p class="section-intro">
                The Big Bang model describes the early universe as an
                extremely hot, dense state that expanded and cooled
                over time. It was not simply an explosion into empty
                space; rather, space itself has been expanding.
            </p>

            <div class="grid">

                <article class="card">
                    <h3>13.8 Billion Years</h3>
                    <p>
                        Current measurements place the age of the
                        universe at roughly 13.8 billion years.
                    </p>
                </article>

                <article class="card">
                    <h3>Cosmic Expansion</h3>
                    <p>
                        Distant galaxies generally appear to be moving
                        away from one another as space expands.
                    </p>
                </article>

            </div>

        </div>

        <div class="feature-box">
            <div style="font-size:110px;">🌌</div>
        </div>

    </div>

</div>
</section>

<!-- ======================================================
     SOLAR SYSTEM
====================================================== -->
<section id="solar">

<div class="container">

    <div class="section-label">02 / Our Neighborhood</div>

    <h2 class="section-title">
        The Solar System
    </h2>

    <p class="section-intro">
        Our Solar System is centered on the Sun. Eight planets,
        numerous moons, dwarf planets, asteroids and comets orbit
        the Sun under its gravitational influence.
    </p>

    <div class="solar-system">

        <div class="sun">☀️</div>

        <div class="planet-orbit o1"><span></span></div>
        <div class="planet-orbit o2"><span></span></div>
        <div class="planet-orbit o3"><span></span></div>
        <div class="planet-orbit o4"><span></span></div>
        <div class="planet-orbit o5"><span></span></div>
        <div class="planet-orbit o6"><span></span></div>
        <div class="planet-orbit o7"><span></span></div>
        <div class="planet-orbit o8"><span></span></div>

    </div>

</div>
</section>

<!-- ======================================================
     PLANETS
====================================================== -->
<section id="planets">

<div class="container">

    <div class="section-label">03 / Worlds</div>

    <h2 class="section-title">
        The Eight Planets
    </h2>

    <p class="section-intro">
        The planets are divided into rocky terrestrial planets
        and giant planets. Each world has its own atmosphere,
        geology, temperature and history.
    </p>

    <div class="planet-grid">

        <article class="card planet">
            <div class="planet-symbol">☿️</div>
            <small>PLANET 01</small>
            <h3>Mercury</h3>
            <p>
                The smallest planet and the closest planet to the Sun.
                Mercury has a heavily cratered surface and almost no
                substantial atmosphere.
            </p>
        </article>

        <article class="card planet">
            <div class="planet-symbol">♀️</div>
            <small>PLANET 02</small>
            <h3>Venus</h3>
            <p>
                Venus is similar in size to Earth but has a dense
                carbon-dioxide atmosphere and an intense greenhouse
                effect that makes its surface extremely hot.
            </p>
        </article>

        <article class="card planet">
            <div class="planet-symbol">🌍</div>
            <small>PLANET 03</small>
            <h3>Earth</h3>
            <p>
                Earth is a rocky planet with abundant liquid surface
                water and the only world currently known to support
                life.
            </p>
        </article>

        <article class="card planet">
            <div class="planet-symbol">🔴</div>
            <small>PLANET 04</small>
            <h3>Mars</h3>
            <p>
                Mars is known as the Red Planet because iron minerals
                in its surface materials have oxidized. It contains
                enormous volcanoes and canyons.
            </p>
        </article>

        <article class="card planet">
            <div class="planet-symbol">🟠</div>
            <small>PLANET 05</small>
            <h3>Jupiter</h3>
            <p>
                Jupiter is the largest planet in the Solar System.
                It is a gas giant with powerful storms, including
                the famous Great Red Spot.
            </p>
        </article>

        <article class="card planet">
            <div class="planet-symbol">🪐</div>
            <small>PLANET 06</small>
            <h3>Saturn</h3>
            <p>
                Saturn is a gas giant surrounded by an enormous,
                bright ring system made primarily of particles of
                ice and rock.
            </p>
        </article>

        <article class="card planet">
            <div class="planet-symbol">🔵</div>
            <small>PLANET 07</small>
            <h3>Uranus</h3>
            <p>
                Uranus is an ice giant with a blue-green appearance.
                Its axis is tilted dramatically, causing unusual
                seasonal patterns.
            </p>
        </article>

        <article class="card planet">
            <div class="planet-symbol">🔷</div>
            <small>PLANET 08</small>
            <h3>Neptune</h3>
            <p>
                Neptune is the farthest recognized planet from the
                Sun. It is an ice giant with some of the fastest
                planetary winds known.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     PLANET DATA
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Quick Reference</div>

    <h2 class="section-title">
        Planet Comparison
    </h2>

    <div style="overflow-x:auto">

        <table class="info-table">

            <thead>
                <tr>
                    <th>Planet</th>
                    <th>Type</th>
                    <th>Day Length</th>
                    <th>Year Length</th>
                    <th>Moons</th>
                </tr>
            </thead>

            <tbody>
                <tr>
                    <td>Mercury</td>
                    <td>Rocky</td>
                    <td>≈ 59 Earth days</td>
                    <td>88 Earth days</td>
                    <td>0</td>
                </tr>

                <tr>
                    <td>Venus</td>
                    <td>Rocky</td>
                    <td>≈ 243 Earth days</td>
                    <td>225 Earth days</td>
                    <td>0</td>
                </tr>

                <tr>
                    <td>Earth</td>
                    <td>Rocky</td>
                    <td>≈ 24 hours</td>
                    <td>365 days</td>
                    <td>1</td>
                </tr>

                <tr>
                    <td>Mars</td>
                    <td>Rocky</td>
                    <td>≈ 24.6 hours</td>
                    <td>687 days</td>
                    <td>2</td>
                </tr>

                <tr>
                    <td>Jupiter</td>
                    <td>Gas giant</td>
                    <td>≈ 9.9 hours</td>
                    <td>≈ 11.86 years</td>
                    <td>Many</td>
                </tr>

                <tr>
                    <td>Saturn</td>
                    <td>Gas giant</td>
                    <td>≈ 10.7 hours</td>
                    <td>≈ 29.5 years</td>
                    <td>Many</td>
                </tr>

                <tr>
                    <td>Uranus</td>
                    <td>Ice giant</td>
                    <td>≈ 17.2 hours</td>
                    <td>≈ 84 years</td>
                    <td>Many</td>
                </tr>

                <tr>
                    <td>Neptune</td>
                    <td>Ice giant</td>
                    <td>≈ 16 hours</td>
                    <td>≈ 165 years</td>
                    <td>Many</td>
                </tr>
            </tbody>

        </table>

    </div>

</div>
</section>

<!-- ======================================================
     SUN & MOON
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Stars & Satellites</div>

    <h2 class="section-title">
        The Sun & The Moon
    </h2>

    <div class="grid">

        <article class="card">
            <div class="card-icon">☀️</div>
            <h3>The Sun</h3>
            <p>
                The Sun is a star at the center of our Solar System.
                Its gravity keeps the planets in orbit, while its
                energy drives Earth's climate and nearly all surface
                ecosystems.
            </p>
            <br>
            <p>
                The Sun is primarily composed of hydrogen and helium.
                Nuclear fusion in its core converts hydrogen into
                helium and releases enormous amounts of energy.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🌙</div>
            <h3>The Moon</h3>
            <p>
                Earth's Moon is our planet's natural satellite.
                Its gravitational interaction with Earth contributes
                significantly to ocean tides.
            </p>
            <br>
            <p>
                The Moon is tidally locked to Earth, meaning the same
                side generally faces our planet as it orbits.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🌘</div>
            <h3>Phases of the Moon</h3>
            <p>
                The Moon appears to change shape during its monthly
                cycle because we see different portions of its
                sunlit half as it moves around Earth.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     BLACK HOLES
====================================================== -->
<section>

<div class="container">

    <div class="feature">

        <div class="feature-box">
            <div class="blackhole"></div>
        </div>

        <div>

            <div class="section-label">Extreme Physics</div>

            <h2 class="section-title">
                Black Holes
            </h2>

            <p class="section-intro">
                Black holes are among the most extreme objects in
                the universe. They can form when massive stars collapse,
                and supermassive black holes can exist at the centers
                of galaxies.
            </p>

            <div class="grid">

                <article class="card">
                    <h3>Event Horizon</h3>
                    <p>
                        The boundary beyond which escape from the
                        black hole is impossible.
                    </p>
                </article>

                <article class="card">
                    <h3>Accretion Disk</h3>
                    <p>
                        Hot material orbiting a black hole can form
                        a bright disk as it falls inward.
                    </p>
                </article>

            </div>

        </div>

    </div>

</div>
</section>

<!-- ======================================================
     STARS
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Stellar Evolution</div>

    <h2 class="section-title">
        The Life of a Star
    </h2>

    <p class="section-intro">
        Stars are born from clouds of gas and dust. Their eventual
        fate depends strongly on their mass.
    </p>

    <div class="grid">

        <article class="card">
            <div class="card-icon">☁️</div>
            <h3>1. Stellar Nursery</h3>
            <p>
                Gravity causes dense regions within molecular clouds
                to collapse and form young stars.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">⭐</div>
            <h3>2. Main Sequence</h3>
            <p>
                A star spends much of its life converting hydrogen
                into helium through nuclear fusion.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🔴</div>
            <h3>3. Giant Phase</h3>
            <p>
                When core hydrogen is depleted, many stars expand
                dramatically and become giants.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">💥</div>
            <h3>4. Supernova</h3>
            <p>
                Some massive stars end their lives in powerful
                explosions that can create and distribute heavy
                elements.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">⚪</div>
            <h3>5. White Dwarf</h3>
            <p>
                Lower-mass stars can leave behind extremely dense
                stellar remnants called white dwarfs.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🕳️</div>
            <h3>6. Black Hole</h3>
            <p>
                The cores of sufficiently massive stars can collapse
                into black holes.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     SPACE OBJECTS
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Cosmic Objects</div>

    <h2 class="section-title">
        Asteroids, Comets & Meteors
    </h2>

    <div class="grid">

        <article class="card">
            <div class="card-icon">☄️</div>
            <h3>Comets</h3>
            <p>
                Comets are icy bodies that can develop glowing comas
                and tails when they approach the Sun.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🪨</div>
            <h3>Asteroids</h3>
            <p>
                Asteroids are rocky or metallic objects that orbit
                the Sun. Many are concentrated in the main asteroid
                belt between Mars and Jupiter.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🔥</div>
            <h3>Meteors</h3>
            <p>
                A meteoroid becomes a meteor when it enters an
                atmosphere and produces a visible streak of light.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     SPACE TECHNOLOGY
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Human Technology</div>

    <h2 class="section-title">
        How Humans Explore Space
    </h2>

    <div class="grid">

        <article class="card">
            <div class="card-icon">🚀</div>
            <h3>Rockets</h3>
            <p>
                Rockets generate thrust by accelerating mass in the
                opposite direction. They carry spacecraft beyond
                Earth's atmosphere and into orbit.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🛰️</div>
            <h3>Satellites</h3>
            <p>
                Artificial satellites support communication,
                navigation, weather observation, Earth science
                and astronomy.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🔭</div>
            <h3>Space Telescopes</h3>
            <p>
                Telescopes in space can observe wavelengths that
                are blocked or distorted by Earth's atmosphere.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🤖</div>
            <h3>Robotic Probes</h3>
            <p>
                Robotic spacecraft explore places that are too
                distant, cold, hot or dangerous for humans.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">👨‍🚀</div>
            <h3>Spacesuits</h3>
            <p>
                Spacesuits provide oxygen, pressure, temperature
                control and protection from the harsh space environment.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🏠</div>
            <h3>Space Stations</h3>
            <p>
                Space stations provide laboratories where astronauts
                can conduct long-duration experiments in microgravity.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     ASTRONAUTS
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Human Spaceflight</div>

    <h2 class="section-title">
        Life in Space
    </h2>

    <p class="section-intro">
        Living in space requires astronauts to adapt to microgravity,
        radiation, isolation and limited resources.
    </p>

    <div class="grid">

        <article class="card">
            <h3>🛌 Sleeping</h3>
            <p>
                Astronauts use sleeping bags attached to surfaces so
                they do not float around the spacecraft while sleeping.
            </p>
        </article>

        <article class="card">
            <h3>🍽️ Food</h3>
            <p>
                Space food is specially prepared to remain safe,
                compact and practical in microgravity.
            </p>
        </article>

        <article class="card">
            <h3>💪 Exercise</h3>
            <p>
                Regular exercise is essential during long missions
                because microgravity can cause loss of muscle and bone.
            </p>
        </article>

        <article class="card">
            <h3>🧪 Science</h3>
            <p>
                Astronauts perform experiments in biology, physics,
                medicine, materials science and Earth observation.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     MISSIONS TIMELINE
====================================================== -->
<section id="missions">

<div class="container">

    <div class="section-label">04 / Exploration</div>

    <h2 class="section-title">
        Historic Space Milestones
    </h2>

    <div class="timeline">

        <div class="timeline-item">
            <div class="timeline-dot"></div>
            <h3>1957 — Sputnik 1</h3>
            <p>
                The Soviet Union launched Sputnik 1, the first
                artificial satellite to orbit Earth.
            </p>
        </div>

        <div class="timeline-item">
            <div class="timeline-dot"></div>
            <h3>1961 — First Human in Orbit</h3>
            <p>
                Yuri Gagarin became the first human to travel into
                space and orbit Earth.
            </p>
        </div>

        <div class="timeline-item">
            <div class="timeline-dot"></div>
            <h3>1969 — Apollo 11</h3>
            <p>
                Apollo 11 carried humans to the lunar surface,
                marking the first crewed Moon landing.
            </p>
        </div>

        <div class="timeline-item">
            <div class="timeline-dot"></div>
            <h3>1990 — Hubble</h3>
            <p>
                The Hubble Space Telescope began observing the
                universe from orbit above Earth's atmosphere.
            </p>
        </div>

        <div class="timeline-item">
            <div class="timeline-dot"></div>
            <h3>1998 — International Space Station</h3>
            <p>
                Construction of the International Space Station
                began through a large international partnership.
            </p>
        </div>

        <div class="timeline-item">
            <div class="timeline-dot"></div>
            <h3>2021 — James Webb Space Telescope</h3>
            <p>
                The James Webb Space Telescope launched to study
                the universe primarily through infrared observations.
            </p>
        </div>

        <div class="timeline-item">
            <div class="timeline-dot"></div>
            <h3>Future — Human Deep-Space Exploration</h3>
            <p>
                Future missions may expand human exploration of the
                Moon, Mars and other destinations.
            </p>
        </div>

    </div>

</div>
</section>

<!-- ======================================================
     SEARCHABLE SPACE TOPICS
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Explore</div>

    <h2 class="section-title">
        Space Knowledge Search
    </h2>

    <p class="section-intro">
        Search the topics below to quickly find information.
    </p>

    <div class="search-wrap">
        <input
            class="search"
            id="spaceSearch"
            type="search"
            placeholder="Search planets, stars, Mars, black holes..."
        >
    </div>

    <div class="grid" id="searchCards">

        <article class="card searchable">
            <h3>🌍 Earth</h3>
            <p>
                Our home world, with oceans, a nitrogen-rich atmosphere,
                active geology and known life.
            </p>
        </article>

        <article class="card searchable">
            <h3>🔴 Mars</h3>
            <p>
                A cold rocky world with polar ice, ancient river
                features, volcanoes and dust storms.
            </p>
        </article>

        <article class="card searchable">
            <h3>🪐 Saturn</h3>
            <p>
                A gas giant famous for its rings and large collection
                of moons.
            </p>
        </article>

        <article class="card searchable">
            <h3>⭐ Stars</h3>
            <p>
                Stars shine because nuclear fusion releases energy
                from their hot interiors.
            </p>
        </article>

        <article class="card searchable">
            <h3>🕳️ Black Holes</h3>
            <p>
                Extreme gravitational objects with event horizons.
            </p>
        </article>

        <article class="card searchable">
            <h3>🌌 Milky Way</h3>
            <p>
                The galaxy containing our Solar System.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     AMAZING FACTS
====================================================== -->
<section id="facts">

<div class="container">

    <div class="section-label">05 / Did You Know?</div>

    <h2 class="section-title">
        Amazing Space Facts
    </h2>

    <div class="fact-grid">

        <div class="fact">
            <strong>8</strong>
            Recognized planets orbit the Sun.
        </div>

        <div class="fact">
            <strong>1</strong>
            Star is at the center of our Solar System.
        </div>

        <div class="fact">
            <strong>1</strong>
            Natural satellite orbits Earth.
        </div>

        <div class="fact">
            <strong>13.8B</strong>
            Approximate age of the universe in years.
        </div>

        <div class="fact">
            <strong>∞</strong>
            Space contains an enormous number of objects.
        </div>

        <div class="fact">
            <strong>🌡️</strong>
            Space has extreme temperature environments.
        </div>

        <div class="fact">
            <strong>🌌</strong>
            The universe is expanding.
        </div>

        <div class="fact">
            <strong>🚀</strong>
            Humans have traveled beyond low Earth orbit.
        </div>

    </div>

</div>
</section>

<!-- ======================================================
     SEARCH FOR LIFE
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Are We Alone?</div>

    <h2 class="section-title">
        The Search for Life
    </h2>

    <p class="section-intro">
        Scientists search for signs of life beyond Earth by studying
        planets, moons, atmospheres and chemical environments.
        So far, Earth remains the only world where life is confirmed.
    </p>

    <div class="grid">

        <article class="card">
            <div class="card-icon">🔴</div>
            <h3>Mars</h3>
            <p>
                Mars preserves evidence that liquid water existed on
                its surface in the distant past, making it a major
                target for astrobiology.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🧊</div>
            <h3>Europa</h3>
            <p>
                Jupiter's moon Europa has an icy exterior and strong
                evidence for a subsurface ocean.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🌊</div>
            <h3>Enceladus</h3>
            <p>
                Saturn's small moon Enceladus ejects plumes of material
                from beneath its icy surface.
            </p>
        </article>

        <article class="card">
            <div class="card-icon">🪐</div>
            <h3>Exoplanets</h3>
            <p>
                Thousands of planets have been confirmed around stars
                beyond our Sun. Some orbit within potentially interesting
                temperature ranges.
            </p>
        </article>

    </div>

</div>
</section>

<!-- ======================================================
     GLOSSARY
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Space Dictionary</div>

    <h2 class="section-title">
        Space Glossary
    </h2>

    <div class="glossary">

        <div><b>Asteroid:</b> Rocky or metallic body orbiting the Sun.</div>

        <div><b>Atmosphere:</b> A layer of gases surrounding a world.</div>

        <div><b>Black Hole:</b> A region where gravity prevents escape beyond its event horizon.</div>

        <div><b>Comet:</b> An icy Solar System body that can develop a coma and tail.</div>

        <div><b>Exoplanet:</b> A planet orbiting a star other than the Sun.</div>

        <div><b>Galaxy:</b> A huge gravitationally bound collection of stars and other matter.</div>

        <div><b>Gravity:</b> The attractive interaction associated with mass and energy.</div>

        <div><b>Light-Year:</b> The distance light travels in one year.</div>

        <div><b>Meteor:</b> A visible streak produced when a meteoroid enters an atmosphere.</div>

        <div><b>Meteorite:</b> A piece of space rock that survives atmospheric entry and reaches the ground.</div>

        <div><b>Nebula:</b> A large cloud of gas and dust in space.</div>

        <div><b>Orbit:</b> The curved path of an object under gravity.</div>

        <div><b>Planet:</b> A large body orbiting a star that meets the accepted planetary criteria.</div>

        <div><b>Satellite:</b> An object that orbits another object; it may be natural or artificial.</div>

        <div><b>Solar System:</b> The Sun and the objects gravitationally associated with it.</div>

        <div><b>Supernova:</b> A powerful stellar explosion or related catastrophic stellar event.</div>

    </div>

</div>
</section>

<!-- ======================================================
     FAQ
====================================================== -->
<section>

<div class="container">

    <div class="section-label">Questions</div>

    <h2 class="section-title">
        Frequently Asked Questions
    </h2>

    <div class="faq">

        <details>
            <summary>How many planets are in our Solar System?</summary>
            <p>
                There are eight recognized planets: Mercury, Venus,
                Earth, Mars, Jupiter, Saturn, Uranus and Neptune.
            </p>
        </details>

        <details>
            <summary>Is Pluto a planet?</summary>
            <p>
                Pluto is classified as a dwarf planet. It is still
                an important object in the outer Solar System.
            </p>
        </details>

        <details>
            <summary>Can humans live in space?</summary>
            <p>
                Humans can live in space with specialized spacecraft
                and life-support systems, but the environment is not
                naturally suitable for human survival.
            </p>
        </details>

        <details>
            <summary>Can we travel to another galaxy?</summary>
            <p>
                With current technology, intergalactic travel is far
                beyond our practical capabilities. The distances are
                extraordinarily large.
            </p>
        </details>

        <details>
            <summary>Is there life outside Earth?</summary>
            <p>
                No extraterrestrial life has been scientifically
                confirmed so far. The search remains an active area
                of scientific research.
            </p>
        </details>

        <details>
            <summary>Why is space dark?</summary>
            <p>
                Space itself does not glow like an atmosphere. Light
                travels through it, but most directions do not contain
                enough visible light reaching our eyes to appear bright.
            </p>
        </details>

        <details>
            <summary>What is a light-year?</summary>
            <p>
                A light-year is a unit of distance: the distance
                light travels through vacuum in one year.
            </p>
        </details>

    </div>

</div>
</section>

<!-- ======================================================
     FOOTER
====================================================== -->
<footer>

    <div class="footer-grid">

        <div>
            <div class="logo">
                <span>🚀</span> COSMOS
            </div>

            <p style="margin-top:15px">
                A digital journey through planets, stars, galaxies,
                black holes and humanity's exploration of the universe.
            </p>
        </div>

        <div>
            <h3>Explore</h3>

            <ul>
                <li><a href="#universe">Universe</a></li>
                <li><a href="#solar">Solar System</a></li>
                <li><a href="#planets">Planets</a></li>
                <li><a href="#missions">Missions</a></li>
            </ul>
        </div>

        <div>
            <h3>Learn</h3>

            <ul>
                <li><a href="#facts">Space Facts</a></li>
                <li><a href="#universe">Galaxies</a></li>
                <li><a href="#universe">Black Holes</a></li>
                <li><a href="#missions">Space History</a></li>
            </ul>
        </div>

    </div>

    <div class="copyright">
        © 2026 Cosmos Explorer · Made for curious minds 🚀
    </div>

</footer>

<button id="top" title="Back to top">↑</button>

<script>
/* =========================================================
   COSMOS JAVASCRIPT
========================================================= */

/* MOBILE MENU */
const menuBtn = document.getElementById("menuBtn");
const navLinks = document.getElementById("navLinks");

menuBtn.addEventListener("click", () => {
    navLinks.classList.toggle("open");
});

document.querySelectorAll("#navLinks a").forEach(link => {
    link.addEventListener("click", () => {
        navLinks.classList.remove("open");
    });
});


/* THEME */
const themeBtn = document.getElementById("themeBtn");

themeBtn.addEventListener("click", () => {

    document.body.classList.toggle("light");

    if (document.body.classList.contains("light")) {
        themeBtn.textContent = "☀";
    } else {
        themeBtn.textContent = "☾";
    }

});


/* BACK TO TOP */
const topButton = document.getElementById("top");

window.addEventListener("scroll", () => {

    if (window.scrollY > 500) {
        topButton.classList.add("show");
    } else {
        topButton.classList.remove("show");
    }

});

topButton.addEventListener("click", () => {
    window.scrollTo({
        top:0,
        behavior:"smooth"
    });
});


/* SEARCH */
const searchInput = document.getElementById("spaceSearch");
const cards = document.querySelectorAll(".searchable");

searchInput.addEventListener("input", () => {

    const query = searchInput.value.toLowerCase().trim();

    cards.forEach(card => {

        const text = card.textContent.toLowerCase();

        if (text.includes(query)) {
            card.style.display = "";
        } else {
            card.style.display = "none";
        }

    });

});


/* PLANET CARD CLICK */
document.querySelectorAll(".planet").forEach(card => {

    card.addEventListener("click", () => {

        const name = card.querySelector("h3").textContent;

        alert(
            name +
            " — Scroll through the Cosmos website to learn more about this world."
        );

    });

});


/* SIMPLE STAR PARALLAX */
window.addEventListener("mousemove", event => {

    const x = (event.clientX / window.innerWidth - .5) * 10;
    const y = (event.clientY / window.innerHeight - .5) * 10;

    document.getElementById("stars").style.transform =
        `translate(${x}px, ${y}px)`;

});


/* KEYBOARD SHORTCUT */
document.addEventListener("keydown", event => {

    if (event.key === "/" && document.activeElement !== searchInput) {

        event.preventDefault();
        searchInput.focus();

    }

});


/* YEAR */
const copyright = document.querySelector(".copyright");

copyright.innerHTML =
    copyright.innerHTML.replace(
        "2026",
        new Date().getFullYear()
    );
</script>

</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>ANSA — Dark Matter</title>
<meta name="description" content="Advance National Space Agency — an interactive explainer on dark matter.">
<style>
:root{
  --bg:#05070b; --panel:#0b1018; --text:#eef3ff; --muted:#9da9bd;
  --line:rgba(255,255,255,.10); --gold:#f3c86b; --cyan:#79d7ff;
  --max:1120px;
}
*{box-sizing:border-box} html{scroll-behavior:smooth}
body{margin:0;background:var(--bg);color:var(--text);font-family:Inter,ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;line-height:1.65}
a{color:inherit;text-decoration:none}.container{width:min(var(--max),calc(100% - 40px));margin:auto}
nav{position:fixed;z-index:20;top:0;left:0;right:0;background:rgba(5,7,11,.70);backdrop-filter:blur(16px);border-bottom:1px solid var(--line)}
.navin{height:72px;display:flex;align-items:center;justify-content:space-between}
.brand{display:flex;align-items:center;gap:11px;font-weight:800;letter-spacing:.08em}
.brand img{width:72px;height:42px;object-fit:cover;object-position:center;border-radius:6px}
.navlinks{display:flex;gap:24px;color:#c7d0df;font-size:14px}.navlinks a:hover{color:#fff}
.hero{min-height:94vh;display:grid;place-items:center;position:relative;overflow:hidden}
.hero:before{content:"";position:absolute;inset:0;background:
 radial-gradient(circle at 72% 35%,rgba(119,161,255,.18),transparent 24%),
 radial-gradient(circle at 25% 70%,rgba(245,180,75,.12),transparent 26%),
 linear-gradient(180deg,rgba(5,7,11,.1),#05070b 94%)}
.hero-media{position:absolute;inset:0;background-image:linear-gradient(180deg,rgba(5,7,11,.12),rgba(5,7,11,.72)),url('data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAMCAgICAgMCAgIDAwMDBAYEBAQEBAgGBgUGCQgKCgkICQkKDA8MCgsOCwkJDRENDg8QEBEQCgwSExIQEw8QEBD/2wBDAQMDAwQDBAgEBAgQCwkLEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBD/wAARCAByAOUDASIAAhEBAxEB/8QAHQAAAQUBAQEBAAAAAAAAAAAAAAECAwQGBQcJCP/EAEgQAAEDAgUCAwUGAwMHDQAAAAECAxEABAUGBxIhMUETUWEIFCJxoRcyUoGR0yOWsQkWwRVCV4bR0vAmJzM3RkdWcnaSo+Hx/8QAGAEBAQEBAQAAAAAAAAAAAAAAAAECBAP/xAAgEQEBAQEAAwEBAAMBAAAAAAAAARECEiExA0FRkeGB/9oADAMBAAIRAxEAPwD5x/bhrVE/bFnefL+8F3+5QNcNazx9sOd/zzDd/uViKKI241x1qJA+2LO/8w3f7lSr1q1qRP8Azy51WJIBTmK75jv/ANJPesKPPyp6NpUAskJnkgSQPlRW1Ot+tJPw6wZ4HA/7Q3f7lH23a1ESNYs7/wAw3f7lYqAFHYSRPEjrRMcRRG1Gt2tU86w54/mG7/cpzetutBcAXrDniCef+UN5/v1iRI56UoPPeia2x1s1on4dYc8Ef+obv9yk+2zWn/TDnj+Ybv8AcrHIbW4YQkmp1WmwIDi0oKyOVAwB58c/ShrWDWzWbaQdX89buCCMxXcDzkb/AJUn22a0zH2wZ4/mG7/crFk1cfRhibG3XbPPKuyT4yVJAQPKDPNS3FntqPtr1o/0w54/mG7/AHKUa160d9YM8/zDd/uVjImntW9xcKKWWlLISpcAf5oEk/kAa1cn1PbYjWrWbmdYs8Dj/wAQ3f7lINataD/3w54/mG7/AHKxyZIImO59anfsXGiktrDyS2lxSkJVCJEwZA5E/L502T6Zb8ax3WfWlpxTStYc7yglJjMV0RIPYhyDSp1r1j2rnV/PRVHwxmK7gGe/x+U1jnH3HW0tOEEI4BKRIHlPWPTpUY56cGribW1GtGs5MfbDnj+Yrv8Acp41m1l76xZ5P+sN3+5WM5ACiD8XIPnT0lABmd3Y+Rp6Jv8AW4t9Z9W0k+8at57XIMRmO7EH/wB9NRrDrKf451bz4tlCgFRmK7HXtO/iYNYrdwFbeZ60qXXdpbk7T1A6R8qw3rYJ1l1j2lJ1fzyVHof7xXfH/wAlKdZNY+Y1hzyf9Ybv9yssxbNXV+LW2ePhrc2oW6AkxPBUATH61czFgdzlzFXsJvHWHHWFFClsOpdbVHdKkkhQ9RU8+Z1Of6ePXj5fx3BrJrJP/XDnn+Yrv/froL1N1mThTWKnWvOOx55bKWhma6LoKUgyU75CTMA+YPlWDPh+ICiVIHmOtSuXL7jDLa3dyGpS2mR8MmTxV631hzZ716VlHWHPFvjIbztqhqPcWQlLqLbNF2y6g8jiVHkHsR2rk4nq/qsm8dGHaw59FvuPhhzMd2VAepC6xygph5JeCHCQlwgOBQIIBglJ688jqDIMEVOi1D9m7dl9IUlQ+A9T8qkkl8tW31ibMucM65r92/vVnjMONm13+AMQxN658HdG7b4ijtnamY6wPKiuS4oBXSaK3jOuNS0K60cdelRQIpwNNPpRJP60RasrR68d8NkCQCokmAAPWi6dS4sJS0hsAAHZ0JA601KUptS944CyvaGx1Ijkn6VFPHU1J7PhZqe3ZLygEieYquBPWa7mXFWjF+w/dx4batxBEzHpWkekYHpw1hmVV5lxh0M7kS02R8Sq8yxe7TcXKygDan4U1ps5akYhmNsWLbik2zY2pSOAB6CsSSFK+9A86tvrGJPem9T60p5ihKdxIgnjzqdCGkBKnFHdvKVNlMEDiD/X9KzreGqUhTQkbVphIgcKHMkmevQcdqYFFKpQSJnvVvEXLJT82KFJb2xCoJ6c1T6ngVJ7KeVpKEoCACmZPc1Nb3t3bNvMsXC0IfQEOJSTC0yDB8xIB/KoEIW4QhCSonoAKUQJB5npBiDVslmUls+Jn7O6t2mbh9opRcpK2zx8QBgkfmCPyNRDbACQZA+Ik9T6flFdxmzsMaxC2s7a5Fm17uhKlXC5SlwJ+OIHAKtxA9a5Fw0GHltJUFBJIkd6c3fVOp/gLcfUhpLq3ChCSGgomAmSTt9Jn85pqSQZ6x0pASeeeOnpSjg81rGd9ntNqedDTaCpazCUjzq6F4nh4fwxQNr48NvJWjaeDMEkSOYqk2oocCwqNpkHuKuXl+/fFy4uHrhy6uFEvOqXPipJBEjuZE9T28q8+pvq/HpzcUgSkylRHlUouXlOFxxW8kEfGArgiO/9e1IGlKBB6AeXJ/49acUbQBt/OtekMUsiE7pmpWWi4tKWwVE9Qfn0pirZ1CEOLTCVztJ7gda7WVHcOZxBHv6IAWDungJ5kR37d+3rU76znYvM241WW9Hs1Zisl4hZ4c6phtJUXdp2gDzrK3+CXVlersA80nYrapS3AlI/M9uK/T2YPaisMI0tTptk/Cre1aUAq4uUpHiuq2/i8vSvytjWKOYjdl9YSCf80Dgef51y/j1+v6X36j2/XnjiST3VAoSs8gcedFOQ6hE7mkrnznj9CKK6/bncVQ57c0lLPEcc+lEcTRolOEdqQVKtralKgsHd9KJTRtO1IATAMnzroWmFJu7G7vhctNi2AIbWr4lyeg865sczTwtQEdv60JQDApQtXQGmH1pRHeqiVDhBCkqhQ5pCCDE9KYggLBKQoA9POnwTAFBZtL16zDvglI8Vstq3ICuPz6fMVG+89cvLuHnCtazKiaYttbaihxJSodQoRTak5kuxdtmU7mYkVIUoQ4RIWkTyOJ461EfSkmD1rTKQGORXQQxh7mHqdNwpNylQARt4UnzmqDYG3cpY8o79KAeomPnSzV+HiUng/pTtygdyVmSCDHXmmCY7frTgCZgRRMAAjjrTiQpZISEyeg6D9aelontSj4Vhbo3+YJ6+lQNbU2kkrSVSCAAYgx1/pQhAUlR3gKSBAMyrnoOPWeaaes/Sunlh/DbbHLN7F2w5ZodSXknumeanXqas+thpXlrAs140jCcYxD3NDkBKzABUfMnpWx1q0Bf0123VpjFpiNqpCV+JbuhYEjpI78151m/EsvIzNc3eTw+xYqWFsJUeUjuDTLrPWPXlp7le4i5cMpSUhC1FSYIjof61yXj9PPy5vr/Do5648fHqf+s8EIbUUubu/SPX/GKtXuJM3NtZtt2Nuy5boKVONn4nfiPKuevb5RVJxxSlFUdfSouivIV15v14SrKnnLlQQhCU7UkfejdE8meJ+UUxdu4jatxBCVczHalsnEN3CC6n4Nw3cdq9Q1Xzdp7j+Xsv4dk7LaMNubCzS1fule43L08r9K871eepzI1JOpbawWB5WxbNSrhzCLe2/gKBcSu6aYCd0wE+Isbuh6THfrRXLQkNoCnWiUr+4ZgGOD86K1Z3vqz/AF/1Jec9y/7/AODKWRM75/vnsMyJk3HMx3lu1471vhGHPXjrbUhO9SWkqITKgJIiSB3qtmHLOZMo4m7gma8vYlguIscO2mI2jls8jv8AEhwBQ6jqK/WP9nTf4/hiPaAxHKd5iFpjNtpJiztg/h7i0XTVwl1goU0pELSsKggp5mIr1FWWdUdbfZN0zwv2jcExTH874tqtZ4Rk1eYn1WeMYjg7zQN00bt1CnhbqVJ8VQXyEH4tqBWh86xE811MEyxmbMreIOZcy7ieKowmzcxG/VZWjj4tLRuN77pQD4baZErVCRPJr6WZk9lH2csbwvLOMWWQ8rWN9het2DZIxe1yxf4y9Yu2L9y00/Y3D19sLzydxKnWEtgbgAB3n0QwHQ6/9ov2ldF8lZMtNMMsYBp5m3K+LYw5ib15va9/bacvXA6YbS0jdtSD9xI3EmSQ+XaELWsIQCpSjAAEkmuvmjJub8kYkjBs6ZUxjAMQcaTcItMTsXbV5TSiQlYQ4kKKSQQDEGD5V7n7YeR8taUe0zc6aZa0tbyhgWWXLW0sU+9vXD2M28JKcQdecWpKlPTuAbCEpEJ27kqJ+jXtL6X6Z+0LrVYZ0zSbWxt/Z2vGrjO7ZWA5fZdOFpxS3cKonYLhD1uW07lQ4tQKZoj455pyZnHI98zhedcp4zl+9uLdN2zb4pYO2rrjCipKXUpcSCpBKVAKHBKT5GuS2y8+VBlpbhQkrVtSTAHUmO1fVPX7L1h7QGrOWNc8/wCR8pYjg1p7P+XsxYivMGL31hhWF3mIXl2ppamrJDl1cgKU4EspUkED4nEnaa6+RtL9INGdec9WenWmlleYbm72Z3s6Kw1xy+8Iurf8N60YbdIuG2XwholLn8ZCkwCiSkUx8lwy8ltL5aWG1EpSvadpPkDTkFxH8ZEjYR8Q7HmP6V9BUN5G1B9hzRTJ+I5AwPArPOeqN3gC8ZL1yRlxL978V0kqdCVFLSiiHSU7UTwqVVb9p72dvZpy3kbV/BMq5StcCzBpqqzVhT2D2eYbm6QneEFOMOXLJtALhBK2nGy2iSnapxPKoY+e2IYje4rdKvMQuVvvLABWsySAIH0quBwY7etfrH+0SwDQ/S/WrGND9ItF7XKq8rXFo9c4w3i91crv03Fgw8GvCeUoNpSXRyFEkhR6EAfk9J2EKgSPMTV1MJPbikMg0opY3cR054qyoclBUBEkq4AT1/SgDjdI4gRUzqrbwmUWyFhez+MVngq3HlPkIjr61DEnmkurfSxcXS7twOLbaQdoT/DbCAY7wO5qfD2w48lJAMnmapDgGKuWLpadCwDwanXz0T69LwTTm7zMkv4bh4SkACEyeg9fPr+dZ7NGTL/A3lNXNspspMGRXqWjWrVplBxPvVu28jyWAQD5xTdXs+YPmp1VzaNICl8qVtAmuHz756dd44vOvAnEbCZqP4Y6xVnEFDxiUxHpVMKIIUOSK7Zdjk+HhzceBH/1T/E7FI7VDJE9vlQJI5Paqiyltak8JMzB4NMKHB51awzGLvC7tN2ypK3ArcoOJCwrvyD1rS4tmnLuOW6HVZYtcMv0JIccslLDTx/EUKJCT/5YHpWfKz+LkY8kQdxO7oPQUpJUI28AdqR4I8QlPQmlKkoaHhOOJWoFLiZhKhII/wAOPSfldXBKkgFSTsP3SUSD5xRUTm3dKSQKKGOtkHU/UfSvE7jGtNM9Y7la/u2Dav3OEX7lq66zuCvDUpsglO5KTB4kDyqxmXWHVrOeYsPzfm7U7NeNY5hC0uYdiV/jFw/c2Skq3pLLq1lTUKAUNpEETWQFFB6bmL2nPaJzZds3uZNbc64g7b3triTHjY0+UM3Vsrcw82jdtQttUqSpIBCiT1JNZq21P1Gs8UzHjdpnrHGcQzhb3NpmC6RfuJdxVi4VufbuVAy6lxXKgqQo9ay9FFaHMuoWe86JwhOb84YzjYwG0RYYX/lC9cfNlbI+4y0VklCE9kjgdq6GLawasY9cY9d4zqVme9dzTbsWuOLexV9ZxNlkAMt3Mq/jJRA2hchMcRWPHWnhM+lEehZe9ojXfKuMWWP5d1ezZYYhhuDtZetX2cVeBZwtqS1ZpG6PBQVEpbjak8gA81Czr7rfb5ywvUNGrebVZnwWzTh1hizmLvuXTFokqIt0uKUVeFK1y2TtO5UgyawZQRQmAfi6URtWdaNWEZYx/JI1Gx/+7+aLpV/jGGG+cNreXJWlxTy25KfEUtCCVAAnaJMAVbzfr7rfqDlezyTnnVrNuPYDYkKZw/EcXffYkH4SpKlELKeiSqSkcJgcVgBEHjntTuYoO1mzOGbNQMxXebc75kxLHsbvvD96xDEbldxcPbEJbRvcWSpW1CEJEngJA7VzLh9b5SVpQClIT8KQkQBHbv61CBz0p3JgTRSc96cKRKVKSVBJIT1PlQImDVQ4qUUhO7gGQKchakHckwSkifQ8GmmP1oBFVDu/TrTkHb0kU2R84p0AK2ggieDQX7O5fTuU2sAIEnmKe/iTzqdqnCRXPSn4wPESEkxuPQesdY/KkIUU8J6dT6Vjxm61p6iFnlQ/OujiisunDrBOEs3abwNn30vKBQV7j9wASBEde9cncDxA44FJMAfKqyeEhQiTNdjDMsYvirSnrCxceSgSrakmK46SQqY6Gv0z7MmouRcsM3Vlm2zbdS42Qkq7E15/r3eZsen58zvrK/PScEcDF89cXbNu5aJBDLpIcdJVEJEckda5iSoCRXoWst/geI5uu7vAQlNu4okBPSvPR5RPPWt/n158+VTueNw5KTG4jikI9Irp4P8A5G8Zb2N292q1DLqUm2IB8bYfDkqBEboJHlMRXOBTu5jjtVl25jOZNROGCAaKkO09QKK1hrlA0optKDPasrS0oikooJRsUuEAhPkTNd/BMHZxBwI8RIiOves6kwa6mHXS2gp5NwltSBIB6qrPUv8AGubI0WZ8vtWyUPIZQ2doSpKBxIHWsg8yUL2gT8q61xmG7umw064VAdq5qL19q4FwwvY4Pukdu1SaXFbpzTgTFNMydw5706tsfCzzTlKBA4jimjnpFKPnQKPKl48jTalDy+ZKeSTykdxQHhObA8W1eHO3dHE+U+dNAg0EqIieB0E0da1Ep4bcLanQglCVBJUOgJmB9D+lIN0bZMdYoSEEckz24pyVQIgdZ6VfgQAzPIBMTTp+ECAO8+dNPXinTKYqUJECYn+lJE9AadPFAPXd8orIUFWwfF3PEn/j/wDKmZfdb+4simNliF+IlW6PgIPQz3pqYJ5JFRYmduy4jYtAJmQsnn5VD0PHFSKNoq2bS2y6HwpRccLgKCnjaAnbIIMyZMyOBHMUyOk1qIelRBBEcGef9lJyTyTSwiZAMR3PeP8AbTSQOpqheaKOexooOVQOKKKy2dTwnjpUUmnB1aeAfoKESbZ5JAgdPOkk9jUZcUep+lAUod6CT86ASDNR71edG9XnRMS8mndhxz3qEOLT0V6UeIvz+lDEwpQeYqAOrSQQeRz0o8Rfn9KGLFOEVV8Vz8X0pfGc/F9KGLUnbtBgHmJpQlRIAB56VU8Z38X0qxZYtiGH3bN7avhLzCgpsqbSsAjnooEH5EVdTEkEU4pKTBnkVVevbl91b7rgK3FFSoQAJPoBA/Kmm5fPVc/MCmmLcc80vBHU1S95e/H9BR7y9+P6CmmLwWgIIKCVEiDugAd+KUkjvJNUDcvEAFQ4M/dFHvD34/oKi46CkDhQJUniVQepHSrGIXiL58Pt2VvaoS2lAbYSQmAIkySST1JnrXH94e/H9BQLl8dHCPyFTP6ZV+OPKkB5gVR95f6eJ9BSi6uACkOGCZIgcmqmOihTqlLdC/iHxEqUJPPr15P+NIFJJO9JIg8BXeOD+sVzveX/AMf0FL7y/wDj+goYvKCkgbh15FFUDcOq6q+goq6eKOiiio0KKKKAooooCiiigKKKKAooooCiiigKKKKAooooCiiigKKKKAooooCiiigKKKKAooooP//Z');background-size:cover;background-position:center;filter:saturate(.9);opacity:.68}
.stars{position:absolute;inset:0;background-image:radial-gradient(1px 1px at 15% 25%,#fff,transparent),radial-gradient(1px 1px at 55% 20%,#fff,transparent),radial-gradient(1px 1px at 85% 62%,#fff,transparent),radial-gradient(1px 1px at 42% 78%,#fff,transparent),radial-gradient(1px 1px at 70% 42%,#fff,transparent);background-size:220px 180px,310px 240px,280px 220px,260px 210px,360px 280px;opacity:.5}
.hero-content{position:relative;z-index:2;padding-top:80px;max-width:900px}
.eyebrow{font-size:12px;letter-spacing:.24em;text-transform:uppercase;color:var(--gold);font-weight:800}
h1{font-size:clamp(58px,10vw,126px);line-height:.9;margin:20px 0 28px;letter-spacing:-.06em}
.hero p{font-size:clamp(17px,2vw,21px);color:#c8d1df;max-width:700px}
.cta{display:flex;gap:12px;margin-top:30px;flex-wrap:wrap}.btn{padding:12px 18px;border:1px solid var(--line);border-radius:999px;background:rgba(255,255,255,.06);font-weight:700}.btn.primary{background:#fff;color:#080a0f}.btn:hover{transform:translateY(-2px)}
section{padding:105px 0}.section-head{display:flex;justify-content:space-between;gap:30px;align-items:end;margin-bottom:42px}
h2{font-size:clamp(35px,5vw,62px);line-height:1.02;letter-spacing:-.045em;margin:8px 0}.lead{color:var(--muted);max-width:640px;font-size:18px}
.grid2{display:grid;grid-template-columns:1.1fr .9fr;gap:28px;align-items:center}
.card{background:linear-gradient(145deg,rgba(255,255,255,.055),rgba(255,255,255,.018));border:1px solid var(--line);border-radius:24px;overflow:hidden}
.card img{display:block;width:100%;height:100%;object-fit:cover}.copy{padding:30px}
.statgrid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:28px}.stat{padding:24px;border:1px solid var(--line);border-radius:18px;background:#090d14}.stat b{font-size:28px;display:block;color:#fff}.stat span{color:var(--muted);font-size:13px}
.quote{font-family:Georgia,serif;font-size:clamp(26px,4vw,44px);line-height:1.25;color:#f7e5b7;text-align:center;max-width:900px;margin:0 auto}
.imageband{height:500px;position:relative;overflow:hidden}.imageband img{width:100%;height:100%;object-fit:cover;filter:saturate(.9)}.imageband:after{content:"";position:absolute;inset:0;background:linear-gradient(90deg,#05070b 0%,transparent 35%,transparent 65%,#05070b 100%)}
.evidence{display:grid;grid-template-columns:repeat(2,1fr);gap:18px}.evidence .card{min-height:360px}
.tags{display:flex;flex-wrap:wrap;gap:9px;margin-top:18px}.tag{border:1px solid var(--line);border-radius:999px;padding:7px 11px;color:#c9d2df;font-size:12px}
.candidates{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}.candidate{padding:26px;border:1px solid var(--line);border-radius:20px;background:linear-gradient(160deg,#0c121c,#080b11)}.candidate .num{font-size:12px;color:var(--gold);letter-spacing:.2em}.candidate h3{font-size:22px;margin:15px 0 8px}.candidate p{color:var(--muted);font-size:14px}
.footer{padding:45px 0 60px;border-top:1px solid var(--line);color:#7f8b9f;font-size:13px}.footerin{display:flex;justify-content:space-between;gap:20px}
.reveal{opacity:0;transform:translateY(24px);transition:.7s ease}.reveal.show{opacity:1;transform:none}
@media(max-width:800px){.navlinks{display:none}.container{width:min(var(--max),calc(100% - 26px))}.grid2,.evidence{grid-template-columns:1fr}.statgrid,.candidates{grid-template-columns:1fr}.imageband{height:360px}.hero{min-height:85vh}section{padding:75px 0}.section-head{display:block}}
</style>
</head>
<body>
<nav><div class="container navin">
  <a class="brand" href="#top"><img src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAMCAgICAgMCAgIDAwMDBAYEBAQEBAgGBgUGCQgKCgkICQkKDA8MCgsOCwkJDRENDg8QEBEQCgwSExIQEw8QEBD/2wBDAQMDAwQDBAgEBAgQCwkLEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBD/wAARCABIAH0DASIAAhEBAxEB/8QAHQABAAIDAQEBAQAAAAAAAAAAAAcIBQYJBAECA//EADIQAAIBAwMDBAEEAQIHAAAAAAECAwQFBgAHEQgSIRMUIjEVCRYyQSNCURczNFJxcpL/xAAaAQEAAwEBAQAAAAAAAAAAAAAAAQIDBAUG/8QAKhEAAgECBAUDBQEAAAAAAAAAAAECAxEEEiExE0FRcZFhobEFFSIzgcH/2gAMAwEAAhEDEQA/AOVWmmmgGmmmgGmmmgGmmnB0A01941nLDhGS5HPTR0FFDTxVbdsVZcayGgo/9Q5apqXSFByjjlnAJUj78aAwWmt0t20+R3z3EGO3PH7tX0qkyW6kvFOapzzx2wRsw925/pKf1WP3xx51pegGmmmgGmmmgGmmmgGmmmgGvdZbJcsguMVrtVOJZ5mA5Z1SOMEgF5HYhY0HPl2IVR5JA15KeCWqnjpoIy8srBEVRyWYngAa2K63k2i3HE7V2pACr10qdwNZMOeGbnz2qGYKOAOCSQGLE6QinrLYpNtaR3MpSUG3GMz0j3mefJqlQJaiGF2p6EMGP+LvH+aZSoAYqYSCSFJADtNu0e5G06VHtMl6d8LltDKxVo6eSrq4uWLAqZ5iZCPrtdz4/rnzqrqSuAVB+xwf/Gshabi1BIsiSydynlQHZVB/o+CDqXNWtFF6aSknPU6W7b9O3R9vtPH+Ax84pclmWZbnb4ZmRmPgxzUFW0sXYC6+Ye0DgMeByoqh1cdL2a7I5MtzvN1a/Wm8cyW+/JK88dYi+ArOfqQKF5QnkAj+uCdYw/fvJsaaGShrZfdwn/HVpIY5ovkWBjcfxIYkg8cefr75niw78UW4mHXXbvcFIK+03SMcx+n/AJYpuGK1lKvkRyr5LBTxyXHHBKnwXR+oUZ8bNmV9udvh+L+vI+oj9txdPhw/B257X77r49FuVS2exGfLtxLXRNX1Vtt9tc3a73SlPbJbbdSj1qmpVv6dI0bsH20hRR8mAOBzPIf3dmF9ysUS0f5q5VVx9urdwh9aVpOwHgcgd3HPA+tStl+Z4zt9tdetkcYsNbT5BdbhTS5DkXqNELrQxs80NIYGLdsSuaaZWQp6jKCwbsjbUI69hO6ufMzjkk0NNNNSVGmmmgGmmmgGrS9HnQLnvVrar9lFLkVPi2P2kGlpq+qpHm99X8AiJFBUdiggyP3EqWQBW5JWNOmTp4yfqR3MpcLsqtT2ymC1d7uJ8LR0YYBiDwQZW/jGvHljyeFDMOkm83W5hvRNU4JsdtXilJcKWwvA98oI5/UNBafIaHnksKqTu9UM5HHxZgwk1NuYOVuU4Zle1Ob37CMttstuyGwVEttqKYnyJeewlSP5IyklWHhlZSOQdWa3h/TA3z2n2ZpN3I7jQZJPDTCsv1ltkMjVFshK93qK31UKg/5hUL2fY70DOLHfqR7C4fvhhWO9aex9TSXKCSmpTfTSRfKuoCQIqtuPPqQ+I5FYdwUDuI9LjVlupvq8tHTBfNrDk1G1VieViut93kgUNNRNGtKYqkD7dV75A6DyVYkclQplttJELc4TY5ZpciyC2WCGYQyXOtgo1kYchDI4QEj++OedXvvf6QW5tFujYNv7BuhaLjb7jQT3K6Xma3tTpbYo5EQKIfUdpncv8QCo+J5Kjzrc+pvojxqTM8Z6nOnI0NTilwu1vut3tlA6mnihedHNbR9vx9Aqe5ox/Dyy/HlUtZuJ1aWTBd27BW2m3/urFay0VVNerpZ62maO0yJOhjd2kdY3XxKHUP3IF54PgHnr4ijho5681FdW0vk2o0KuIllpRcn6K/wVQb9GqSmdoW6prAkiMVZHsXaykfYI914Oo46g+hqXpI28bdyXqDsN9qaWvpqO3W+ntzxTVNRIx+KkSuAFjWRz3eOEI+yAdrzi8/pxZLlNwraLC0hrq6eeoqp7jmlXDEJ3fu7lFI9RG6HuJ+MgI+u3nxrE7idEO1932jyLqG2qyOjvGP2ehkrYbNaL7LU05FP/ANR3VM0LSFgoduwqhHaByOe7VaeNjP8AUnLsnZ9m7J+TSWFnT1qNL+q/hXa8FO6Gz5bvRm2PYtjNue5ZBe5Y7ZSwJwDLKXPBY/SgBuSx8AKSfonU5dYH6fW4PSbjmP5lV5JS5TY7qRSV1ZR0kkQt9d293pMGJ5jYBuyTkElGBVfj3Wj6KtiLPs1gg6stxKKjwWc2qWpp4acNKlPamQN7iRql55FmlXjgRGNgp7eCXKiZOnnqf2266tpdwdqM8pJopJJKmknoJpF9ybXK59pVxlu5RMnxDEdwWVFbgK6DW0ZSnLWNvH+NmMrWve5xMPg8aa3ve/aLItjdzL1txkas8ltnPtasRlY62lYkxTpz9qy/fBPawZT5U60TVnoUGmmmgGmmmgLo9MPWNRbCbU1eG7ebJXi63iujnqqq6o3qCorVRVDuFQn0ozJEvaD4DD/U5JjDYDqGzzAd5r3ullWCf8Q0yuKpo8opKy3LK9XDOrTyBSY2WP4ws/Z29hjiYEBVBWDaLIsgtqLHbr7caVUjeFVgqnQLG5DOo4PhWIBI+iQCdfqlyXI6F1losguVO6qEVoquRCFEfpAAg/Xp/D/18fXjU3IsX4wfr3tmD5RktdQ7E3ux7OXq20wNkt1DGtPb61wyGSJQI4I4qhVfuUcdzoXHJ7+Y26mur/H+oxrfDNsxc6224tFLU28VVXJD6SzmGP1qgQ89yFhCoAdBy/HcxZeKo/ufJfxs1m/cNz/H1KRxzUnu5PRkSNmaNWTntIVncqCPBYkfZ15VuVxSnajS4VKwOoVohKwRgCSARzwQO5v/AKP++sK1Hj6Sk0uidvdWfubUqvB1jFX6tX9ndexaLZXqZy3bm4fj852XNywWiiMf4qhoaiL8aTM4742lZueZY5gRIx5dG4YFTrL7udWGMbr70YDmuSbJ1I23weWrVLLLQxMbhMFV5hKhAhIUGmLRHuCqSWJDgaqYMhv60slCt8uAppUEUkIqX7HQO0gUrzwR3u7cf9zsfsnXxL7e41Kx3iuUFJIyBUOAUdWV1+/plZgR/YYg/Z1Sjg8Ph3mpwSfW2r7vd/1l62Lr11lqTbXS+i7LZHQiHq76QquihuUXQzSNST+p6U8WE2l439NWZ+1u3g9qo5P+wUk/R1lrj177cQYqNt8I6Xcht2J1Zp/zNtprTBRQezrE9SNVgg+B90pUAsVDo7Ed3I1zhS/X2O3R2dL1XrQQvJJHSipcQo8i9kjBOe0Fl+LHjyPB8a/rS5Rk1DMtRRZFc6eWOaOoV4quRGWWNmaNwQfDKzuVP2CzEfZ115mc2VFs+sDrhyLqXxy3bd4NiN6sOOUtUhusEh5krankingdY/ARSjMEJPc4B4BjGpGxPrW2a2zoaK5Yt0mXHGLj+KFI1xpLbTpNLTRExODU9iySxiSmZSzH+UJ58qeKAU98vVJLNPS3ethkqJVmmeOodWkkVu5XYg+WDfIE+QfOvTU5fllagjrMou06LFLAFlrZWAjleSSROC38XeWV2H0WkcnkseYuxZFhOrfe+xb4Rw11Ttrkdhv+P1fspauvp1j7FkDN7ab+w3KMyq3kcScDy2qy69VddrrdHZ7nc6urZ5nqGM8zSEyuFDue4n5MEXk/Z7Rz9DXl1DdwlYaaaaEjTTTQDTTTQDTTTQDTTTQDTTTQDTTTQDTTTQDTTTQH/9k=' alt="ANSA logo"><span>ANSA / RESEARCH</span></a>
  <div class="navlinks"><a href="#what">What is it?</a><a href="#evidence">Evidence</a><a href="#study">Study</a><a href="#candidates">Candidates</a></div>
</div></nav>

<header class="hero" id="top">
  <div class="hero-media"></div><div class="stars"></div>
  <div class="container hero-content reveal">
    <div class="eyebrow">Advance National Space Agency · Cosmic Science</div>
    <h1>Dark<br>Matter</h1>
    <p>Most of the universe may be made of something we cannot see. We infer dark matter from the gravity it exerts on stars, galaxies and the fabric of spacetime.</p>
    <div class="cta"><a class="btn primary" href="#what">Explore the mystery ↓</a><a class="btn" href="#evidence">View evidence</a></div>
  </div>
</header>

<section id="what"><div class="container reveal">
  <div class="section-head"><div><div class="eyebrow">01 · The invisible universe</div><h2>What is dark matter?</h2></div>
  <p class="lead">Dark matter does not emit, absorb or reflect light in a way our telescopes can directly detect. Yet its gravitational influence appears across the cosmos.</p></div>
  <div class="grid2">
    <div class="card"><div class="copy">
      <p>When astronomers measure how galaxies rotate, how galaxy clusters move, and how light bends around massive objects, the visible matter alone often cannot account for what they observe.</p>
      <p>The leading explanation is an unseen form of matter that adds gravity without shining. It is called <strong>dark matter</strong>.</p>
      <div class="statgrid"><div class="stat"><b>~27%</b><span>of the universe's total energy budget is commonly attributed to dark matter.</span></div><div class="stat"><b>Gravity</b><span>is our strongest observational clue.</span></div><div class="stat"><b>Unknown</b><span>its microscopic identity remains unresolved.</span></div></div>
    </div></div>
    <div class="card" style="height:100%"><img src='data:image/jpeg;base64,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' alt="Deep-space galaxy cluster"></div>
  </div>
</div></section>

<div class="imageband"><img src='data:image/jpeg;base64,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' alt="Galaxy cluster from the supplied reference"></div>

<section><div class="container reveal"><p class="quote">“We may not see dark matter itself — but we can map its presence by watching how gravity reshapes the universe.”</p></div></section>

<section id="evidence"><div class="container reveal">
  <div class="section-head"><div><div class="eyebrow">02 · Evidence</div><h2>Gravity leaves fingerprints.</h2></div>
  <p class="lead">From the motion of galaxies to the bending of distant light, several independent observations point toward additional unseen mass.</p></div>
  <div class="evidence">
    <article class="card"><img src='data:image/jpeg;base64,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' alt="Colorful galaxy-cluster observation"><div class="copy"><div class="eyebrow">Galaxy clusters</div><h3>Collisions reveal separation</h3><p>In merging clusters, hot gas can be observed through X-rays while gravitational lensing can trace where most of the mass is concentrated. The two distributions can differ.</p></div></article>
    <article class="card"><div class="copy"><div class="eyebrow">Gravitational lensing</div><h3>Mass bends spacetime.</h3><p>Massive clusters warp spacetime, magnifying and distorting the light of galaxies behind them. Measuring that distortion lets astronomers reconstruct an invisible mass map.</p><div class="tags"><span class="tag">Einstein</span><span class="tag">Lensing</span><span class="tag">Mass maps</span></div></div></article>
  </div>
</div></section>

<section id="study"><div class="container reveal">
  <div class="section-head"><div><div class="eyebrow">03 · Research program</div><h2>Studying dark matter</h2></div>
  <p class="lead">ANSA-style mission science can combine astronomical observations, precision detectors and computational models to narrow the possibilities.</p></div>
  <div class="grid2">
    <div class="card"><div class="copy">
      <h3>Three complementary approaches</h3>
      <p><strong>Look up:</strong> survey galaxies and lensing to map where unseen mass is distributed.</p>
      <p><strong>Look down:</strong> search for rare interactions in shielded detectors deep underground.</p>
      <p><strong>Look across:</strong> use particle-physics experiments and astrophysical signals to test candidate particles.</p>
    </div></div>
    <div class="card"><img src='data:image/jpeg;base64,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' alt="Deep-field stars and galaxies"></div>
  </div>
</div></section>

<section id="candidates"><div class="container reveal">
  <div class="section-head"><div><div class="eyebrow">04 · The candidates</div><h2>What could it be?</h2></div><p class="lead">No candidate has yet been confirmed as the dark matter particle. Different theories predict different signatures.</p></div>
  <div class="candidates">
    <article class="candidate"><div class="num">01 / WIMP</div><h3>Weakly interacting particles</h3><p>Hypothetical particles that could interact through gravity and the weak force while remaining difficult to detect.</p></article>
    <article class="candidate"><div class="num">02 / AXION</div><h3>Ultra-light fields</h3><p>Very light particles proposed in particle physics that could behave collectively on enormous cosmic scales.</p></article>
    <article class="candidate"><div class="num">03 / BEYOND</div><h3>Something unexpected</h3><p>The final answer may require new physics beyond today's best-tested particle models.</p></article>
  </div>
</div></section>

<section><div class="container reveal"><div class="card"><div class="copy" style="text-align:center;padding:55px 28px">
  <div class="eyebrow">ANSA · COSMIC FRONTIER</div><h2>The universe is full of clues.</h2><p class="lead" style="margin:0 auto 24px">Every galaxy, every distorted arc of light, and every missing piece of mass brings us closer to understanding what holds the cosmos together.</p>
  <a class="btn primary" href="#top">Back to the stars ↑</a>
</div></div></div></section>

<footer class="footer"><div class="container footerin"><span>© 2026 Advance National Space Agency (ANSA) · Concept website</span><span>Dark Matter Research / Educational</span></div></footer>

<script>
const obs=new IntersectionObserver(entries=>entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('show')}),{threshold:.12});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
</script>
</body></html>
