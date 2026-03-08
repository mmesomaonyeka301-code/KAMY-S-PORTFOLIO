<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>@Kamythedesigner — README</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500;600&family=Pacifico&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --pink:#ff4d9e;--rose:#ff85c2;--blush:#ffd6eb;
  --purple:#c77dff;--lilac:#e9d5ff;
  --dark:#1a0a12;--mid:#2d1020;--card:rgba(255,255,255,0.06);
  --border:rgba(255,182,219,0.2);
}
html{scroll-behavior:smooth}
body{
  font-family:'DM Sans',sans-serif;
  background:var(--dark);color:#fff;
  overflow-x:hidden;min-height:100vh;
}

/* ── GRAIN OVERLAY ── */
body::before{
  content:'';position:fixed;inset:0;z-index:0;pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  opacity:0.35;
}

/* ── BLOBS ── */
.blob{position:fixed;border-radius:50%;filter:blur(100px);pointer-events:none;z-index:0}
.b1{width:600px;height:600px;background:#ff4d9e;top:-200px;left:-200px;opacity:0.08}
.b2{width:400px;height:400px;background:#c77dff;bottom:-100px;right:-100px;opacity:0.1}
.b3{width:300px;height:300px;background:#ff85c2;top:40%;left:40%;opacity:0.06}

/* ── MAIN WRAP ── */
.wrap{
  position:relative;z-index:1;
  max-width:860px;margin:0 auto;
  padding:60px 32px 100px;
}

/* ── HEADER ── */
header{text-align:center;margin-bottom:56px}

.header-eyebrow{
  display:inline-flex;align-items:center;gap:10px;
  background:rgba(255,77,158,0.12);
  border:1px solid rgba(255,77,158,0.3);
  border-radius:100px;padding:8px 22px;
  font-size:12px;font-weight:600;color:#ffb3d9;
  letter-spacing:1px;margin-bottom:28px;
  animation:fadeDown 0.8s ease both;
}
.dot{
  width:7px;height:7px;border-radius:50%;
  background:var(--pink);
  animation:pulse 1.8s ease-in-out infinite;
}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.4;transform:scale(0.7)}}

h1{
  font-family:'Playfair Display',serif;
  font-size:clamp(42px,7vw,72px);font-weight:900;
  line-height:1.05;margin-bottom:12px;
  animation:fadeDown 0.9s ease 0.1s both;
}
.h1-plain{color:#fff}
.h1-pink{
  background:linear-gradient(135deg,#ff4d9e,#ff85c2,#c77dff);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  font-style:italic;
}

.tagline{
  font-size:16px;color:rgba(255,255,255,0.55);
  font-weight:300;letter-spacing:0.3px;
  max-width:460px;margin:0 auto 32px;
  animation:fadeDown 1s ease 0.2s both;
}

/* ── BADGES ROW ── */
.badges{
  display:flex;flex-wrap:wrap;justify-content:center;
  gap:10px;margin-bottom:40px;
  animation:fadeDown 1s ease 0.3s both;
}
.badge{
  display:inline-flex;align-items:center;gap:6px;
  padding:6px 16px;border-radius:100px;
  font-size:12px;font-weight:600;
  border:1.5px solid;
  transition:transform 0.2s,box-shadow 0.2s;
}
.badge:hover{transform:translateY(-2px);box-shadow:0 6px 20px rgba(255,77,158,0.25)}

/* ── VIDEO SECTION ── */
.video-section{
  margin-bottom:52px;
  animation:fadeUp 1s ease 0.4s both;
}
.video-label{
  font-size:11px;font-weight:700;letter-spacing:3px;
  text-transform:uppercase;color:var(--pink);
  display:flex;align-items:center;gap:10px;
  margin-bottom:18px;
}
.video-label::before,.video-label::after{
  content:'';flex:1;height:1px;
  background:linear-gradient(90deg,transparent,rgba(255,77,158,0.4),transparent);
}

.video-frame{
  position:relative;border-radius:24px;overflow:hidden;
  border:1.5px solid var(--border);
  box-shadow:0 24px 80px rgba(255,77,158,0.18),0 0 0 1px rgba(255,255,255,0.04);
  background:#0d0509;
  aspect-ratio:16/9;
}
/* Pink vignette overlay */
.video-frame::after{
  content:'';position:absolute;inset:0;pointer-events:none;
  background:radial-gradient(ellipse at center,transparent 50%,rgba(255,77,158,0.12) 100%);
  z-index:2;
}

/* The CSS animated "girl typing" scene */
.scene{
  width:100%;height:100%;
  display:flex;align-items:center;justify-content:center;
  position:relative;overflow:hidden;
  background:linear-gradient(160deg,#1a0a12 0%,#2d1020 40%,#1a0a12 100%);
}

/* Ambient glow */
.glow{
  position:absolute;width:400px;height:300px;
  background:radial-gradient(ellipse,rgba(199,125,255,0.25) 0%,transparent 70%);
  top:10%;left:50%;transform:translateX(-50%);
  animation:glowPulse 4s ease-in-out infinite;
}
@keyframes glowPulse{0%,100%{opacity:0.6;transform:translateX(-50%) scale(1)}50%{opacity:1;transform:translateX(-50%) scale(1.08)}}

/* Floating particles */
.particles{position:absolute;inset:0;pointer-events:none}
.p{position:absolute;border-radius:50%;animation:float linear infinite}
@keyframes float{0%{transform:translateY(110%) scale(0);opacity:0}10%{opacity:1}90%{opacity:0.6}100%{transform:translateY(-20px) scale(1.2);opacity:0}}

/* Desk */
.desk{
  position:absolute;bottom:0;left:0;right:0;height:38%;
  background:linear-gradient(180deg,#3d1a2e 0%,#2a1020 100%);
  border-top:2px solid rgba(255,130,190,0.2);
}
.desk-shine{
  position:absolute;top:0;left:10%;right:10%;height:1px;
  background:linear-gradient(90deg,transparent,rgba(255,182,219,0.5),transparent);
}

/* Laptop */
.laptop{
  position:absolute;bottom:36%;left:50%;transform:translateX(-50%);
  width:280px;
}
.laptop-screen{
  width:100%;height:0;padding-bottom:63%;
  background:#0a0510;border-radius:10px 10px 0 0;
  border:2.5px solid #4a2040;
  position:relative;overflow:hidden;
  box-shadow:0 0 30px rgba(199,125,255,0.3),0 0 60px rgba(199,125,255,0.1);
}
/* Screen glow */
.laptop-screen::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(199,125,255,0.08),rgba(255,77,158,0.08));
}
/* Fake code/text on screen */
.screen-content{
  position:absolute;inset:0;padding:14px 16px;
  font-family:monospace;font-size:8.5px;line-height:1.7;
  color:rgba(255,255,255,0.6);overflow:hidden;
}
.code-line{display:block;white-space:nowrap;overflow:hidden}
.c1{color:#ff85c2}.c2{color:#c77dff}.c3{color:#4cc9f0}.c4{color:#ffd166}
.blink{display:inline-block;width:5px;height:10px;background:#ff4d9e;animation:blink 1.1s step-end infinite;vertical-align:middle}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.laptop-base{
  width:105%;margin-left:-2.5%;height:12px;
  background:linear-gradient(180deg,#4a2040,#2d1020);
  border-radius:0 0 8px 8px;
  border:2.5px solid #4a2040;border-top:none;
  display:flex;align-items:center;justify-content:center;
}
.trackpad{width:50px;height:6px;background:#3a1830;border-radius:3px;border:1px solid #5a2a50}

/* Girl silhouette */
.girl{
  position:absolute;
  bottom:36%;left:50%;
  transform:translateX(70px);
  width:100px;height:140px;
  pointer-events:none;
}
/* Body */
.g-body{
  position:absolute;bottom:0;left:50%;transform:translateX(-50%);
  width:52px;height:70px;
  background:linear-gradient(180deg,#3a1830,#2a1220);
  border-radius:30px 30px 10px 10px;
}
/* Head */
.g-head{
  position:absolute;top:0;left:50%;transform:translateX(-50%);
  width:36px;height:38px;
  background:#8B5E3C;
  border-radius:50% 50% 45% 45%;
}
/* Hair */
.g-hair{
  position:absolute;top:-4px;left:50%;transform:translateX(-52%);
  width:40px;height:28px;
  background:#1a0a08;
  border-radius:50% 50% 0 0;
  overflow:hidden;
}
.g-hair::after{
  content:'';position:absolute;right:-8px;top:2px;
  width:16px;height:34px;background:#1a0a08;
  border-radius:0 0 10px 10px;
}
/* Braid / ponytail */
.g-ponytail{
  position:absolute;top:10px;right:-6px;
  width:10px;height:50px;background:#1a0a08;
  border-radius:5px;transform:rotate(-5deg);
  transform-origin:top center;
  animation:sway 3s ease-in-out infinite;
}
@keyframes sway{0%,100%{transform:rotate(-5deg)}50%{transform:rotate(5deg)}}

/* Arms */
.g-arm-l,.g-arm-r{
  position:absolute;
  width:14px;height:50px;
  background:linear-gradient(180deg,#3a1830,#2a1220);
  border-radius:8px;
  transform-origin:top center;
}
.g-arm-l{top:28px;left:-2px;transform:rotate(30deg)}
.g-arm-r{top:28px;right:-2px;transform:rotate(-30deg)}

/* Typing hands animation */
.g-hand-l,.g-hand-r{
  position:absolute;bottom:0;
  width:12px;height:12px;
  background:#8B5E3C;border-radius:50%;
}
.g-hand-l{left:-1px;animation:typeleft 0.3s ease-in-out infinite alternate}
.g-hand-r{right:-1px;animation:typeright 0.3s ease-in-out infinite alternate}
@keyframes typeleft{0%{transform:translateY(0)}100%{transform:translateY(-4px)}}
@keyframes typeright{0%{transform:translateY(-4px)}100%{transform:translateY(0)}}

/* Floating hearts & stars */
.floatie{
  position:absolute;font-size:14px;
  animation:floatUp 4s ease-in-out infinite;
  opacity:0;
}
@keyframes floatUp{
  0%{opacity:0;transform:translateY(0) scale(0.5)}
  20%{opacity:1}
  80%{opacity:0.8}
  100%{opacity:0;transform:translateY(-80px) scale(1)}
}

/* Screen reflection on face */
.g-glow{
  position:absolute;top:0;left:50%;transform:translateX(-50%);
  width:36px;height:38px;border-radius:50% 50% 45% 45%;
  background:radial-gradient(ellipse at 30% 40%,rgba(199,125,255,0.3),transparent 70%);
  animation:screenGlow 3s ease-in-out infinite;
}
@keyframes screenGlow{0%,100%{opacity:0.6}50%{opacity:1}}

/* Coffee cup */
.coffee{
  position:absolute;bottom:37%;right:calc(50% - 180px);
  width:28px;
  animation:steam 2s ease-in-out infinite;
}
.cup-body{width:28px;height:26px;background:linear-gradient(135deg,#5a2040,#3a1025);border-radius:4px 4px 8px 8px;border:1.5px solid rgba(255,130,190,0.3)}
.cup-handle{position:absolute;right:-8px;top:6px;width:10px;height:12px;border:2px solid rgba(255,130,190,0.3);border-radius:0 6px 6px 0;border-left:none}
.steam-line{position:absolute;top:-10px;left:8px;width:3px;height:10px;background:rgba(255,182,219,0.5);border-radius:2px;animation:steamUp 1.5s ease-in-out infinite}
.steam-line:nth-child(2){left:14px;animation-delay:0.5s}
@keyframes steam{0%,100%{transform:translateY(0)}50%{transform:translateY(-2px)}}
@keyframes steamUp{0%,100%{opacity:0;transform:translateY(0)}50%{opacity:1;transform:translateY(-8px)}}

/* Window / fairy lights */
.lights{position:absolute;top:8%;left:50%;transform:translateX(-50%);display:flex;gap:16px}
.light{width:6px;height:6px;border-radius:50%;animation:twinkle 2s ease-in-out infinite}
@keyframes twinkle{0%,100%{opacity:1;box-shadow:0 0 6px currentColor}50%{opacity:0.3;box-shadow:none}}

/* ── TYPING TEXT ── */
.typing-wrap{
  text-align:center;margin-bottom:52px;
  animation:fadeUp 1s ease 0.5s both;
}
.typing-container{
  display:inline-block;
  font-family:'Playfair Display',serif;
  font-size:clamp(18px,3vw,26px);
  font-style:italic;color:#ffb3d9;
  min-height:1.4em;
}
.typing-cursor{
  display:inline-block;width:2px;height:1.2em;
  background:var(--pink);vertical-align:middle;margin-left:3px;
  animation:blink 1s step-end infinite;
}

/* ── STATS ── */
.stats{
  display:grid;grid-template-columns:repeat(3,1fr);
  gap:16px;margin-bottom:52px;
  animation:fadeUp 1s ease 0.55s both;
}
.stat{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:20px;padding:24px 16px;
  text-align:center;
  transition:transform 0.25s,box-shadow 0.25s;
}
.stat:hover{transform:translateY(-4px);box-shadow:0 12px 40px rgba(255,77,158,0.18)}
.stat-num{
  font-family:'Playfair Display',serif;
  font-size:36px;font-weight:900;
  background:linear-gradient(135deg,var(--pink),var(--purple));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
}
.stat-label{font-size:12px;color:rgba(255,255,255,0.45);margin-top:4px}

/* ── SECTIONS ── */
.sec{
  margin-bottom:44px;
  background:var(--card);
  border:1px solid var(--border);
  border-radius:24px;padding:32px;
  animation:fadeUp 1s ease 0.6s both;
  transition:border-color 0.3s;
}
.sec:hover{border-color:rgba(255,77,158,0.35)}

.sec-title{
  font-family:'Playfair Display',serif;
  font-size:22px;font-weight:700;
  margin-bottom:20px;
  display:flex;align-items:center;gap:10px;
}
.sec-title .icon{font-size:20px}

/* Tech stack pills */
.tech-grid{display:flex;flex-wrap:wrap;gap:10px}
.tech{
  padding:8px 18px;border-radius:100px;
  font-size:13px;font-weight:600;
  border:1.5px solid rgba(255,77,158,0.3);
  background:rgba(255,77,158,0.08);color:#ffb3d9;
  transition:all 0.2s;cursor:default;
}
.tech:hover{background:rgba(255,77,158,0.18);border-color:var(--pink);transform:translateY(-2px)}

/* Projects mini */
.proj-list{display:grid;gap:14px}
.proj{
  display:flex;align-items:center;gap:16px;
  padding:16px;border-radius:16px;
  background:rgba(255,255,255,0.03);
  border:1px solid rgba(255,255,255,0.06);
  text-decoration:none;color:#fff;
  transition:all 0.25s;
}
.proj:hover{background:rgba(255,77,158,0.08);border-color:rgba(255,77,158,0.3);transform:translateX(4px)}
.proj-emoji{font-size:28px;flex-shrink:0}
.proj-title{font-weight:700;font-size:15px;margin-bottom:3px}
.proj-desc{font-size:12px;color:rgba(255,255,255,0.45)}
.proj-arrow{margin-left:auto;color:var(--pink);font-size:18px;opacity:0;transition:opacity 0.2s}
.proj:hover .proj-arrow{opacity:1}

/* Currently */
.currently{display:flex;flex-direction:column;gap:12px}
.curr-item{
  display:flex;align-items:center;gap:14px;
  font-size:14px;color:rgba(255,255,255,0.7);
}
.curr-dot{
  width:8px;height:8px;border-radius:50%;
  background:var(--pink);flex-shrink:0;
  box-shadow:0 0 8px var(--pink);
  animation:pulse 2s ease-in-out infinite;
}

/* GitHub graph fake */
.graph-wrap{margin-top:8px}
.graph-row{display:flex;gap:4px;margin-bottom:4px;justify-content:center;flex-wrap:wrap}
.g-cell{
  width:13px;height:13px;border-radius:3px;
  background:rgba(255,255,255,0.06);
  transition:background 0.3s,transform 0.2s;
}
.g-cell:hover{transform:scale(1.3)}

/* Social links */
.socials{display:flex;flex-wrap:wrap;gap:12px;justify-content:center}
.social{
  display:flex;align-items:center;gap:8px;
  padding:10px 22px;border-radius:100px;
  font-size:13px;font-weight:600;
  border:1.5px solid var(--border);
  background:var(--card);color:#fff;
  text-decoration:none;transition:all 0.25s;
}
.social:hover{border-color:var(--pink);background:rgba(255,77,158,0.1);transform:translateY(-2px)}

/* Footer quote */
.footer-quote{
  text-align:center;margin-top:56px;
  font-family:'Pacifico',cursive;
  font-size:clamp(18px,3vw,28px);
  color:rgba(255,77,158,0.7);
  animation:fadeUp 1s ease 0.8s both;
}
.footer-quote span{color:var(--pink)}

/* ANIMATIONS */
@keyframes fadeDown{from{opacity:0;transform:translateY(-20px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}

/* Responsive */
@media(max-width:600px){
  .stats{grid-template-columns:1fr 1fr}
  .wrap{padding:40px 16px 80px}
  h1{font-size:38px}
}
</style>
</head>
<body>

<!-- BG -->
<div class="blob b1"></div>
<div class="blob b2"></div>
<div class="blob b3"></div>

<div class="wrap">

  <!-- HEADER -->
  <header>
    <div class="header-eyebrow"><div class="dot"></div> she/her · Nigeria 🇳🇬 · available for projects</div>

    <h1>
      <span class="h1-plain">Hi, I'm </span><br/>
      <span class="h1-pink">Kamy ✦</span>
    </h1>

    <p class="tagline">Designer · Animator · Web Developer · Storyteller · Dream chaser 🌸</p>

    <div class="badges">
      <span class="badge" style="color:#ff4d9e;border-color:#ff4d9e;background:rgba(255,77,158,0.1)">🎨 UI/UX Design</span>
      <span class="badge" style="color:#c77dff;border-color:#c77dff;background:rgba(199,125,255,0.1)">✨ Animation</span>
      <span class="badge" style="color:#4cc9f0;border-color:#4cc9f0;background:rgba(76,201,240,0.1)">💻 Web Dev</span>
      <span class="badge" style="color:#ffd166;border-color:#ffd166;background:rgba(255,209,102,0.1)">📖 Storytelling</span>
      <span class="badge" style="color:#06d6a0;border-color:#06d6a0;background:rgba(6,214,160,0.1)">🌸 Content Creator</span>
    </div>
  </header>

  <!-- VIDEO SCENE -->
  <div class="video-section">
    <div class="video-label">✦ currently in my creative era ✦</div>
    <div class="video-frame">
      <div class="scene">

        <!-- Glow -->
        <div class="glow"></div>

        <!-- Fairy lights -->
        <div class="lights">
          <div class="light" style="background:#ff4d9e;color:#ff4d9e;animation-delay:0s"></div>
          <div class="light" style="background:#ffd166;color:#ffd166;animation-delay:0.3s"></div>
          <div class="light" style="background:#c77dff;color:#c77dff;animation-delay:0.6s"></div>
          <div class="light" style="background:#4cc9f0;color:#4cc9f0;animation-delay:0.9s"></div>
          <div class="light" style="background:#ff4d9e;color:#ff4d9e;animation-delay:1.2s"></div>
          <div class="light" style="background:#06d6a0;color:#06d6a0;animation-delay:1.5s"></div>
          <div class="light" style="background:#ff85c2;color:#ff85c2;animation-delay:1.8s"></div>
          <div class="light" style="background:#ffd166;color:#ffd166;animation-delay:2.1s"></div>
        </div>

        <!-- Floating particles -->
        <div class="particles">
          <div class="p" style="left:10%;width:4px;height:4px;background:#ff4d9e;animation-duration:6s;animation-delay:0s"></div>
          <div class="p" style="left:25%;width:3px;height:3px;background:#c77dff;animation-duration:8s;animation-delay:1s"></div>
          <div class="p" style="left:40%;width:5px;height:5px;background:#ff85c2;animation-duration:7s;animation-delay:2s"></div>
          <div class="p" style="left:60%;width:3px;height:3px;background:#ffd166;animation-duration:9s;animation-delay:0.5s"></div>
          <div class="p" style="left:75%;width:4px;height:4px;background:#4cc9f0;animation-duration:6.5s;animation-delay:1.5s"></div>
          <div class="p" style="left:88%;width:3px;height:3px;background:#ff4d9e;animation-duration:7.5s;animation-delay:3s"></div>
        </div>

        <!-- Desk -->
        <div class="desk"><div class="desk-shine"></div></div>

        <!-- Coffee cup -->
        <div class="coffee">
          <div class="steam-line"></div>
          <div class="steam-line"></div>
          <div class="cup-body"></div>
          <div class="cup-handle"></div>
        </div>

        <!-- Laptop -->
        <div class="laptop">
          <div class="laptop-screen">
            <div class="screen-content">
              <span class="code-line"><span class="c2">const</span> <span class="c3">kamy</span> = {</span>
              <span class="code-line">  <span class="c1">name</span>: <span class="c4">"Mmesoma Onyeka"</span>,</span>
              <span class="code-line">  <span class="c1">role</span>: <span class="c4">"Designer ✨"</span>,</span>
              <span class="code-line">  <span class="c1">passion</span>: [</span>
              <span class="code-line">    <span class="c4">"animation"</span>,</span>
              <span class="code-line">    <span class="c4">"storytelling"</span>,</span>
              <span class="code-line">  ],</span>
              <span class="code-line">  <span class="c1">vibe</span>: <span class="c4">"pink 🌸"</span></span>
              <span class="code-line">};<span class="blink"></span></span>
            </div>
          </div>
          <div class="laptop-base"><div class="trackpad"></div></div>
        </div>

        <!-- Girl -->
        <div class="girl">
          <div class="g-body">
            <div class="g-arm-l"><div class="g-hand-l"></div></div>
            <div class="g-arm-r"><div class="g-hand-r"></div></div>
          </div>
          <div class="g-head">
            <div class="g-hair"><div class="g-ponytail"></div></div>
            <div class="g-glow"></div>
          </div>
        </div>

        <!-- Floating hearts -->
        <div class="floatie" style="left:62%;bottom:60%;animation-delay:0s">💗</div>
        <div class="floatie" style="left:68%;bottom:55%;animation-delay:1.5s">✨</div>
        <div class="floatie" style="left:56%;bottom:65%;animation-delay:2.8s">🌸</div>
        <div class="floatie" style="left:72%;bottom:62%;animation-delay:4s">💜</div>
        <div class="floatie" style="left:50%;bottom:58%;animation-delay:1s">⭐</div>

      </div>
    </div>
  </div>

  <!-- TYPING QUOTE -->
  <div class="typing-wrap">
    <div class="typing-container" id="typer"></div><span class="typing-cursor"></span>
  </div>

  <!-- STATS -->
  <div class="stats">
    <div class="stat">
      <div class="stat-num">4+</div>
      <div class="stat-label">Projects Completed</div>
    </div>
    <div class="stat">
      <div class="stat-num">3</div>
      <div class="stat-label">YouTube Stories</div>
    </div>
    <div class="stat">
      <div class="stat-num">∞</div>
      <div class="stat-label">Creative Ideas 🌸</div>
    </div>
  </div>

  <!-- ABOUT ME -->
  <div class="sec">
    <div class="sec-title"><span class="icon">🌸</span> About Me</div>
    <p style="font-size:15px;line-height:1.9;color:rgba(255,255,255,0.65);margin-bottom:16px">
      I'm <strong style="color:#ffb3d9">Mmesoma Onyeka</strong> — a passionate designer, animator, and web developer from Nigeria 🇳🇬.
      I love turning ideas into beautiful, meaningful visuals and digital experiences.
    </p>
    <p style="font-size:15px;line-height:1.9;color:rgba(255,255,255,0.65)">
      Whether it's crafting a fairy-tale animation, designing a pixel-perfect UI, or writing code that brings something to life —
      I pour my whole heart into every project. Always learning, always growing, always creating. 💕
    </p>
  </div>

  <!-- CURRENTLY -->
  <div class="sec" style="animation-delay:0.65s">
    <div class="sec-title"><span class="icon">✨</span> Currently</div>
    <div class="currently">
      <div class="curr-item"><div class="curr-dot"></div>🎓 Studying & leveling up my skills</div>
      <div class="curr-item"><div class="curr-dot"></div>🎬 Creating animated stories on <a href="https://youtube.com/@kachi_tales?si=p3XJhmU37cUWHF_k" style="color:var(--pink);font-weight:700">@kachi_tales</a></div>
      <div class="curr-item"><div class="curr-dot"></div>💻 Building cool web projects</div>
      <div class="curr-item"><div class="curr-dot"></div>🌸 Open for freelance & creative collabs</div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="sec" style="animation-delay:0.7s">
    <div class="sec-title"><span class="icon">🛠️</span> Tools & Tech</div>
    <div class="tech-grid">
      <span class="tech">🎨 Figma</span>
      <span class="tech">✨ After Effects</span>
      <span class="tech">🖌️ Canva</span>
      <span class="tech">💻 HTML/CSS</span>
      <span class="tech">⚡ JavaScript</span>
      <span class="tech">🗄️ T-SQL</span>
      <span class="tech">📱 Responsive Design</span>
      <span class="tech">🎬 Animation</span>
      <span class="tech">📖 Storytelling</span>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="sec" style="animation-delay:0.75s">
    <div class="sec-title"><span class="icon">💼</span> Featured Projects</div>
    <div class="proj-list">
      <a href="https://youtube.com/@kachi_tales?si=p3XJhmU37cUWHF_k" target="_blank" class="proj">
        <div class="proj-emoji">🌟</div>
        <div>
          <div class="proj-title">Lumi & The Clockticker</div>
          <div class="proj-desc">Fairy-tale animated story · Narration + background music</div>
        </div>
        <div class="proj-arrow">→</div>
      </a>
      <a href="https://youtube.com/@kachi_tales?si=p3XJhmU37cUWHF_k" target="_blank" class="proj">
        <div class="proj-emoji">🌿</div>
        <div>
          <div class="proj-title">Amara Story</div>
          <div class="proj-desc">Nigerian folktale animation · Heartwarming breakthrough story</div>
        </div>
        <div class="proj-arrow">→</div>
      </a>
      <a href="https://youtube.com/@kachi_tales?si=p3XJhmU37cUWHF_k" target="_blank" class="proj">
        <div class="proj-emoji">📖</div>
        <div>
          <div class="proj-title">David & Goliath Bible Story</div>
          <div class="proj-desc">Children's YouTube content · Thumbnails & engagement copy</div>
        </div>
        <div class="proj-arrow">→</div>
      </a>
      <div class="proj" style="cursor:default">
        <div class="proj-emoji">💻</div>
        <div>
          <div class="proj-title">ABStores Database</div>
          <div class="proj-desc">T-SQL · Sales tracking & store management system</div>
        </div>
      </div>
    </div>
  </div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="sec" style="animation-delay:0.8s">
    <div class="sec-title"><span class="icon">📊</span> Creative Activity</div>
    <div class="graph-wrap" id="graph"></div>
  </div>

  <!-- CONNECT -->
  <div class="sec" style="animation-delay:0.85s;text-align:center">
    <div class="sec-title" style="justify-content:center"><span class="icon">💌</span> Let's Connect</div>
    <p style="font-size:14px;color:rgba(255,255,255,0.5);margin-bottom:24px">Always happy to chat, collab, or just vibe 🌸</p>
    <div class="socials">
      <a href="mailto:mmesomaonyeka301@gmail.com" class="social">📧 Email</a>
      <a href="https://github.com/mmesomaonyeka301-code" target="_blank" class="social">🐙 GitHub</a>
      <a href="https://youtube.com/@kachi_tales?si=p3XJhmU37cUWHF_k" target="_blank" class="social">▶ YouTube</a>
    </div>
  </div>

  <!-- FOOTER QUOTE -->
  <div class="footer-quote">
    "Creating beautiful things,<br/><span>one pixel at a time 🌸"</span>
  </div>

</div>

<script>
// ── TYPING EFFECT ──
const phrases = [
  "designing with love 💗",
  "animating stories ✨",
  "building cool things 💻",
  "dreaming in pink 🌸",
  "always creating 🎨",
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('typer');

function type() {
  const phrase = phrases[pi];
  if (!deleting) {
    el.textContent = phrase.slice(0, ++ci);
    if (ci === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
  } else {
    el.textContent = phrase.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
  }
  setTimeout(type, deleting ? 55 : 90);
}
type();

// ── CONTRIBUTION GRAPH ──
const g = document.getElementById('graph');
const cols = 26, rows = 7;
const pinkLevels = [
  'rgba(255,255,255,0.06)',
  'rgba(255,77,158,0.2)',
  'rgba(255,77,158,0.4)',
  'rgba(255,77,158,0.65)',
  'rgba(255,77,158,0.9)',
];
for (let r = 0; r < rows; r++) {
  const row = document.createElement('div');
  row.className = 'graph-row';
  for (let c = 0; c < cols; c++) {
    const cell = document.createElement('div');
    cell.className = 'g-cell';
    const rand = Math.random();
    const lvl = rand < 0.45 ? 0 : rand < 0.6 ? 1 : rand < 0.75 ? 2 : rand < 0.9 ? 3 : 4;
    cell.style.background = pinkLevels[lvl];
    if (lvl > 0) cell.title = `${Math.floor(rand * 8) + 1} contributions`;
    row.appendChild(cell);
  }
  g.appendChild(row);
}

// ── NAV ACTIVE (scroll) ──
// (no nav here but keeping for future use)
</script>
</body>
</html>
