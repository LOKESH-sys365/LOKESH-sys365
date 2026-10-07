## Hi there 👋
![My GIF](githubgif.gif)

<!--
**LOKESH-sys365/LOKESH-sys365** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

<!DOCTYPE html>
<!-- ============================================================
  ⚡ Pokémon Skill Cards — portfolio skills section
  HOW TO USE:
  1. Save this file, open it in any browser.
  2. To embed in your portfolio (React/Next.js): copy the <style>
     block into your CSS and the card markup into your component.
  3. To change a skill's level, edit the badge class/text + xp-fill width.
  4. HOVER EASTER EGG: hovering a card reveals the SHINY version
     of the Pokémon (like the dev.to article).
  5. Professors: to use real character sprites, drop image URLs into
     the .prof-avatar divs (replace the letter).
     Sprite source for Pokémon: github.com/PokeAPI/sprites (free, hotlinkable)
============================================================= -->
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Tech Stack — Pokémon Edition</title>
<style>
  * { margin:0; padding:0; box-sizing:border-box; }
  body {
    background:#0d0d1a;
    font-family:'Segoe UI', system-ui, sans-serif;
    color:#eaeaf2;
    padding:48px 20px;
    min-height:100vh;
  }
  .container { max-width:1100px; margin:0 auto; }
  h1 {
    text-align:center; font-size:2rem; letter-spacing:1px; margin-bottom:6px;
  }
  h1 .pokeball { font-size:1.6rem; vertical-align:middle; }
  .subtitle {
    text-align:center; color:#8a8aa3; margin-bottom:34px; font-size:.95rem;
  }
  .subtitle b { color:#c8c8e0; }

  .grid {
    display:grid;
    grid-template-columns:repeat(auto-fill, minmax(220px, 1fr));
    gap:16px;
  }

  /* ---------- skill card ---------- */
  .card {
    position:relative;
    background:linear-gradient(160deg, rgba(255,255,255,.05), rgba(255,255,255,.01));
    border:1px solid rgba(255,255,255,.09);
    border-top:3px solid var(--c);
    border-radius:14px;
    padding:20px 14px 16px;
    text-align:center;
    transition:transform .25s ease, box-shadow .25s ease;
    box-shadow:0 0 0 rgba(0,0,0,0);
  }
  .card:hover {
    transform:translateY(-6px) scale(1.02);
    box-shadow:0 10px 34px var(--glow);
  }

  .sprite-wrap {
    position:relative; height:96px; width:96px; margin:0 auto 8px;
    display:flex; align-items:center; justify-content:center;
  }
  .sprite {
    position:absolute; inset:0; margin:auto; max-width:100%; max-height:100%;
    image-rendering:pixelated;
    filter:drop-shadow(0 0 12px var(--glow));
    transition:opacity .25s ease;
  }
  .sprite.shiny { opacity:0; }
  .card:hover .sprite.normal { opacity:0; }
  .card:hover .sprite.shiny { opacity:1; }
  /* keep the shiny sparkle subtle pre-hover */
  .card:hover .sprite { filter:drop-shadow(0 0 18px var(--c)); }

  .dots { display:flex; gap:8px; justify-content:center; margin-bottom:8px; }
  .dots span { width:10px; height:10px; border-radius:50%; opacity:.9; display:inline-block; }

  .skill-name { font-weight:700; font-size:1.02rem; margin-bottom:6px; letter-spacing:.3px; }

  .chain { display:flex; align-items:center; justify-content:center; gap:4px; margin-bottom:10px; min-height:30px; }
  .chain-img { width:30px; height:30px; image-rendering:pixelated; opacity:.45; filter:grayscale(70%); }
  .chain-img.current { opacity:1; filter:none; transform:scale(1.35); filter:drop-shadow(0 0 6px var(--c)); }
  .arrow { color:#55556e; font-size:.8rem; }

  .level-row { margin-bottom:8px; }
  .badge {
    display:inline-block; font-size:.62rem; font-weight:800; letter-spacing:1.2px;
    padding:4px 10px; border-radius:20px;
  }

  .xp {
    height:6px; background:rgba(255,255,255,.08); border-radius:6px; overflow:hidden;
  }
  .xp-fill {
    height:100%; border-radius:6px;
    box-shadow:0 0 8px var(--glow);
  }

  /* ---------- professors / database section ---------- */
  h2.section-title {
    text-align:center; font-size:1.5rem; margin:56px 0 6px; letter-spacing:1px;
  }
  .prof { border-top-color:#e3350d; }
  .prof-wrap { border-radius:50%; background:radial-gradient(circle at 50% 35%, #3a3a55, #1a1a2c); border:2px solid #e3350d55; }
  .prof-avatar {
    width:72px; height:72px; border-radius:50%;
    display:flex; align-items:center; justify-content:center;
    font-size:2rem; font-weight:900; color:#ffd94a;
    text-shadow:0 2px 8px rgba(0,0,0,.6);
  }
  .prof-who { color:#9a9ab5; font-size:.8rem; font-style:italic; margin:2px 0 8px; }
  .flavor { font-size:.78rem; color:#b8b8d0; line-height:1.45; margin-bottom:12px; min-height:44px; }

  footer {
    text-align:center; margin-top:56px; color:#55556e; font-size:.78rem; line-height:1.8;
  }
  footer .hint { color:#8a8aa3; }
  footer .sparkle { color:#ffd94a; }
</style>
</head>
<body>
<div class="container">

  <h1><span class="pokeball">⚡</span> Choose your stack <span class="pokeball">⚡</span></h1>
  <p class="subtitle">Hover a card to reveal the <b>shiny</b> — every skill is a Pokémon, and it evolves as I level up.</p>

  <div class="grid">
    
    <div class="card" style="--c:#ff6b35; --glow:rgba(255,107,53,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/6.gif" alt="Java">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/6.gif" alt="Java shiny">
      </div>
      <div class="dots"><span style="background:#ff6b35"></span><span style="background:#ff6b35"></span><span style="background:#ff6b35"></span></div>
      <div class="skill-name">Java</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/4.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/5.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/6.gif" class="chain-img current"></div>
      <div class="level-row">
        <span class="badge" style="background:#ff6b3522; color:#ff6b35; border:1px solid #ff6b3555;">ADVANCED · FINAL FORM</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:100%; background:#ff6b35;"></div></div>
    </div>

    <div class="card" style="--c:#ff6b35; --glow:rgba(255,107,53,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/5.gif" alt="Spring Boot">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/5.gif" alt="Spring Boot shiny">
      </div>
      <div class="dots"><span style="background:#ff6b35"></span><span style="background:#ff6b35"></span><span style="background:#ff6b35"></span></div>
      <div class="skill-name">Spring Boot</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/4.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/5.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/6.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#ff6b3522; color:#ff6b35; border:1px solid #ff6b3555;">INTERMEDIATE</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:66%; background:#ff6b35;"></div></div>
    </div>

    <div class="card" style="--c:#ff6b35; --glow:rgba(255,107,53,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/4.gif" alt="Spring AI">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/4.gif" alt="Spring AI shiny">
      </div>
      <div class="dots"><span style="background:#ff6b35"></span><span style="background:#ff6b35"></span><span style="background:#ff6b35"></span></div>
      <div class="skill-name">Spring AI</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/4.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/5.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/6.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#ff6b3522; color:#ff6b35; border:1px solid #ff6b3555;">BASIC</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:33%; background:#ff6b35;"></div></div>
    </div>

    <div class="card" style="--c:#8a6df0; --glow:rgba(138,109,240,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/149.gif" alt="JavaScript">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/149.gif" alt="JavaScript shiny">
      </div>
      <div class="dots"><span style="background:#8a6df0"></span><span style="background:#8a6df0"></span><span style="background:#8a6df0"></span></div>
      <div class="skill-name">JavaScript</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/147.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/148.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/149.gif" class="chain-img current"></div>
      <div class="level-row">
        <span class="badge" style="background:#8a6df022; color:#8a6df0; border:1px solid #8a6df055;">ADVANCED · FINAL FORM</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:100%; background:#8a6df0;"></div></div>
    </div>

    <div class="card" style="--c:#8a6df0; --glow:rgba(138,109,240,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/148.gif" alt="Node.js">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/148.gif" alt="Node.js shiny">
      </div>
      <div class="dots"><span style="background:#8a6df0"></span><span style="background:#8a6df0"></span><span style="background:#8a6df0"></span></div>
      <div class="skill-name">Node.js</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/147.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/148.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/149.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#8a6df022; color:#8a6df0; border:1px solid #8a6df055;">INTERMEDIATE</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:66%; background:#8a6df0;"></div></div>
    </div>

    <div class="card" style="--c:#b366d9; --glow:rgba(179,102,217,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/24.gif" alt="Python · FastAPI">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/24.gif" alt="Python · FastAPI shiny">
      </div>
      <div class="dots"><span style="background:#b366d9"></span><span style="background:#b366d9"></span><span style="background:#b366d9"></span></div>
      <div class="skill-name">Python · FastAPI</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/23.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/24.gif" class="chain-img current"></div>
      <div class="level-row">
        <span class="badge" style="background:#b366d922; color:#b366d9; border:1px solid #b366d955;">INTERMEDIATE · FINAL FORM</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:66%; background:#b366d9;"></div></div>
    </div>

    <div class="card" style="--c:#d9435f; --glow:rgba(217,67,95,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/67.gif" alt="C">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/67.gif" alt="C shiny">
      </div>
      <div class="dots"><span style="background:#d9435f"></span><span style="background:#d9435f"></span><span style="background:#d9435f"></span></div>
      <div class="skill-name">C</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/66.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/67.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/68.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#d9435f22; color:#d9435f; border:1px solid #d9435f55;">INTERMEDIATE</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:66%; background:#d9435f;"></div></div>
    </div>

    <div class="card" style="--c:#4aa8ff; --glow:rgba(74,168,255,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/8.gif" alt="React">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/8.gif" alt="React shiny">
      </div>
      <div class="dots"><span style="background:#4aa8ff"></span><span style="background:#4aa8ff"></span><span style="background:#4aa8ff"></span></div>
      <div class="skill-name">React</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/7.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/8.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/9.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#4aa8ff22; color:#4aa8ff; border:1px solid #4aa8ff55;">INTERMEDIATE</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:66%; background:#4aa8ff;"></div></div>
    </div>

    <div class="card" style="--c:#6ee27a; --glow:rgba(110,226,122,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/3.gif" alt="HTML">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/3.gif" alt="HTML shiny">
      </div>
      <div class="dots"><span style="background:#6ee27a"></span><span style="background:#6ee27a"></span><span style="background:#6ee27a"></span></div>
      <div class="skill-name">HTML</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/1.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/2.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/3.gif" class="chain-img current"></div>
      <div class="level-row">
        <span class="badge" style="background:#6ee27a22; color:#6ee27a; border:1px solid #6ee27a55;">ADVANCED · FINAL FORM</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:100%; background:#6ee27a;"></div></div>
    </div>

    <div class="card" style="--c:#6ee27a; --glow:rgba(110,226,122,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/2.gif" alt="CSS">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/2.gif" alt="CSS shiny">
      </div>
      <div class="dots"><span style="background:#6ee27a"></span><span style="background:#6ee27a"></span><span style="background:#6ee27a"></span></div>
      <div class="skill-name">CSS</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/1.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/2.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/3.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#6ee27a22; color:#6ee27a; border:1px solid #6ee27a55;">INTERMEDIATE</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:66%; background:#6ee27a;"></div></div>
    </div>

    <div class="card" style="--c:#4aa8ff; --glow:rgba(74,168,255,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/7.gif" alt="Docker">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/7.gif" alt="Docker shiny">
      </div>
      <div class="dots"><span style="background:#4aa8ff"></span><span style="background:#4aa8ff"></span><span style="background:#4aa8ff"></span></div>
      <div class="skill-name">Docker</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/7.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/8.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/9.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#4aa8ff22; color:#4aa8ff; border:1px solid #4aa8ff55;">BASIC</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:33%; background:#4aa8ff;"></div></div>
    </div>

    <div class="card" style="--c:#a8b820; --glow:rgba(168,184,32,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/11.gif" alt="Kubernetes">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/11.gif" alt="Kubernetes shiny">
      </div>
      <div class="dots"><span style="background:#a8b820"></span><span style="background:#a8b820"></span><span style="background:#a8b820"></span></div>
      <div class="skill-name">Kubernetes</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/10.gif" class="chain-img "><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/11.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/12.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#a8b82022; color:#a8b820; border:1px solid #a8b82055;">BASIC</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:33%; background:#a8b820;"></div></div>
    </div>

    <div class="card" style="--c:#ffd94a; --glow:rgba(255,217,74,.45);">
      <div class="sprite-wrap">
        <img class="sprite normal" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/100.gif" alt="Redis">
        <img class="sprite shiny" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/shiny/100.gif" alt="Redis shiny">
      </div>
      <div class="dots"><span style="background:#ffd94a"></span><span style="background:#ffd94a"></span><span style="background:#ffd94a"></span></div>
      <div class="skill-name">Redis</div>
      <div class="chain"><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/100.gif" class="chain-img current"><span class="arrow">→</span><img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/101.gif" class="chain-img "></div>
      <div class="level-row">
        <span class="badge" style="background:#ffd94a22; color:#ffd94a; border:1px solid #ffd94a55;">BASIC</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:33%; background:#ffd94a;"></div></div>
    </div>
  </div>

  <h2 class="section-title">🧪 The Professors of Data</h2>
  <p class="subtitle">Every trainer needs a professor. These are mine for the database world.</p>
  <div class="grid">
    
    <div class="card prof" style="--c:#e3350d; --glow:rgba(227,53,13,.35);">
      <div class="sprite-wrap prof-wrap">
        <div class="prof-avatar">O</div>
      </div>
      <div class="skill-name">MySQL</div>
      <div class="prof-who">Professor Oak</div>
      <div class="flavor">The original. Catches and stores them all — reliably, since 1995.</div>
      <div class="level-row">
        <span class="badge" style="background:#e3350d22; color:#ff6b57; border:1px solid #e3350d55;">ADVANCED</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:100%; background:#e3350d;"></div></div>
    </div>

    <div class="card prof" style="--c:#e3350d; --glow:rgba(227,53,13,.35);">
      <div class="sprite-wrap prof-wrap">
        <div class="prof-avatar">E</div>
      </div>
      <div class="skill-name">PostgreSQL</div>
      <div class="prof-who">Professor Elm</div>
      <div class="flavor">The researcher. Strict schemas, serious indexes, and JSONB when you're feeling wild.</div>
      <div class="level-row">
        <span class="badge" style="background:#e3350d22; color:#ff6b57; border:1px solid #e3350d55;">INTERMEDIATE</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:66%; background:#e3350d;"></div></div>
    </div>

    <div class="card prof" style="--c:#e3350d; --glow:rgba(227,53,13,.35);">
      <div class="sprite-wrap prof-wrap">
        <div class="prof-avatar">K</div>
      </div>
      <div class="skill-name">MongoDB</div>
      <div class="prof-who">Delia Ketchum</div>
      <div class="flavor">Ash's mom. Keeps everything at home — no schema required, just like her kitchen.</div>
      <div class="level-row">
        <span class="badge" style="background:#e3350d22; color:#ff6b57; border:1px solid #e3350d55;">BASIC</span>
      </div>
      <div class="xp"><div class="xp-fill" style="width:33%; background:#e3350d;"></div></div>
    </div>
  </div>

  <footer>
    <span class="sparkle">✨</span> <span class="hint">Easter egg: hover any skill card — the Pokémon turns shiny, just like the dev.to article.</span><br>
    Sprites: PokeAPI/sprites (MIT, hotlinkable) · Evolution logic: Basic → Intermediate → Advanced
  </footer>

</div>
</body>
</html>

