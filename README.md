<!DOCTYPE html>

<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RISE UP — Discipline. Nature. Force.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=DM+Sans:wght@300;400;500&family=Playfair+Display:ital,wght@0,700;0,900;1,400&display=swap" rel="stylesheet">

<style>
/* ═══════════════════════════════════════════════
   ROOT & RESET
═══════════════════════════════════════════════ */
:root {
  --ink:       #0d1008;
  --forest:    #1a2e1a;
  --moss:      #2d4a2d;
  --fern:      #3d6b3d;
  --sage:      #6a9b5e;
  --mint:      #a8d5a2;
  --dew:       #d4edd0;
  --cream:     #f7f2e8;
  --gold:      #c8a84b;
  --amber:     #e8c97a;
  --white:     #fdfaf4;
  --bark:      #8b6914;
  --mist:      rgba(212,237,208,0.08);
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;font-size:16px;}
body{
  background:var(--ink);
  color:var(--cream);
  font-family:'DM Sans',sans-serif;
  overflow-x:hidden;
  cursor:none;
}

/* ── CUSTOM CURSOR ── */
#cur{
  width:10px;height:10px;
  background:var(--mint);
  border-radius:50%;
  position:fixed;pointer-events:none;
  z-index:9999;
  transition:width .2s,height .2s,background .2s;
  mix-blend-mode:screen;
}
#cur2{
  width:36px;height:36px;
  border:1px solid rgba(168,213,162,.4);
  border-radius:50%;
  position:fixed;pointer-events:none;
  z-index:9998;
  transition:all .08s linear;
}
body:hover #cur{width:10px;height:10px;}
a:hover ~ #cur, button:hover ~ #cur{width:20px;height:20px;}

/* ── SCROLLBAR ── */
::-webkit-scrollbar{width:4px;}
::-webkit-scrollbar-track{background:var(--ink);}
::-webkit-scrollbar-thumb{background:var(--fern);border-radius:2px;}

/* ═══════════════════════════════════════════════
   NAV
═══════════════════════════════════════════════ */
nav{
  position:fixed;top:0;left:0;right:0;
  z-index:1000;
  display:flex;justify-content:space-between;align-items:center;
  padding:28px 80px;
  transition:all .5s cubic-bezier(.4,0,.2,1);
}
nav.stuck{
  background:rgba(13,16,8,.92);
  backdrop-filter:blur(20px);
  padding:18px 80px;
  border-bottom:1px solid rgba(168,213,162,.1);
}
.nav-logo{
  font-family:'Cormorant Garamond',serif;
  font-size:1.8rem;font-weight:700;
  letter-spacing:6px;text-transform:uppercase;
  color:var(--mint);text-decoration:none;
}
.nav-links{display:flex;gap:48px;list-style:none;align-items:center;}
.nav-links a{
  font-size:.72rem;letter-spacing:3px;text-transform:uppercase;
  color:rgba(247,242,232,.55);text-decoration:none;
  transition:color .3s;
  font-weight:500;
}
.nav-links a:hover{color:var(--mint);}
.nav-btn{
  background:linear-gradient(135deg,var(--fern),var(--sage));
  color:var(--white)!important;
  padding:11px 28px!important;
  border-radius:100px!important;
  transition:box-shadow .3s,transform .2s!important;
  opacity:1!important;
}
.nav-btn:hover{
  box-shadow:0 0 32px rgba(106,155,94,.4)!important;
  transform:translateY(-1px)!important;
}

/* ═══════════════════════════════════════════════
   HERO
═══════════════════════════════════════════════ */
#hero{
  height:100vh;min-height:700px;
  position:relative;overflow:hidden;
  display:flex;align-items:center;
}

/* SVG forest landscape */
.hero-landscape{
  position:absolute;inset:0;
  width:100%;height:100%;
}

.hero-overlay{
  position:absolute;inset:0;
  background:
    radial-gradient(ellipse 70% 60% at 30% 50%, rgba(13,16,8,.1) 0%, transparent 70%),
    linear-gradient(to right, rgba(13,16,8,.85) 0%, rgba(13,16,8,.4) 50%, rgba(13,16,8,.1) 100%),
    linear-gradient(to top, rgba(13,16,8,.7) 0%, transparent 50%);
}

.hero-content{
  position:relative;z-index:3;
  padding:0 80px;
  max-width:760px;
}

.hero-tag{
  display:inline-flex;align-items:center;gap:10px;
  font-size:.7rem;letter-spacing:5px;text-transform:uppercase;
  color:var(--mint);margin-bottom:32px;
  opacity:0;animation:riseIn .8s .4s forwards;
}
.hero-tag::before{
  content:'';width:24px;height:1px;background:var(--mint);
}

.hero-h1{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(5rem,9vw,9rem);
  font-weight:700;line-height:.88;
  letter-spacing:-2px;
  color:var(--white);
  opacity:0;animation:riseIn .9s .6s forwards;
}
.hero-h1 em{
  font-style:italic;color:var(--mint);
  display:block;
}
.hero-h1 span{
  font-weight:300;font-style:italic;
  font-size:.55em;display:block;
  color:var(--dew);letter-spacing:2px;
  margin-top:8px;
}

.hero-p{
  font-size:1.05rem;line-height:1.85;
  color:rgba(212,237,208,.7);
  margin-top:32px;max-width:460px;
  opacity:0;animation:riseIn .9s .85s forwards;
  font-weight:300;
}

.hero-actions{
  display:flex;gap:20px;margin-top:48px;align-items:center;
  opacity:0;animation:riseIn .9s 1.05s forwards;
}
.btn-forest{
  background:linear-gradient(135deg,var(--fern) 0%,var(--sage) 100%);
  color:var(--white);
  padding:17px 44px;font-size:.82rem;letter-spacing:2.5px;
  text-transform:uppercase;text-decoration:none;font-weight:500;
  border-radius:100px;display:inline-block;
  box-shadow:0 8px 40px rgba(61,107,61,.5);
  transition:transform .25s,box-shadow .25s;
}
.btn-forest:hover{
  transform:translateY(-3px);
  box-shadow:0 16px 56px rgba(61,107,61,.6);
}
.btn-ghost{
  color:var(--dew);text-decoration:none;
  font-size:.8rem;letter-spacing:2px;text-transform:uppercase;
  display:flex;align-items:center;gap:12px;
  opacity:.7;transition:opacity .25s;
}
.btn-ghost:hover{opacity:1;}
.btn-ghost::after{
  content:'';width:28px;height:1px;background:currentColor;
  transition:width .25s;
}
.btn-ghost:hover::after{width:44px;}

/* floating badge */
.hero-badge{
  position:absolute;right:80px;bottom:120px;
  width:140px;height:140px;
  border:1px solid rgba(168,213,162,.2);
  border-radius:50%;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  gap:4px;text-align:center;
  z-index:3;
  animation:rotateSlow 20s linear infinite;
  opacity:0;animation:riseIn 1s 1.4s forwards, rotateSlow 25s 2.4s linear infinite;
}
.hero-badge-text{
  font-family:'Cormorant Garamond',serif;
  font-size:.65rem;letter-spacing:4px;text-transform:uppercase;
  color:var(--mint);line-height:1.6;
}
.hero-badge-num{
  font-family:'Cormorant Garamond',serif;
  font-size:2.4rem;font-weight:700;color:var(--gold);line-height:1;
}

.hero-scroll{
  position:absolute;bottom:48px;left:80px;
  display:flex;align-items:center;gap:16px;z-index:3;
  opacity:0;animation:riseIn 1s 1.6s forwards;
}
.hero-scroll span{
  font-size:.65rem;letter-spacing:4px;text-transform:uppercase;
  color:rgba(212,237,208,.45);
}
.scroll-bar{
  width:60px;height:1px;
  background:linear-gradient(to right,var(--sage),transparent);
  animation:scrollBarPulse 2.5s ease-in-out infinite;
}

/* ═══════════════════════════════════════════════
   MARQUEE
═══════════════════════════════════════════════ */
.marquee-wrap{
  overflow:hidden;
  border-top:1px solid rgba(168,213,162,.12);
  border-bottom:1px solid rgba(168,213,162,.12);
  padding:22px 0;
  background:linear-gradient(90deg,var(--forest),var(--moss) 50%,var(--forest));
}
.marquee-inner{
  display:flex;gap:0;
  animation:marqueeScroll 28s linear infinite;
  width:max-content;
}
.m-item{
  display:flex;align-items:center;gap:0;
  flex-shrink:0;
}
.m-word{
  font-family:'Cormorant Garamond',serif;
  font-size:1.15rem;font-weight:400;
  letter-spacing:5px;text-transform:uppercase;
  color:rgba(212,237,208,.75);
  padding:0 40px;white-space:nowrap;
}
.m-sep{
  color:var(--gold);font-size:.6rem;
}

/* ═══════════════════════════════════════════════
   SECTION HELPERS
═══════════════════════════════════════════════ */
.section-label{
  display:inline-flex;align-items:center;gap:14px;
  font-size:.68rem;letter-spacing:5px;text-transform:uppercase;
  color:var(--sage);margin-bottom:28px;
}
.section-label::before{
  content:'';width:32px;height:1px;background:var(--sage);
}

.reveal{
  opacity:0;transform:translateY(48px);
  transition:opacity .8s cubic-bezier(.4,0,.2,1),transform .8s cubic-bezier(.4,0,.2,1);
}
.reveal.on{opacity:1;transform:none;}
.reveal-left{
  opacity:0;transform:translateX(-48px);
  transition:opacity .8s cubic-bezier(.4,0,.2,1),transform .8s cubic-bezier(.4,0,.2,1);
}
.reveal-left.on{opacity:1;transform:none;}
.reveal-right{
  opacity:0;transform:translateX(48px);
  transition:opacity .8s cubic-bezier(.4,0,.2,1),transform .8s cubic-bezier(.4,0,.2,1);
}
.reveal-right.on{opacity:1;transform:none;}

/* ═══════════════════════════════════════════════
   ABOUT / MISSION
═══════════════════════════════════════════════ */
#mission{
  padding:160px 80px;
  position:relative;overflow:hidden;
}
#mission::before{
  content:'';
  position:absolute;top:-200px;right:-300px;
  width:700px;height:700px;
  background:radial-gradient(circle,rgba(45,74,45,.35) 0%,transparent 70%);
  pointer-events:none;
}

.mission-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:120px;align-items:center;
  max-width:1400px;margin:0 auto;
}

.mission-left h2{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(3.2rem,5.5vw,5.5rem);
  font-weight:700;line-height:.92;
  letter-spacing:-1px;
  color:var(--white);
  margin-bottom:48px;
}
.mission-left h2 em{
  font-style:italic;color:var(--mint);
  display:block;
}

.mission-stats{
  display:grid;grid-template-columns:1fr 1fr;gap:32px;
  margin-top:56px;
}
.m-stat{
  padding:28px;
  border:1px solid rgba(168,213,162,.1);
  border-radius:12px;
  background:rgba(168,213,162,.03);
  transition:border-color .3s,background .3s;
}
.m-stat:hover{
  border-color:rgba(168,213,162,.25);
  background:rgba(168,213,162,.06);
}
.m-stat-n{
  font-family:'Cormorant Garamond',serif;
  font-size:3.2rem;font-weight:700;
  color:var(--gold);line-height:1;
}
.m-stat-l{
  font-size:.72rem;letter-spacing:2px;text-transform:uppercase;
  color:var(--sage);margin-top:8px;
}

.mission-right p{
  font-size:1.08rem;line-height:1.95;
  color:rgba(247,242,232,.62);
  margin-bottom:28px;font-weight:300;
}
.mission-right p strong{color:var(--cream);font-weight:500;}

.value-pills{
  display:flex;flex-wrap:wrap;gap:12px;margin-top:48px;
}
.pill{
  padding:10px 22px;
  border:1px solid rgba(168,213,162,.2);
  border-radius:100px;
  font-size:.75rem;letter-spacing:2px;text-transform:uppercase;
  color:var(--mint);
  transition:background .3s,border-color .3s;
}
.pill:hover{background:rgba(168,213,162,.08);border-color:var(--mint);}

/* ═══════════════════════════════════════════════
   LANDSCAPE BREAK — FOREST
═══════════════════════════════════════════════ */
.landscape-break{
  height:65vh;
  position:relative;overflow:hidden;
}
.landscape-break svg{
  width:100%;height:100%;
  display:block;
}
.landscape-caption{
  position:absolute;
  bottom:60px;left:50%;transform:translateX(-50%);
  text-align:center;z-index:2;
}
.landscape-caption h3{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(2rem,4vw,4rem);
  font-style:italic;font-weight:400;
  color:var(--dew);
  text-shadow:0 4px 32px rgba(0,0,0,.5);
}
.landscape-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to top,rgba(13,16,8,.8) 0%,transparent 40%,transparent 60%,rgba(13,16,8,.4) 100%);
}

/* ═══════════════════════════════════════════════
   PILLARS
═══════════════════════════════════════════════ */
#pillars{
  padding:160px 80px;
  position:relative;
}
.pillars-title{
  text-align:center;margin-bottom:100px;
}
.pillars-title h2{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(3rem,5.5vw,5.5rem);
  font-weight:700;color:var(--white);
  line-height:.9;letter-spacing:-1px;
}
.pillars-title h2 em{font-style:italic;color:var(--mint);}

.pillars-row{
  display:grid;grid-template-columns:repeat(3,1fr);
  gap:2px;max-width:1400px;margin:0 auto;
}
.pillar{
  padding:72px 52px;
  background:rgba(255,255,255,.018);
  border:1px solid rgba(168,213,162,.06);
  position:relative;overflow:hidden;
  transition:background .4s;
}
.pillar::after{
  content:'';
  position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--sage),transparent);
  transform:scaleX(0);
  transition:transform .5s cubic-bezier(.4,0,.2,1);
}
.pillar:hover::after{transform:scaleX(1);}
.pillar:hover{background:rgba(168,213,162,.035);}

.pillar-num{
  font-family:'Cormorant Garamond',serif;
  font-size:6rem;font-weight:700;
  color:rgba(168,213,162,.06);
  line-height:1;position:absolute;top:24px;right:32px;
}
.pillar-svg{margin-bottom:32px;}
.pillar-h{
  font-family:'Cormorant Garamond',serif;
  font-size:1.9rem;font-weight:600;
  color:var(--white);margin-bottom:18px;
  letter-spacing:-.5px;
}
.pillar-p{
  font-size:.88rem;line-height:1.85;
  color:rgba(247,242,232,.5);font-weight:300;
}

/* ═══════════════════════════════════════════════
   PRODUCTS
═══════════════════════════════════════════════ */
#products{
  padding:160px 80px;
  background:linear-gradient(180deg,var(--ink) 0%,var(--forest) 50%,var(--ink) 100%);
  position:relative;overflow:hidden;
}
#products::before{
  content:'';
  position:absolute;top:50%;left:50%;
  transform:translate(-50%,-50%);
  width:1000px;height:1000px;
  background:radial-gradient(circle,rgba(61,107,61,.18) 0%,transparent 70%);
  pointer-events:none;
}

.prod-header{
  display:flex;justify-content:space-between;align-items:flex-end;
  margin-bottom:80px;max-width:1400px;margin-left:auto;margin-right:auto;
}
.prod-header-l h2{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(3rem,5.5vw,5.5rem);
  font-weight:700;line-height:.9;letter-spacing:-1px;
  color:var(--white);
}
.prod-header-l h2 em{font-style:italic;color:var(--gold);}
.prod-header-r{
  max-width:320px;text-align:right;
  font-size:.88rem;line-height:1.8;
  color:rgba(212,237,208,.5);font-weight:300;
}

/* TABS */
.prod-tabs{
  display:flex;gap:0;
  border:1px solid rgba(168,213,162,.12);
  border-radius:100px;
  width:fit-content;
  margin:0 auto 72px;
  overflow:hidden;
  max-width:1400px;
}
.tab{
  padding:13px 36px;
  background:none;border:none;
  font-family:'DM Sans',sans-serif;
  font-size:.75rem;letter-spacing:2.5px;
  text-transform:uppercase;color:rgba(212,237,208,.45);
  cursor:pointer;transition:all .3s;
  white-space:nowrap;
}
.tab.on{
  background:linear-gradient(135deg,var(--fern),var(--moss));
  color:var(--white);
}
.tab:hover:not(.on){color:var(--mint);}

.tab-content{display:none;}
.tab-content.on{display:block;}

/* PRODUCT CARDS */
.prod-grid{
  display:grid;grid-template-columns:repeat(4,1fr);
  gap:24px;max-width:1400px;margin:0 auto;
}

.prod-card{
  background:rgba(13,16,8,.7);
  border:1px solid rgba(168,213,162,.08);
  border-radius:20px;overflow:hidden;
  transition:transform .35s cubic-bezier(.4,0,.2,1),
             border-color .35s,box-shadow .35s;
  position:relative;
}
.prod-card:hover{
  transform:translateY(-10px);
  border-color:rgba(168,213,162,.25);
  box-shadow:0 32px 80px rgba(0,0,0,.5),
             0 0 40px rgba(61,107,61,.15);
}

.prod-visual{
  height:240px;
  display:flex;align-items:center;justify-content:center;
  position:relative;overflow:hidden;
}
.prod-visual svg{
  width:120px;height:auto;
  filter:drop-shadow(0 8px 32px rgba(0,0,0,.6));
  transition:transform .4s cubic-bezier(.4,0,.2,1);
}
.prod-card:hover .prod-visual svg{transform:scale(1.08) translateY(-4px);}

.v-wellness{background:radial-gradient(ellipse at 50% 80%,rgba(45,74,45,.6) 0%,rgba(13,16,8,.8) 70%);}
.v-protein{background:radial-gradient(ellipse at 50% 80%,rgba(30,50,80,.6) 0%,rgba(13,16,8,.8) 70%);}
.v-comp{background:radial-gradient(ellipse at 50% 80%,rgba(80,50,20,.4) 0%,rgba(13,16,8,.8) 70%);}

.prod-badge{
  position:absolute;top:16px;left:16px;
  background:var(--gold);color:var(--ink);
  font-size:.58rem;font-weight:700;
  letter-spacing:2px;text-transform:uppercase;
  padding:5px 12px;border-radius:100px;
}
.prod-badge.new{background:var(--mint);color:var(--forest);}

.prod-body{padding:28px 28px 32px;}
.prod-cat{
  font-size:.62rem;letter-spacing:3px;text-transform:uppercase;
  color:var(--sage);margin-bottom:10px;
}
.prod-name{
  font-family:'Cormorant Garamond',serif;
  font-size:1.25rem;font-weight:600;
  color:var(--white);margin-bottom:10px;
  line-height:1.2;
}
.prod-desc{
  font-size:.78rem;line-height:1.75;
  color:rgba(247,242,232,.42);
  margin-bottom:24px;font-weight:300;
}
.prod-foot{
  display:flex;justify-content:space-between;align-items:center;
}
.prod-price{
  font-family:'Cormorant Garamond',serif;
  font-size:1.8rem;font-weight:700;
  color:var(--gold);line-height:1;
}
.prod-price small{
  font-family:'DM Sans',sans-serif;
  font-size:.65rem;color:rgba(247,242,232,.35);
  display:block;font-weight:300;letter-spacing:1px;
}
.add-btn{
  background:rgba(168,213,162,.08);
  border:1px solid rgba(168,213,162,.2);
  color:var(--mint);
  padding:10px 20px;border-radius:100px;
  font-family:'DM Sans',sans-serif;
  font-size:.7rem;letter-spacing:1.5px;text-transform:uppercase;
  cursor:pointer;transition:all .25s;
}
.add-btn:hover{
  background:rgba(168,213,162,.18);
  border-color:var(--mint);
  box-shadow:0 0 24px rgba(168,213,162,.15);
}

/* ═══════════════════════════════════════════════
   LANDSCAPE BREAK — MOUNTAIN
═══════════════════════════════════════════════ */

/* ═══════════════════════════════════════════════
   DISCIPLINE / ROUTINE
═══════════════════════════════════════════════ */
#routine{
  padding:160px 80px;
  position:relative;overflow:hidden;
}
.routine-bg{
  position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(26,46,26,.4) 0%,transparent 60%);
}
.routine-grid{
  display:grid;grid-template-columns:1fr 1fr;
  gap:120px;align-items:start;
  max-width:1400px;margin:0 auto;position:relative;z-index:1;
}
.routine-left h2{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(3rem,5.5vw,5.5rem);
  font-weight:700;line-height:.9;letter-spacing:-1px;
  color:var(--white);margin-bottom:32px;
}
.routine-left h2 em{font-style:italic;color:var(--mint);display:block;}
.routine-left p{
  font-size:1rem;line-height:1.9;
  color:rgba(247,242,232,.55);font-weight:300;
  margin-bottom:48px;
}

/* timeline */
.timeline{display:flex;flex-direction:column;gap:0;}
.t-item{
  display:flex;gap:32px;position:relative;
  padding-bottom:36px;
}
.t-item:last-child{padding-bottom:0;}
.t-left{
  display:flex;flex-direction:column;align-items:center;
  min-width:72px;
}
.t-time{
  font-family:'Cormorant Garamond',serif;
  font-size:1rem;font-weight:600;
  color:var(--gold);white-space:nowrap;
}
.t-dot{
  width:10px;height:10px;
  border-radius:50%;background:var(--sage);
  margin-top:8px;flex-shrink:0;
  box-shadow:0 0 16px rgba(106,155,94,.4);
}
.t-line{
  width:1px;flex:1;
  background:linear-gradient(to bottom,var(--sage),rgba(106,155,94,.1));
  margin-top:4px;
}
.t-item:last-child .t-line{display:none;}
.t-content{
  background:rgba(168,213,162,.04);
  border:1px solid rgba(168,213,162,.08);
  border-radius:12px;padding:22px 26px;flex:1;
  transition:border-color .3s,background .3s;
}
.t-content:hover{
  border-color:rgba(168,213,162,.2);
  background:rgba(168,213,162,.07);
}
.t-title{
  font-family:'Cormorant Garamond',serif;
  font-size:1.1rem;font-weight:600;
  color:var(--white);margin-bottom:6px;
}
.t-desc{
  font-size:.8rem;line-height:1.7;
  color:rgba(247,242,232,.45);font-weight:300;
}

/* ═══════════════════════════════════════════════
   QUOTE SECTION
═══════════════════════════════════════════════ */
#quotes{
  padding:140px 80px;
  text-align:center;
  border-top:1px solid rgba(168,213,162,.06);
  border-bottom:1px solid rgba(168,213,162,.06);
  position:relative;overflow:hidden;
}
#quotes::before{
  content:'"';
  position:absolute;top:-40px;left:50%;transform:translateX(-50%);
  font-family:'Cormorant Garamond',serif;
  font-size:32vw;color:rgba(168,213,162,.025);
  pointer-events:none;line-height:1;
}

.quote-wrap{max-width:900px;margin:0 auto;}
.q-text{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(1.8rem,3.8vw,3.8rem);
  font-style:italic;font-weight:400;
  color:var(--white);line-height:1.3;
  margin-bottom:40px;
  transition:opacity .4s;
}
.q-author{
  font-size:.7rem;letter-spacing:5px;
  text-transform:uppercase;color:var(--gold);
  transition:opacity .4s;
}
.q-dots{
  display:flex;gap:10px;justify-content:center;
  margin-top:48px;
}
.q-dot{
  width:6px;height:6px;border-radius:50%;
  background:rgba(168,213,162,.25);cursor:pointer;
  transition:background .3s,transform .3s;
}
.q-dot.on{background:var(--mint);transform:scale(1.4);}

/* ═══════════════════════════════════════════════
   NEWSLETTER
═══════════════════════════════════════════════ */
#cta{
  padding:160px 80px;
  position:relative;overflow:hidden;
}
.cta-inner{
  max-width:800px;margin:0 auto;text-align:center;
  position:relative;z-index:1;
}
.cta-inner h2{
  font-family:'Cormorant Garamond',serif;
  font-size:clamp(3rem,5.5vw,5.5rem);
  font-weight:700;line-height:.9;letter-spacing:-1px;
  color:var(--white);margin-bottom:24px;
}
.cta-inner h2 em{font-style:italic;color:var(--mint);}
.cta-inner p{
  font-size:1rem;line-height:1.8;
  color:rgba(247,242,232,.5);font-weight:300;
  margin-bottom:56px;
}
.cta-form{
  display:flex;gap:12px;max-width:520px;
  margin:0 auto;
}
.cta-input{
  flex:1;
  background:rgba(168,213,162,.06);
  border:1px solid rgba(168,213,162,.15);
  color:var(--white);
  padding:18px 24px;
  font-family:'DM Sans',sans-serif;font-size:.9rem;
  border-radius:100px;outline:none;
  transition:border-color .3s,background .3s;
}
.cta-input:focus{
  border-color:rgba(168,213,162,.4);
  background:rgba(168,213,162,.09);
}
.cta-input::placeholder{color:rgba(247,242,232,.3);}

/* ═══════════════════════════════════════════════
   FOOTER
═══════════════════════════════════════════════ */
footer{
  padding:100px 80px 48px;
  border-top:1px solid rgba(168,213,162,.07);
}
.footer-top{
  display:grid;grid-template-columns:2fr 1fr 1fr 1fr;
  gap:80px;margin-bottom:80px;
}
.f-logo{
  font-family:'Cormorant Garamond',serif;
  font-size:2.2rem;font-weight:700;letter-spacing:4px;
  color:var(--mint);margin-bottom:20px;display:block;
}
.f-brand p{
  font-size:.85rem;line-height:1.8;
  color:rgba(247,242,232,.4);font-weight:300;
  max-width:280px;
}
.f-col h4{
  font-size:.65rem;letter-spacing:4px;text-transform:uppercase;
  color:rgba(247,242,232,.4);margin-bottom:24px;
}
.f-col ul{list-style:none;}
.f-col ul li{margin-bottom:14px;}
.f-col ul li a{
  font-size:.85rem;color:rgba(247,242,232,.35);
  text-decoration:none;font-weight:300;
  transition:color .25s;
}
.f-col ul li a:hover{color:var(--mint);}
.footer-bottom{
  display:flex;justify-content:space-between;align-items:center;
  border-top:1px solid rgba(168,213,162,.06);
  padding-top:32px;
}
.footer-bottom p{
  font-size:.75rem;color:rgba(247,242,232,.25);
}
.socials{display:flex;gap:16px;}
.soc{
  width:38px;height:38px;border-radius:50%;
  border:1px solid rgba(168,213,162,.12);
  display:flex;align-items:center;justify-content:center;
  color:rgba(247,242,232,.3);text-decoration:none;font-size:.75rem;
  transition:all .25s;
}
.soc:hover{border-color:var(--sage);color:var(--mint);}

/* ═══════════════════════════════════════════════
   TOAST
═══════════════════════════════════════════════ */
#toast{
  position:fixed;bottom:40px;right:40px;
  background:linear-gradient(135deg,var(--forest),var(--moss));
  border:1px solid rgba(168,213,162,.2);
  color:var(--dew);padding:18px 28px;border-radius:12px;
  font-size:.85rem;z-index:9999;
  display:flex;align-items:center;gap:12px;
  transform:translateY(80px);opacity:0;
  transition:transform .35s cubic-bezier(.4,0,.2,1),opacity .35s;
  box-shadow:0 16px 48px rgba(0,0,0,.5);
}
#toast.show{transform:translateY(0);opacity:1;}

/* ═══════════════════════════════════════════════
   KEYFRAMES
═══════════════════════════════════════════════ */
@keyframes riseIn{
  from{opacity:0;transform:translateY(28px);}
  to{opacity:1;transform:none;}
}
@keyframes marqueeScroll{
  from{transform:translateX(0);}
  to{transform:translateX(-50%);}
}
@keyframes rotateSlow{
  from{transform:rotate(0deg);}
  to{transform:rotate(360deg);}
}
@keyframes scrollBarPulse{
  0%,100%{opacity:1;transform:scaleX(1);}
  50%{opacity:.4;transform:scaleX(.6);}
}
@keyframes float{
  0%,100%{transform:translateY(0);}
  50%{transform:translateY(-12px);}
}
@keyframes leafSway{
  0%,100%{transform:rotate(-3deg);}
  50%{transform:rotate(3deg);}
}
@keyframes shimmer{
  0%{filter:brightness(1);}
  50%{filter:brightness(1.15);}
  100%{filter:brightness(1);}
}
</style>

</head>
<body>

<div id="cur"></div>
<div id="cur2"></div>
<div id="toast">✦ <span id="toastMsg">Ajouté au panier !</span></div>

<!-- ════════════════════ NAV ════════════════════ -->

<nav id="nav">
  <a href="#" class="nav-logo">RISE UP</a>
  <ul class="nav-links">
    <li><a href="#mission">Mission</a></li>
    <li><a href="#pillars">Piliers</a></li>
    <li><a href="#products">Produits</a></li>
    <li><a href="#routine">Routine</a></li>
    <li><a href="#cta" class="nav-btn">Rejoindre</a></li>
  </ul>
</nav>

<!-- ════════════════════ HERO ════════════════════ -->

<section id="hero">

  <!-- SVG Forest Landscape -->

  <svg class="hero-landscape" viewBox="0 0 1600 900" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <radialGradient id="skyGrad" cx="50%" cy="30%" r="70%">
        <stop offset="0%" stop-color="#1a3a2a"/>
        <stop offset="40%" stop-color="#0f2018"/>
        <stop offset="100%" stop-color="#050c07"/>
      </radialGradient>
      <radialGradient id="moonGlow" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="#c8a84b" stop-opacity=".25"/>
        <stop offset="100%" stop-color="#c8a84b" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="sun" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="#e8c97a" stop-opacity="1"/>
        <stop offset="60%" stop-color="#c8a84b" stop-opacity=".7"/>
        <stop offset="100%" stop-color="#c8a84b" stop-opacity="0"/>
      </radialGradient>
      <filter id="glow">
        <feGaussianBlur stdDeviation="4" result="blur"/>
        <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
      </filter>
      <filter id="softBlur">
        <feGaussianBlur stdDeviation="2"/>
      </filter>
      <linearGradient id="fogGrad" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#a8d5a2" stop-opacity="0"/>
        <stop offset="100%" stop-color="#a8d5a2" stop-opacity=".07"/>
      </linearGradient>
      <linearGradient id="mountainGrad" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#2d4a2d"/>
        <stop offset="100%" stop-color="#1a2e1a"/>
      </linearGradient>
    </defs>

```
<!-- SKY -->
<rect width="1600" height="900" fill="url(#skyGrad)"/>

<!-- Stars -->
<g opacity=".6" filter="url(#softBlur)">
  <circle cx="120" cy="80" r="1" fill="#a8d5a2"/>
  <circle cx="340" cy="45" r="1.5" fill="#d4edd0"/>
  <circle cx="580" cy="90" r="1" fill="#a8d5a2"/>
  <circle cx="780" cy="30" r="1" fill="#d4edd0"/>
  <circle cx="920" cy="70" r="1.5" fill="#a8d5a2"/>
  <circle cx="1100" cy="40" r="1" fill="#d4edd0"/>
  <circle cx="1280" cy="85" r="1" fill="#a8d5a2"/>
  <circle cx="1450" cy="55" r="1.5" fill="#d4edd0"/>
  <circle cx="200" cy="130" r="1" fill="#d4edd0"/>
  <circle cx="450" cy="110" r="1" fill="#a8d5a2"/>
  <circle cx="700" cy="140" r="1.5" fill="#d4edd0"/>
  <circle cx="1000" cy="120" r="1" fill="#a8d5a2"/>
  <circle cx="1350" cy="100" r="1" fill="#d4edd0"/>
  <circle cx="60" cy="160" r="1" fill="#a8d5a2"/>
  <circle cx="1540" cy="130" r="1" fill="#d4edd0"/>
</g>

<!-- Sun / Moon glow -->
<ellipse cx="1200" cy="180" rx="200" ry="200" fill="url(#moonGlow)"/>
<circle cx="1200" cy="180" r="40" fill="url(#sun)" filter="url(#glow)"/>

<!-- Far mountains - layer 4 -->
<path d="M0,420 L160,280 L320,380 L480,240 L640,360 L800,200 L960,340 L1120,220 L1280,360 L1440,240 L1600,320 L1600,900 L0,900 Z"
  fill="#0f1f0f" opacity=".9"/>

<!-- Mountains - layer 3 -->
<path d="M0,480 L200,320 L380,430 L560,280 L720,400 L900,250 L1080,380 L1240,300 L1400,420 L1600,350 L1600,900 L0,900 Z"
  fill="#162416" opacity=".95"/>

<!-- Hill layer 2 -->
<path d="M0,560 L100,480 L250,540 L400,460 L580,530 L740,450 L900,520 L1060,460 L1220,530 L1400,480 L1600,520 L1600,900 L0,900 Z"
  fill="#1a2e1a"/>

<!-- Fog layer -->
<ellipse cx="800" cy="560" rx="900" ry="80" fill="#a8d5a2" opacity=".04"/>
<ellipse cx="400" cy="600" rx="500" ry="50" fill="#a8d5a2" opacity=".03"/>

<!-- GROUND -->
<path d="M0,620 Q400,580 800,620 Q1200,660 1600,620 L1600,900 L0,900 Z"
  fill="#1a2e1a"/>
<path d="M0,680 Q300,650 600,680 Q900,710 1200,680 Q1400,660 1600,680 L1600,900 L0,900 Z"
  fill="#0d1008"/>

<!-- Big trees - back row -->
<g opacity=".7">
  <!-- Tree 1 -->
  <polygon points="80,620 110,380 140,620" fill="#1a3a1a"/>
  <polygon points="90,580 110,420 130,580" fill="#2d4a2d"/>
  <polygon points="95,540 110,460 125,540" fill="#3d6b3d" opacity=".6"/>
  <!-- Tree 2 -->
  <polygon points="200,620 235,350 270,620" fill="#1a3a1a"/>
  <polygon points="210,580 235,390 260,580" fill="#2d4a2d"/>
  <!-- Tree 3 -->
  <polygon points="350,620 390,300 430,620" fill="#142814"/>
  <polygon points="360,570 390,340 420,570" fill="#1e3a1e"/>
  <!-- Right side trees -->
  <polygon points="1200,620 1230,390 1260,620" fill="#1a3a1a"/>
  <polygon points="1350,620 1390,320 1430,620" fill="#142814"/>
  <polygon points="1360,570 1390,360 1420,570" fill="#1e3a1e"/>
  <polygon points="1480,620 1510,420 1540,620" fill="#1a3a1a"/>
</g>

<!-- Front trees - big -->
<g>
  <!-- Far left large tree -->
  <polygon points="-20,900 50,580 120,900" fill="#0d1a0d"/>
  <polygon points="-10,850 50,620 110,850" fill="#142814"/>
  <polygon points="0,800 50,660 100,800" fill="#1a3a1a" opacity=".8"/>
  <rect x="42" y="860" width="18" height="40" fill="#0a0f0a"/>

  <!-- Left tree cluster -->
  <polygon points="80,900 160,520 240,900" fill="#0f1f0f"/>
  <polygon points="90,850 160,570 230,850" fill="#162416"/>
  <polygon points="100,780 160,620 220,780" fill="#1a2e1a" opacity=".7"/>
  <rect x="150" y="860" width="22" height="40" fill="#0a0f0a"/>

  <!-- Mid-left -->
  <polygon points="180,900 240,600 300,900" fill="#0d1a0d"/>
  <polygon points="190,850 240,640 290,850" fill="#142814"/>
  <rect x="232" y="860" width="16" height="40" fill="#080e08"/>

  <!-- Right cluster -->
  <polygon points="1300,900 1380,500 1460,900" fill="#0f1f0f"/>
  <polygon points="1310,840 1380,550 1450,840" fill="#162416"/>
  <polygon points="1320,770 1380,600 1440,770" fill="#1a2e1a" opacity=".7"/>
  <rect x="1372" y="855" width="22" height="45" fill="#0a0f0a"/>

  <polygon points="1400,900 1465,560 1530,900" fill="#0d1a0d"/>
  <polygon points="1410,850 1465,600 1520,850" fill="#142814"/>
  <rect x="1457" y="860" width="18" height="40" fill="#080e08"/>

  <!-- Far right -->
  <polygon points="1480,900 1550,540 1620,900" fill="#0b160b"/>
  <polygon points="1490,850 1550,580 1610,850" fill="#0f1f0f"/>
</g>

<!-- Ground foliage -->
<ellipse cx="60" cy="900" rx="120" ry="20" fill="#1a2e1a" opacity=".8"/>
<ellipse cx="300" cy="900" rx="80" ry="15" fill="#142814" opacity=".6"/>
<ellipse cx="1400" cy="900" rx="140" ry="22" fill="#1a2e1a" opacity=".8"/>

<!-- Mist at ground -->
<rect x="0" y="820" width="1600" height="80" fill="url(#fogGrad)"/>

<!-- Light rays from moon -->
<g opacity=".04" filter="url(#softBlur)">
  <line x1="1200" y1="180" x2="600" y2="900" stroke="#e8c97a" stroke-width="40"/>
  <line x1="1200" y1="180" x2="1000" y2="900" stroke="#e8c97a" stroke-width="20"/>
</g>
```

  </svg>

  <div class="hero-overlay"></div>

  <div class="hero-content">
    <div class="hero-tag">Belgique · Bien-être · Nature</div>
    <h1 class="hero-h1">
      RISE<br>
      <em>UP</em>
      <span>Lève-toi. Deviens.</span>
    </h1>
    <p class="hero-p">La première marque belge de bien-être conçue pour la jeunesse. Soins naturels, protéines végétales, et une philosophie qui transforme.</p>
    <div class="hero-actions">
      <a href="#products" class="btn-forest">Découvrir les produits</a>
      <a href="#mission" class="btn-ghost">Notre histoire</a>
    </div>
  </div>

  <div class="hero-badge">
    <div class="hero-badge-text">100%<br>Naturel</div>
    <div class="hero-badge-num">∞</div>
    <div class="hero-badge-text">Potentiel</div>
  </div>

  <div class="hero-scroll">
    <span>Explorer</span>
    <div class="scroll-bar"></div>
  </div>
</section>

<!-- ════════════════════ MARQUEE ════════════════════ -->

<div class="marquee-wrap">
  <div class="marquee-inner" id="mq">
    <div class="m-item"><span class="m-word">Discipline</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Bien-être naturel</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Protéines végétales</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Force intérieure</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">100% Vegan</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Fait pour les jeunes</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Rise Up Belgium</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Discipline</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Bien-être naturel</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Protéines végétales</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Force intérieure</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">100% Vegan</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Fait pour les jeunes</span><span class="m-sep">◆</span></div>
    <div class="m-item"><span class="m-word">Rise Up Belgium</span><span class="m-sep">◆</span></div>
  </div>
</div>

<!-- ════════════════════ MISSION ════════════════════ -->

<section id="mission">
  <div class="mission-grid">
    <div class="mission-left reveal-left">
      <div class="section-label">Notre histoire</div>
      <h2>Créé pour<em>les audacieux</em></h2>
      <div class="mission-stats">
        <div class="m-stat">
          <div class="m-stat-n">100%</div>
          <div class="m-stat-l">Ingrédients naturels</div>
        </div>
        <div class="m-stat">
          <div class="m-stat-n">0</div>
          <div class="m-stat-l">Compromis sur la qualité</div>
        </div>
        <div class="m-stat">
          <div class="m-stat-n">∞</div>
          <div class="m-stat-l">Potentiel en chacun</div>
        </div>
        <div class="m-stat">
          <div class="m-stat-n">🇧🇪</div>
          <div class="m-stat-l">Fièrement belge</div>
        </div>
      </div>
    </div>
    <div class="mission-right reveal-right">
      <div class="section-label">Manifeste</div>
      <p>RISE UP est né d'une conviction profonde : <strong>nos jeunes méritent mieux.</strong> Mieux que des produits bourrés de chimie. Mieux que des discours creux. Mieux qu'une culture qui les écrase.</p>
      <p>On a construit une marque qui <strong>te ressemble vraiment</strong> — des soins capillaires aux actifs naturels puissants, des protéines végétales complètes, une philosophie de vie bâtie sur la discipline, la constance et le respect profond de soi.</p>
      <p>Parce que <strong>prendre soin de ton corps</strong>, c'est aussi prendre soin de qui tu deviendras.</p>
      <div class="value-pills">
        <div class="pill">🌿 Vegan</div>
        <div class="pill">🧪 Sans sulfates</div>
        <div class="pill">💚 Éthique</div>
        <div class="pill">🇧🇪 Local</div>
        <div class="pill">♻️ Éco-responsable</div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════════════ LANDSCAPE 1 — VALLEY ════════════════════ -->

<div class="landscape-break">
  <svg viewBox="0 0 1600 600" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient id="valSky" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#0d2a1a"/>
        <stop offset="60%" stop-color="#1a3a20"/>
        <stop offset="100%" stop-color="#0d1a10"/>
      </linearGradient>
      <radialGradient id="sunRise" cx="25%" cy="40%" r="40%">
        <stop offset="0%" stop-color="#e8c97a" stop-opacity=".5"/>
        <stop offset="50%" stop-color="#c8a84b" stop-opacity=".2"/>
        <stop offset="100%" stop-color="#c8a84b" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="horizGlow" cx="25%" cy="80%" r="40%">
        <stop offset="0%" stop-color="#6a9b5e" stop-opacity=".3"/>
        <stop offset="100%" stop-color="#6a9b5e" stop-opacity="0"/>
      </radialGradient>
    </defs>
    <rect width="1600" height="600" fill="url(#valSky)"/>
    <ellipse cx="400" cy="240" rx="500" ry="300" fill="url(#sunRise)"/>
    <circle cx="380" cy="180" r="28" fill="#e8c97a" opacity=".6" filter="url(#glow)"/>
    <ellipse cx="600" cy="500" rx="800" ry="120" fill="url(#horizGlow)"/>
    <!-- Far mountains -->
    <path d="M0,300 L150,160 L300,260 L500,120 L700,240 L900,100 L1100,220 L1300,140 L1500,240 L1600,200 L1600,600 L0,600Z" fill="#142a14" opacity=".7"/>
    <!-- Mid range -->
    <path d="M0,380 L200,240 L400,320 L600,180 L800,300 L1000,180 L1200,280 L1400,220 L1600,300 L1600,600 L0,600Z" fill="#1a3a1a" opacity=".85"/>
    <!-- Rolling hills -->
    <path d="M0,440 Q200,380 400,430 Q600,480 800,420 Q1000,360 1200,420 Q1400,480 1600,440 L1600,600 L0,600Z" fill="#1f4020"/>
    <path d="M0,500 Q300,460 600,500 Q900,540 1200,490 Q1400,460 1600,500 L1600,600 L0,600Z" fill="#162e16"/>
    <path d="M0,560 Q400,530 800,560 Q1200,590 1600,555 L1600,600 L0,600Z" fill="#0f1f0f"/>
    <!-- Pine trees silhouette -->
    <g fill="#0d1a0d">
      <polygon points="0,500 20,400 40,500"/>
      <polygon points="30,500 55,380 80,500"/>
      <polygon points="70,500 100,360 130,500"/>
      <polygon points="1480,500 1500,390 1520,500"/>
      <polygon points="1510,500 1540,370 1570,500"/>
      <polygon points="1550,500 1580,400 1610,500"/>
    </g>
    <!-- Mist -->
    <ellipse cx="800" cy="480" rx="1000" ry="40" fill="#a8d5a2" opacity=".06"/>
    <ellipse cx="800" cy="520" rx="1200" ry="30" fill="#a8d5a2" opacity=".04"/>
    <!-- Light rays -->
    <g opacity=".06">
      <path d="M380,180 L-100,600" stroke="#e8c97a" stroke-width="60"/>
      <path d="M380,180 L200,600" stroke="#e8c97a" stroke-width="30"/>
      <path d="M380,180 L600,600" stroke="#e8c97a" stroke-width="20"/>
    </g>
  </svg>
  <div class="landscape-overlay"></div>
  <div class="landscape-caption">
    <h3>Là où la nature inspire la force</h3>
  </div>
</div>

<!-- ════════════════════ PILLARS ════════════════════ -->

<section id="pillars">
  <div class="pillars-title reveal">
    <div class="section-label" style="justify-content:center">Ce qu'on défend</div>
    <h2>Les 3 piliers<br><em>RISE UP</em></h2>
  </div>
  <div class="pillars-row">
    <div class="pillar reveal">
      <div class="pillar-num">01</div>
      <!-- Leaf SVG icon -->
      <div class="pillar-svg">
        <svg width="52" height="52" viewBox="0 0 52 52" fill="none">
          <path d="M8 44 C8 44 12 20 26 12 C40 4 48 8 48 8 C48 8 44 36 26 44 C18 44 8 44 8 44Z" fill="rgba(61,107,61,.2)" stroke="#6a9b5e" stroke-width="1.5"/>
          <line x1="26" y1="44" x2="26" y2="14" stroke="#6a9b5e" stroke-width="1" opacity=".6"/>
          <line x1="26" y1="30" x2="38" y2="22" stroke="#6a9b5e" stroke-width="1" opacity=".4"/>
          <line x1="26" y1="36" x2="16" y2="28" stroke="#6a9b5e" stroke-width="1" opacity=".4"/>
        </svg>
      </div>
      <h3 class="pillar-h">Corps Sain</h3>
      <p class="pillar-p">Des soins capillaires aux actifs naturels puissants — beurre de karité, huile d'argan, aloe vera bio. Des protéines végétales complètes pour nourrir ta force de l'intérieur. Ce que tu mets sur et dans ton corps façonne qui tu deviens.</p>
    </div>
    <div class="pillar reveal">
      <div class="pillar-num">02</div>
      <div class="pillar-svg">
        <svg width="52" height="52" viewBox="0 0 52 52" fill="none">
          <circle cx="26" cy="20" r="12" fill="rgba(61,107,61,.2)" stroke="#6a9b5e" stroke-width="1.5"/>
          <path d="M26 32 L26 46" stroke="#6a9b5e" stroke-width="1.5"/>
          <path d="M18 40 L26 46 L34 40" stroke="#6a9b5e" stroke-width="1.5" fill="none"/>
          <circle cx="26" cy="20" r="4" fill="#6a9b5e" opacity=".5"/>
          <path d="M22 20 Q26 14 30 20" stroke="#a8d5a2" stroke-width="1" fill="none" opacity=".6"/>
        </svg>
      </div>
      <h3 class="pillar-h">Mental Fort</h3>
      <p class="pillar-p">La discipline ne se construit pas en un jour. On te donne les outils concrets : routines guidées, méthodes de concentration, gestion du stress. Un mental solide, ça se travaille comme un muscle — avec constance et intention.</p>
    </div>
    <div class="pillar reveal">
      <div class="pillar-num">03</div>
      <div class="pillar-svg">
        <svg width="52" height="52" viewBox="0 0 52 52" fill="none">
          <polygon points="26,6 32,18 46,20 36,30 38,44 26,38 14,44 16,30 6,20 20,18" fill="rgba(61,107,61,.15)" stroke="#6a9b5e" stroke-width="1.5"/>
          <polygon points="26,14 29,20 36,21 31,26 33,33 26,30 19,33 21,26 16,21 23,20" fill="rgba(106,155,94,.2)"/>
          <circle cx="26" cy="26" r="3" fill="#6a9b5e" opacity=".7"/>
        </svg>
      </div>
      <h3 class="pillar-h">Communauté</h3>
      <p class="pillar-p">Tu n'es jamais seul. RISE UP c'est un mouvement — des jeunes belges et francophones qui s'entraident, se challengent et s'élèvent ensemble. Des milliers de personnes qui ont choisi de se lever chaque matin avec intention.</p>
    </div>
  </div>
</section>

<!-- ════════════════════ PRODUCTS ════════════════════ -->

<section id="products">
  <div class="prod-header reveal">
    <div class="prod-header-l">
      <div class="section-label">La collection</div>
      <h2>Nos<br><em>Produits</em></h2>
    </div>
    <div class="prod-header-r">Chaque formule est pensée pour maximiser ton bien-être. Ingrédients éthiques, efficacité prouvée, prix juste.</div>
  </div>

  <div class="prod-tabs" style="max-width:none;margin-left:80px;">
    <button class="tab on" onclick="switchTab(this,'t-soin')">🌿 Soins &amp; Capillaires</button>
    <button class="tab" onclick="switchTab(this,'t-prot')">💪 Protéines Végétales</button>
    <button class="tab" onclick="switchTab(this,'t-comp')">⚡ Compléments</button>
  </div>

  <!-- TAB: SOINS -->

  <div class="tab-content on" id="t-soin">
    <div class="prod-grid">

```
  <!-- Shampoing -->
  <div class="prod-card reveal">
    <div class="prod-visual v-wellness">
      <span class="prod-badge">Bestseller</span>
      <svg width="80" height="160" viewBox="0 0 80 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 4s ease-in-out infinite;">
        <defs>
          <linearGradient id="shampGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#2d6b3d"/>
            <stop offset="100%" stop-color="#1a3a2a"/>
          </linearGradient>
          <linearGradient id="shampShine" x1="0" y1="0" x2="1" y2="0">
            <stop offset="0%" stop-color="rgba(255,255,255,.0)"/>
            <stop offset="40%" stop-color="rgba(255,255,255,.15)"/>
            <stop offset="100%" stop-color="rgba(255,255,255,.0)"/>
          </linearGradient>
        </defs>
        <!-- Bottle body -->
        <rect x="18" y="40" width="44" height="100" rx="8" fill="url(#shampGrad)"/>
        <!-- Shine -->
        <rect x="18" y="40" width="44" height="100" rx="8" fill="url(#shampShine)"/>
        <!-- Pump -->
        <rect x="34" y="8" width="12" height="36" rx="4" fill="#3d8b4d"/>
        <ellipse cx="40" cy="8" rx="8" ry="4" fill="#4aa05e"/>
        <!-- Label -->
        <rect x="22" y="70" width="36" height="50" rx="4" fill="rgba(255,255,255,.06)"/>
        <text x="40" y="90" text-anchor="middle" font-family="serif" font-size="7" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="40" y="100" text-anchor="middle" font-family="serif" font-size="5" fill="rgba(168,213,162,.6)">UP</text>
        <text x="40" y="112" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(168,213,162,.45)">SHAMPOING</text>
        <text x="40" y="120" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(168,213,162,.35)">MENTHE · ALOE</text>
        <!-- Leaf deco -->
        <path d="M24 66 Q28 60 32 66 Q28 68 24 66Z" fill="#4aa05e" opacity=".6"/>
        <!-- Cap shine -->
        <ellipse cx="40" cy="140" rx="20" ry="3" fill="rgba(168,213,162,.08)"/>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Capillaire · 250ml</div>
      <div class="prod-name">Shampoing Frais Menthe &amp; Aloe</div>
      <div class="prod-desc">Formule légère sans sulfates. Purifie le cuir chevelu, apporte une fraîcheur longue durée. Menthe bio + aloe vera.</div>
      <div class="prod-foot">
        <div class="prod-price">12.90€ <small>250ml · Vegan</small></div>
        <button class="add-btn" onclick="addCart('Shampoing Frais')">+ Ajouter</button>
      </div>
    </div>
  </div>

  <!-- Après-shampoing -->
  <div class="prod-card reveal">
    <div class="prod-visual v-wellness">
      <svg width="80" height="160" viewBox="0 0 80 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 4.5s ease-in-out infinite .5s;">
        <defs>
          <linearGradient id="condGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#3d6b3d"/>
            <stop offset="100%" stop-color="#2a4a2a"/>
          </linearGradient>
        </defs>
        <!-- Wide jar body -->
        <rect x="10" y="60" width="60" height="80" rx="6" fill="url(#condGrad)"/>
        <rect x="10" y="60" width="60" height="80" rx="6" fill="url(#shampShine)"/>
        <!-- Lid -->
        <rect x="8" y="50" width="64" height="16" rx="4" fill="#4a7a4a"/>
        <rect x="14" y="53" width="52" height="10" rx="3" fill="rgba(255,255,255,.1)"/>
        <!-- Label -->
        <rect x="14" y="72" width="52" height="52" rx="4" fill="rgba(255,255,255,.05)"/>
        <text x="40" y="90" text-anchor="middle" font-family="serif" font-size="7" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="40" y="100" text-anchor="middle" font-family="serif" font-size="4.5" fill="rgba(168,213,162,.6)">APRÈS-SHAMPOING</text>
        <text x="40" y="112" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.4)">KARITÉ · COCO</text>
        <ellipse cx="40" cy="140" rx="26" ry="3" fill="rgba(168,213,162,.08)"/>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Capillaire · 250ml</div>
      <div class="prod-name">Après-Shampoing Revitalisant</div>
      <div class="prod-desc">Kératine végétale + beurre de karité + huile de coco. Démêle, nourrit et protège sans alourdir.</div>
      <div class="prod-foot">
        <div class="prod-price">13.90€ <small>250ml · Sans silicones</small></div>
        <button class="add-btn" onclick="addCart('Après-Shampoing')">+ Ajouter</button>
      </div>
    </div>
  </div>

  <!-- Gel nettoyant -->
  <div class="prod-card reveal">
    <div class="prod-visual v-wellness">
      <svg width="70" height="160" viewBox="0 0 70 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 3.8s ease-in-out infinite 1s;">
        <defs>
          <linearGradient id="gelGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#1e4a2e"/>
            <stop offset="100%" stop-color="#152a1e"/>
          </linearGradient>
        </defs>
        <!-- Tube body -->
        <rect x="15" y="30" width="40" height="110" rx="10" fill="url(#gelGrad)"/>
        <rect x="15" y="30" width="40" height="110" rx="10" fill="url(#shampShine)"/>
        <!-- Cap -->
        <rect x="20" y="18" width="30" height="18" rx="6" fill="#2d6a3d"/>
        <rect x="24" y="21" width="22" height="12" rx="4" fill="rgba(255,255,255,.1)"/>
        <!-- Label area -->
        <rect x="18" y="55" width="34" height="60" rx="4" fill="rgba(255,255,255,.05)"/>
        <text x="35" y="74" text-anchor="middle" font-family="serif" font-size="6" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="35" y="84" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.55)">GEL NETTOYANT</text>
        <text x="35" y="94" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.4)">EAU DE ROSE</text>
        <!-- Bottom crimp -->
        <rect x="15" y="132" width="40" height="8" rx="2" fill="#1a3a24" opacity=".8"/>
        <ellipse cx="35" cy="140" rx="18" ry="3" fill="rgba(168,213,162,.07)"/>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Visage · 150ml</div>
      <div class="prod-name">Gel Nettoyant Peau Nette</div>
      <div class="prod-desc">Eau de rose + zinc + acide salicylique végétal. Purifie sans dessécher. Idéal peaux mixtes à grasses.</div>
      <div class="prod-foot">
        <div class="prod-price">11.90€ <small>150ml · Testé dermo</small></div>
        <button class="add-btn" onclick="addCart('Gel Nettoyant')">+ Ajouter</button>
      </div>
    </div>
  </div>

  <!-- Huile corps -->
  <div class="prod-card reveal">
    <div class="prod-visual v-wellness">
      <span class="prod-badge new">Nouveau</span>
      <svg width="60" height="160" viewBox="0 0 60 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 5s ease-in-out infinite 0.8s;">
        <defs>
          <linearGradient id="oilGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#4a7a3a"/>
            <stop offset="100%" stop-color="#2a4a24"/>
          </linearGradient>
        </defs>
        <!-- Dropper bottle -->
        <rect x="14" y="55" width="32" height="85" rx="8" fill="url(#oilGrad)"/>
        <rect x="14" y="55" width="32" height="85" rx="8" fill="url(#shampShine)"/>
        <!-- Neck -->
        <rect x="22" y="35" width="16" height="24" rx="4" fill="#3d6b2d"/>
        <!-- Dropper cap -->
        <ellipse cx="30" cy="33" rx="12" ry="6" fill="#2d5a22"/>
        <rect x="27" y="10" width="6" height="26" rx="3" fill="#4a7a3a"/>
        <circle cx="30" cy="8" r="5" fill="#3d6b2d"/>
        <!-- Label -->
        <rect x="17" y="68" width="26" height="55" rx="3" fill="rgba(255,255,255,.05)"/>
        <text x="30" y="84" text-anchor="middle" font-family="serif" font-size="5.5" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="30" y="95" text-anchor="middle" font-family="sans-serif" font-size="3.2" fill="rgba(168,213,162,.5)">HUILE CORPS</text>
        <text x="30" y="105" text-anchor="middle" font-family="sans-serif" font-size="3" fill="rgba(168,213,162,.35)">ARGAN · JOJ.</text>
        <!-- Liquid visible -->
        <rect x="16" y="100" width="28" height="38" rx="6" fill="rgba(200,168,75,.08)"/>
        <ellipse cx="30" cy="140" rx="14" ry="2.5" fill="rgba(168,213,162,.07)"/>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Corps · 100ml</div>
      <div class="prod-name">Huile Corps Revitalisante</div>
      <div class="prod-desc">Argan + jojoba + vitamine E. Pénètre vite, peau satinée dès la 1ère application. Parfum boisé subtil.</div>
      <div class="prod-foot">
        <div class="prod-price">18.90€ <small>100ml · Pressage froid</small></div>
        <button class="add-btn" onclick="addCart('Huile Corps')">+ Ajouter</button>
      </div>
    </div>
  </div>
</div>
```

  </div>

  <!-- TAB: PROTEINES -->

  <div class="tab-content" id="t-prot">
    <div class="prod-grid">
      <div class="prod-card reveal">
        <div class="prod-visual v-protein">
          <span class="prod-badge">Pro</span>
          <svg width="90" height="160" viewBox="0 0 90 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 4s ease-in-out infinite;">
            <defs>
              <linearGradient id="bagGrad" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#1e3050"/>
                <stop offset="100%" stop-color="#0f1a2e"/>
              </linearGradient>
            </defs>
            <!-- Protein bag/pouch -->
            <path d="M15,30 L75,30 L80,140 L10,140Z" fill="url(#bagGrad)"/>
            <path d="M15,30 L75,30 L80,140 L10,140Z" fill="url(#shampShine)"/>
            <!-- Zip top -->
            <rect x="12" y="24" width="66" height="10" rx="3" fill="#2a4a6a"/>
            <rect x="14" y="26" width="62" height="6" rx="2" fill="rgba(255,255,255,.08)"/>
            <!-- Label -->
            <rect x="18" y="50" width="54" height="70" rx="4" fill="rgba(255,255,255,.05)"/>
            <text x="45" y="72" text-anchor="middle" font-family="serif" font-size="9" fill="#a8d5a2" font-weight="bold">RISE</text>
            <text x="45" y="84" text-anchor="middle" font-family="sans-serif" font-size="5" fill="rgba(168,213,162,.7)" font-weight="500">WHEY VÉGÉTALE</text>
            <rect x="22" y="88" width="46" height="1" fill="rgba(168,213,162,.2)"/>
            <text x="45" y="100" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(168,213,162,.5)">CHOCOLAT NOIR</text>
            <text x="45" y="110" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.35)">25g PROTÉINES</text>
            <!-- Scoop icon -->
            <path d="M34 118 Q45 114 56 118 Q56 125 45 126 Q34 125 34 118Z" fill="rgba(168,213,162,.1)" stroke="rgba(168,213,162,.3)" stroke-width=".8"/>
          </svg>
        </div>
        <div class="prod-body">
          <div class="prod-cat">Protéine Végétale · 500g</div>
          <div class="prod-name">Whey Végétale Chocolat Noir</div>
          <div class="prod-desc">25g de protéines par dose. Isolat de pois + riz brun. Sans lactose, sans gluten. Goût premium intense.</div>
          <div class="prod-foot">
            <div class="prod-price">34.90€ <small>500g · 20 doses</small></div>
            <button class="add-btn" onclick="addCart('Whey Végétale')">+ Ajouter</button>
          </div>
        </div>
      </div>

```
  <div class="prod-card reveal">
    <div class="prod-visual v-protein">
      <svg width="90" height="160" viewBox="0 0 90 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 4.8s ease-in-out infinite .4s;">
        <defs>
          <linearGradient id="bag2Grad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#2a3a50"/>
            <stop offset="100%" stop-color="#141e30"/>
          </linearGradient>
        </defs>
        <path d="M15,30 L75,30 L80,140 L10,140Z" fill="url(#bag2Grad)"/>
        <path d="M15,30 L75,30 L80,140 L10,140Z" fill="url(#shampShine)"/>
        <rect x="12" y="24" width="66" height="10" rx="3" fill="#3a5a7a"/>
        <rect x="14" y="26" width="62" height="6" rx="2" fill="rgba(255,255,255,.08)"/>
        <rect x="18" y="50" width="54" height="70" rx="4" fill="rgba(255,255,255,.04)"/>
        <text x="45" y="72" text-anchor="middle" font-family="serif" font-size="9" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="45" y="84" text-anchor="middle" font-family="sans-serif" font-size="5" fill="rgba(168,213,162,.7)" font-weight="500">WHEY VÉGÉTALE</text>
        <rect x="22" y="88" width="46" height="1" fill="rgba(168,213,162,.2)"/>
        <text x="45" y="100" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(168,213,162,.5)">BANANE VANILLE</text>
        <text x="45" y="110" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.35)">22g PROTÉINES</text>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Protéine Végétale · 500g</div>
      <div class="prod-name">Shake Banane Vanille</div>
      <div class="prod-desc">22g de protéines. Chanvre + pois chiches. Parfait post-entraînement, digestion ultra-facile.</div>
      <div class="prod-foot">
        <div class="prod-price">31.90€ <small>500g · 20 doses</small></div>
        <button class="add-btn" onclick="addCart('Shake Banane')">+ Ajouter</button>
      </div>
    </div>
  </div>

  <div class="prod-card reveal">
    <div class="prod-visual v-protein">
      <span class="prod-badge new">Nouveau</span>
      <svg width="120" height="130" viewBox="0 0 120 130" xmlns="http://www.w3.org/2000/svg" style="animation:float 4.2s ease-in-out infinite .9s;">
        <!-- Protein bar wrapper -->
        <rect x="10" y="30" width="100" height="60" rx="10" fill="#1e3050"/>
        <rect x="10" y="30" width="100" height="60" rx="10" fill="url(#shampShine)"/>
        <!-- Wrapper folds -->
        <rect x="10" y="30" width="8" height="60" rx="2" fill="rgba(255,255,255,.03)"/>
        <rect x="102" y="30" width="8" height="60" rx="2" fill="rgba(255,255,255,.03)"/>
        <!-- Label -->
        <rect x="20" y="35" width="80" height="50" rx="6" fill="rgba(168,213,162,.06)"/>
        <text x="60" y="57" text-anchor="middle" font-family="serif" font-size="11" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="60" y="68" text-anchor="middle" font-family="sans-serif" font-size="5" fill="rgba(168,213,162,.6)" font-weight="500">BARRE PROTÉINÉE</text>
        <text x="60" y="78" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(168,213,162,.4)">CACAHUÈTE · 15g PROT.</text>
        <!-- Bite mark suggestion -->
        <ellipse cx="60" cy="120" rx="40" ry="5" fill="rgba(168,213,162,.05)"/>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Barres · 60g</div>
      <div class="prod-name">Barre RISE Cacahuète</div>
      <div class="prod-desc">15g de protéines végétales par barre. Sucres réduits, fibres élevées. Snack sain et vraiment rassasiant.</div>
      <div class="prod-foot">
        <div class="prod-price">2.90€ <small>par barre · Pack ×12</small></div>
        <button class="add-btn" onclick="addCart('Barre Cacahuète')">+ Ajouter</button>
      </div>
    </div>
  </div>

  <div class="prod-card reveal">
    <div class="prod-visual v-protein">
      <svg width="90" height="160" viewBox="0 0 90 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 5.2s ease-in-out infinite 1.2s;">
        <defs>
          <linearGradient id="gainerGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#1a3a20"/>
            <stop offset="100%" stop-color="#0f2014"/>
          </linearGradient>
        </defs>
        <!-- Big container -->
        <ellipse cx="45" cy="38" rx="36" ry="10" fill="#2d5a35"/>
        <rect x="9" y="38" width="72" height="100" rx="6" fill="url(#gainerGrad)"/>
        <rect x="9" y="38" width="72" height="100" rx="6" fill="url(#shampShine)"/>
        <!-- Lid rim -->
        <ellipse cx="45" cy="38" rx="36" ry="10" fill="rgba(255,255,255,.0)" stroke="#3d6b45" stroke-width="2"/>
        <!-- Label -->
        <rect x="14" y="55" width="62" height="65" rx="4" fill="rgba(255,255,255,.04)"/>
        <text x="45" y="76" text-anchor="middle" font-family="serif" font-size="8" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="45" y="87" text-anchor="middle" font-family="sans-serif" font-size="4.5" fill="rgba(168,213,162,.7)">GAINER VERT</text>
        <rect x="18" y="91" width="54" height="1" fill="rgba(168,213,162,.15)"/>
        <text x="45" y="102" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.45)">40g PROT. · SPIRULINE</text>
        <text x="45" y="112" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.35)">CHLORELLA · BCAA</text>
        <ellipse cx="45" cy="138" rx="30" ry="4" fill="rgba(168,213,162,.05)"/>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Protéine Végétale · 1kg</div>
      <div class="prod-name">Gainer Nature Vert</div>
      <div class="prod-desc">Prise de masse propre. 40g protéines + glucides complexes. Spiruline & chlorella pour la récupération.</div>
      <div class="prod-foot">
        <div class="prod-price">39.90€ <small>1kg · 20 doses</small></div>
        <button class="add-btn" onclick="addCart('Gainer Nature Vert')">+ Ajouter</button>
      </div>
    </div>
  </div>
</div>
```

  </div>

  <!-- TAB: COMPLEMENTS -->

  <div class="tab-content" id="t-comp">
    <div class="prod-grid">
      <div class="prod-card reveal">
        <div class="prod-visual v-comp">
          <svg width="70" height="160" viewBox="0 0 70 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 4s ease-in-out infinite;">
            <defs>
              <linearGradient id="capGrad" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#3a2a10"/>
                <stop offset="100%" stop-color="#1e1608"/>
              </linearGradient>
            </defs>
            <!-- Capsule bottle -->
            <ellipse cx="35" cy="44" rx="22" ry="7" fill="#4a3818"/>
            <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#capGrad)"/>
            <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#shampShine)"/>
            <!-- Cap -->
            <ellipse cx="35" cy="44" rx="22" ry="7" fill="#5a4820"/>
            <rect x="16" y="38" width="38" height="10" rx="5" fill="#6a5828"/>
            <!-- Label -->
            <rect x="16" y="60" width="38" height="62" rx="4" fill="rgba(255,255,255,.05)"/>
            <text x="35" y="78" text-anchor="middle" font-family="serif" font-size="6.5" fill="#e8c97a" font-weight="bold">RISE</text>
            <text x="35" y="89" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(232,201,122,.65)">PRE-WORKOUT</text>
            <rect x="19" y="92" width="32" height="1" fill="rgba(232,201,122,.2)"/>
            <text x="35" y="102" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(232,201,122,.45)">MATCHA · CITRON</text>
            <text x="35" y="112" text-anchor="middle" font-family="sans-serif" font-size="3" fill="rgba(232,201,122,.3)">200mg CAFÉINE NAT.</text>
            <!-- Capsules visible through glass -->
            <ellipse cx="35" cy="138" rx="18" ry="3" fill="rgba(232,201,122,.05)"/>
          </svg>
        </div>
        <div class="prod-body">
          <div class="prod-cat">Énergie · 200g · 30 doses</div>
          <div class="prod-name">Pre-Workout Matcha Citron</div>
          <div class="prod-desc">Caféine naturelle du thé vert + L-théanine + beta-alanine. Énergie propre sans crash. Concentration 3h.</div>
          <div class="prod-foot">
            <div class="prod-price">24.90€ <small>30 doses · Vegan</small></div>
            <button class="add-btn" onclick="addCart('Pre-Workout Matcha')">+ Ajouter</button>
          </div>
        </div>
      </div>

```
  <div class="prod-card reveal">
    <div class="prod-visual v-comp">
      <span class="prod-badge">Top ventes</span>
      <svg width="70" height="160" viewBox="0 0 70 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 4.6s ease-in-out infinite .5s;">
        <defs>
          <linearGradient id="sleepGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#1e1a3a"/>
            <stop offset="100%" stop-color="#0f0e20"/>
          </linearGradient>
        </defs>
        <ellipse cx="35" cy="44" rx="22" ry="7" fill="#2e2a4a"/>
        <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#sleepGrad)"/>
        <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#shampShine)"/>
        <ellipse cx="35" cy="44" rx="22" ry="7" fill="#3e3a5a"/>
        <rect x="16" y="38" width="38" height="10" rx="5" fill="#4e4a6a"/>
        <rect x="16" y="60" width="38" height="62" rx="4" fill="rgba(255,255,255,.04)"/>
        <text x="35" y="78" text-anchor="middle" font-family="serif" font-size="6.5" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="35" y="89" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(168,213,162,.65)">SLEEP &amp; RECOVER</text>
        <rect x="19" y="92" width="32" height="1" fill="rgba(168,213,162,.15)"/>
        <text x="35" y="102" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.45)">MAGNÉSIUM · ASHW.</text>
        <text x="35" y="112" text-anchor="middle" font-family="sans-serif" font-size="3" fill="rgba(168,213,162,.3)">60 GÉLULES VEGAN</text>
        <!-- Moon icon -->
        <path d="M30,120 Q35,115 40,120 Q37,126 30,120Z" fill="rgba(168,213,162,.15)" stroke="rgba(168,213,162,.3)" stroke-width=".8"/>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Récupération · 60 gélules</div>
      <div class="prod-name">Sleep &amp; Recover</div>
      <div class="prod-desc">Magnésium bisglycinate + ashwagandha KSM-66 + mélatonine végétale. Sommeil profond, réveil reposé.</div>
      <div class="prod-foot">
        <div class="prod-price">22.90€ <small>60 gélules · 2 mois</small></div>
        <button class="add-btn" onclick="addCart('Sleep & Recover')">+ Ajouter</button>
      </div>
    </div>
  </div>

  <div class="prod-card reveal">
    <div class="prod-visual v-comp">
      <svg width="70" height="160" viewBox="0 0 70 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 3.9s ease-in-out infinite 1s;">
        <defs>
          <linearGradient id="vitGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#2a1e0a"/>
            <stop offset="100%" stop-color="#160f04"/>
          </linearGradient>
        </defs>
        <ellipse cx="35" cy="44" rx="22" ry="7" fill="#3a2e12"/>
        <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#vitGrad)"/>
        <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#shampShine)"/>
        <ellipse cx="35" cy="44" rx="22" ry="7" fill="#4a3c1a"/>
        <rect x="16" y="38" width="38" height="10" rx="5" fill="#5a4c22"/>
        <rect x="16" y="60" width="38" height="62" rx="4" fill="rgba(255,255,255,.04)"/>
        <text x="35" y="78" text-anchor="middle" font-family="serif" font-size="6.5" fill="#e8c97a" font-weight="bold">RISE</text>
        <text x="35" y="89" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(232,201,122,.65)">VITAMINE D3+K2</text>
        <rect x="19" y="92" width="32" height="1" fill="rgba(232,201,122,.2)"/>
        <text x="35" y="102" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(232,201,122,.45)">SOURCE ALGUE</text>
        <text x="35" y="112" text-anchor="middle" font-family="sans-serif" font-size="3" fill="rgba(232,201,122,.3)">100% VÉGÉTALIEN</text>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Immunité · 90 gélules</div>
      <div class="prod-name">Vitamines D3 + K2 Vegan</div>
      <div class="prod-desc">Combo essentiel os, immunité et humeur. D3 source algue + K2 MK-7. 100% végétalien certifié.</div>
      <div class="prod-foot">
        <div class="prod-price">16.90€ <small>90 gélules · 3 mois</small></div>
        <button class="add-btn" onclick="addCart('D3 + K2')">+ Ajouter</button>
      </div>
    </div>
  </div>

  <div class="prod-card reveal">
    <div class="prod-visual v-comp">
      <span class="prod-badge new">Nouveau</span>
      <svg width="70" height="160" viewBox="0 0 70 160" xmlns="http://www.w3.org/2000/svg" style="animation:float 5.1s ease-in-out infinite 1.5s;">
        <defs>
          <linearGradient id="brainGrad" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stop-color="#1a2a1a"/>
            <stop offset="100%" stop-color="#0f180f"/>
          </linearGradient>
        </defs>
        <ellipse cx="35" cy="44" rx="22" ry="7" fill="#2a3a2a"/>
        <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#brainGrad)"/>
        <rect x="13" y="44" width="44" height="95" rx="10" fill="url(#shampShine)"/>
        <ellipse cx="35" cy="44" rx="22" ry="7" fill="#3a4a3a"/>
        <rect x="16" y="38" width="38" height="10" rx="5" fill="#4a5a4a"/>
        <rect x="16" y="60" width="38" height="62" rx="4" fill="rgba(255,255,255,.04)"/>
        <text x="35" y="78" text-anchor="middle" font-family="serif" font-size="6.5" fill="#a8d5a2" font-weight="bold">RISE</text>
        <text x="35" y="89" text-anchor="middle" font-family="sans-serif" font-size="4" fill="rgba(168,213,162,.65)">BRAIN BOOST</text>
        <rect x="19" y="92" width="32" height="1" fill="rgba(168,213,162,.15)"/>
        <text x="35" y="102" text-anchor="middle" font-family="sans-serif" font-size="3.5" fill="rgba(168,213,162,.45)">RHODIOLA · BACOPA</text>
        <text x="35" y="112" text-anchor="middle" font-family="sans-serif" font-size="3" fill="rgba(168,213,162,.3)">GINKGO · 60 GÉL.</text>
      </svg>
    </div>
    <div class="prod-body">
      <div class="prod-cat">Focus · 60 gélules</div>
      <div class="prod-name">Brain Boost Rhodiola</div>
      <div class="prod-desc">Adaptogènes naturels — rhodiola, bacopa monnieri, ginkgo biloba. Clarté mentale et concentration durable.</div>
      <div class="prod-foot">
        <div class="prod-price">27.90€ <small>60 gélules · 2 mois</small></div>
        <button class="add-btn" onclick="addCart('Brain Boost')">+ Ajouter</button>
      </div>
    </div>
  </div>
</div>
```

  </div>
</section>

<!-- ════════════════════ LANDSCAPE 2 — MOUNTAIN LAKE ════════════════════ -->

<div class="landscape-break" style="height:55vh;">
  <svg viewBox="0 0 1600 500" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient id="lkSky" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#05120a"/>
        <stop offset="50%" stop-color="#0f2a18"/>
        <stop offset="100%" stop-color="#162e1a"/>
      </linearGradient>
      <linearGradient id="lake" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#0a1e0a" stop-opacity=".9"/>
        <stop offset="100%" stop-color="#162e16" stop-opacity=".6"/>
      </linearGradient>
      <radialGradient id="moonRefl" cx="50%" cy="0%" r="80%">
        <stop offset="0%" stop-color="#c8a84b" stop-opacity=".12"/>
        <stop offset="100%" stop-color="#c8a84b" stop-opacity="0"/>
      </radialGradient>
    </defs>
    <!-- Sky -->
    <rect width="1600" height="500" fill="url(#lkSky)"/>
    <!-- Stars -->
    <g opacity=".5">
      <circle cx="100" cy="50" r="1" fill="#d4edd0"/>
      <circle cx="300" cy="30" r="1.2" fill="#d4edd0"/>
      <circle cx="600" cy="60" r="1" fill="#d4edd0"/>
      <circle cx="900" cy="25" r="1.2" fill="#d4edd0"/>
      <circle cx="1200" cy="45" r="1" fill="#d4edd0"/>
      <circle cx="1450" cy="35" r="1.2" fill="#d4edd0"/>
      <circle cx="200" cy="90" r="1" fill="#a8d5a2"/>
      <circle cx="750" cy="80" r="1" fill="#a8d5a2"/>
      <circle cx="1300" cy="70" r="1" fill="#a8d5a2"/>
    </g>
    <!-- Moon -->
    <circle cx="800" cy="80" r="22" fill="#e8c97a" opacity=".5"/>
    <ellipse cx="800" cy="80" rx="120" ry="120" fill="rgba(200,168,75,.08)"/>
    <!-- Far mountains -->
    <path d="M0,240 L200,100 L400,200 L600,80 L800,180 L1000,60 L1200,180 L1400,100 L1600,200 L1600,500 L0,500Z" fill="#0d1e0d"/>
    <!-- Mid mountains -->
    <path d="M0,300 L300,160 L500,260 L700,140 L900,260 L1100,140 L1300,240 L1500,160 L1600,220 L1600,500 L0,500Z" fill="#142814"/>
    <!-- Lakeside hills -->
    <path d="M0,360 Q200,320 400,360 Q600,400 800,350 Q1000,300 1200,360 Q1400,400 1600,360 L1600,500 L0,500Z" fill="#1a3a1a"/>
    <!-- Lake -->
    <rect x="0" y="380" width="1600" height="120" fill="url(#lake)"/>
    <!-- Moon reflection -->
    <ellipse cx="800" cy="380" rx="800" ry="60" fill="url(#moonRefl)"/>
    <!-- Reflection shimmer -->
    <g opacity=".15">
      <line x1="800" y1="380" x2="800" y2="500" stroke="#e8c97a" stroke-width="3"/>
      <line x1="790" y1="390" x2="810" y2="500" stroke="#e8c97a" stroke-width="1"/>
      <line x1="780" y1="400" x2="820" y2="500" stroke="#e8c97a" stroke-width=".5"/>
    </g>
    <!-- Tree reflections in lake -->
    <g opacity=".25" transform="scale(1,-1) translate(0,-760)">
      <polygon points="0,500 30,400 60,500" fill="#0d1a0d"/>
      <polygon points="80,500 110,380 140,500" fill="#0d1a0d"/>
      <polygon points="1460,500 1490,390 1520,500" fill="#0d1a0d"/>
      <polygon points="1540,500 1570,410 1600,500" fill="#0d1a0d"/>
    </g>
    <!-- Trees -->
    <g fill="#0d1a0d">
      <polygon points="0,380 25,280 50,380"/>
      <polygon points="40,380 70,260 100,380"/>
      <polygon points="90,380 120,290 150,380"/>
      <polygon points="1460,380 1490,270 1520,380"/>
      <polygon points="1510,380 1540,260 1570,380"/>
      <polygon points="1555,380 1580,285 1605,380"/>
    </g>
    <!-- Mist over lake -->
    <ellipse cx="800" cy="385" rx="900" ry="18" fill="#a8d5a2" opacity=".05"/>
  </svg>
  <div class="landscape-overlay"></div>
  <div class="landscape-caption">
    <h3>La nature comme source d'énergie</h3>
  </div>
</div>

<!-- ════════════════════ ROUTINE ════════════════════ -->

<section id="routine">
  <div class="routine-bg"></div>
  <div class="routine-grid">
    <div class="routine-left reveal-left">
      <div class="section-label">Discipline quotidienne</div>
      <h2>La routine<em>qui change</em>tout</h2>
      <p>La discipline, c'est pas se priver. C'est se respecter assez pour faire les choses qui comptent, même quand t'as pas envie. Voici la routine RISE UP — testée, affinée, transformatrice.</p>
      <a href="#cta" class="btn-forest" style="display:inline-flex;align-items:center;gap:12px;">
        Guide PDF gratuit
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
      </a>
    </div>
    <div class="routine-right reveal-right">
      <div class="timeline">
        <div class="t-item">
          <div class="t-left">
            <div class="t-time">5H30</div>
            <div class="t-dot"></div>
            <div class="t-line"></div>
          </div>
          <div class="t-content">
            <div class="t-title">🌅 Réveil intentionnel</div>
            <div class="t-desc">Verre d'eau citronné, 5 min de respiration consciente (4-7-8). Ton corps et ton mental démarrent ensemble.</div>
          </div>
        </div>
        <div class="t-item">
          <div class="t-left">
            <div class="t-time">6H00</div>
            <div class="t-dot"></div>
            <div class="t-line"></div>
          </div>
          <div class="t-content">
            <div class="t-title">💪 Mouvement</div>
            <div class="t-desc">30 min — course, musculation, yoga, peu importe. Le mouvement matinal libère les endorphines et programme ta journée pour la victoire.</div>
          </div>
        </div>
        <div class="t-item">
          <div class="t-left">
            <div class="t-time">6H45</div>
            <div class="t-dot"></div>
            <div class="t-line"></div>
          </div>
          <div class="t-content">
            <div class="t-title">🧴 Rituel soins RISE UP</div>
            <div class="t-desc">Shampoing frais, gel nettoyant, huile corps. Prendre soin de toi, c'est un acte de discipline et de respect envers toi-même.</div>
          </div>
        </div>
        <div class="t-item">
          <div class="t-left">
            <div class="t-time">7H15</div>
            <div class="t-dot"></div>
            <div class="t-line"></div>
          </div>
          <div class="t-content">
            <div class="t-title">🥤 Nutrition végétale</div>
            <div class="t-desc">Shake protéiné végétal + petit-déjeuner équilibré. Nourris ton corps pour la journée qui t'attend — sans compromis.</div>
          </div>
        </div>
        <div class="t-item">
          <div class="t-left">
            <div class="t-time">7H30</div>
            <div class="t-dot"></div>
            <div class="t-line"></div>
          </div>
          <div class="t-content">
            <div class="t-title">📖 Intention du jour</div>
            <div class="t-desc">3 objectifs concrets écrits à la main. Une chose pour laquelle tu es reconnaissant. Tu pars conquérir ta journée.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════════════ QUOTES ════════════════════ -->

<section id="quotes">
  <div class="quote-wrap reveal">
    <div class="section-label" style="justify-content:center;margin-bottom:48px;">Ils se sont levés</div>
    <div class="q-text" id="qt">"La discipline est le pont entre les objectifs et les accomplissements."</div>
    <div class="q-author" id="qa">— Jim Rohn</div>
    <div class="q-dots">
      <div class="q-dot on" onclick="sq(0)"></div>
      <div class="q-dot" onclick="sq(1)"></div>
      <div class="q-dot" onclick="sq(2)"></div>
      <div class="q-dot" onclick="sq(3)"></div>
    </div>
  </div>
</section>

<!-- ════════════════════ CTA / NEWSLETTER ════════════════════ -->

<section id="cta" style="position:relative;overflow:hidden;">
  <!-- SVG aurora bg -->
  <svg style="position:absolute;inset:0;width:100%;height:100%;pointer-events:none;" viewBox="0 0 1600 600" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <radialGradient id="aur1" cx="30%" cy="50%" r="60%">
        <stop offset="0%" stop-color="#2d6a4f" stop-opacity=".2"/>
        <stop offset="100%" stop-color="#2d6a4f" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="aur2" cx="70%" cy="50%" r="60%">
        <stop offset="0%" stop-color="#c8a84b" stop-opacity=".08"/>
        <stop offset="100%" stop-color="#c8a84b" stop-opacity="0"/>
      </radialGradient>
    </defs>
    <rect width="1600" height="600" fill="url(#aur1)"/>
    <rect width="1600" height="600" fill="url(#aur2)"/>
    <!-- Subtle grid -->
    <g opacity=".04" stroke="#a8d5a2" stroke-width=".5">
      <line x1="0" y1="100" x2="1600" y2="100"/>
      <line x1="0" y1="200" x2="1600" y2="200"/>
      <line x1="0" y1="300" x2="1600" y2="300"/>
      <line x1="0" y1="400" x2="1600" y2="400"/>
      <line x1="0" y1="500" x2="1600" y2="500"/>
      <line x1="200" y1="0" x2="200" y2="600"/>
      <line x1="400" y1="0" x2="400" y2="600"/>
      <line x1="600" y1="0" x2="600" y2="600"/>
      <line x1="800" y1="0" x2="800" y2="600"/>
      <line x1="1000" y1="0" x2="1000" y2="600"/>
      <line x1="1200" y1="0" x2="1200" y2="600"/>
      <line x1="1400" y1="0" x2="1400" y2="600"/>
    </g>
  </svg>
  <div class="cta-inner reveal">
    <div class="section-label" style="justify-content:center;margin-bottom:24px;">Rejoins le mouvement</div>
    <h2>Prêt à<em>te lever ?</em></h2>
    <p>Guide de routine matinale offert + 10% sur ta première commande. Des milliers de jeunes belges t'attendent dans la communauté RISE UP.</p>
    <div class="cta-form">
      <input type="email" class="cta-input" placeholder="ton@email.com" id="emailIn">
      <button class="btn-forest" onclick="sub()" style="white-space:nowrap;">Je rejoins ✦</button>
    </div>
    <p style="font-size:.7rem;color:rgba(247,242,232,.25);margin-top:20px;letter-spacing:1px;">Sans spam. Désabonnement en 1 clic. Données protégées RGPD.</p>
  </div>
</section>

<!-- ════════════════════ FOOTER ════════════════════ -->

<footer>
  <div class="footer-top">
    <div class="f-brand">
      <span class="f-logo">RISE UP</span>
      <p>La première marque belge de bien-être naturel pour la jeunesse. Discipline, nature, communauté.</p>
    </div>
    <div class="f-col">
      <h4>Produits</h4>
      <ul>
        <li><a href="#products">Soins Capillaires</a></li>
        <li><a href="#products">Protéines Végétales</a></li>
        <li><a href="#products">Compléments</a></li>
        <li><a href="#products">Packs Découverte</a></li>
      </ul>
    </div>
    <div class="f-col">
      <h4>La Marque</h4>
      <ul>
        <li><a href="#mission">Notre Mission</a></li>
        <li><a href="#pillars">Nos Valeurs</a></li>
        <li><a href="#routine">Routine RISE</a></li>
        <li><a href="#cta">Communauté</a></li>
      </ul>
    </div>
    <div class="f-col">
      <h4>Support</h4>
      <ul>
        <li><a href="#">FAQ</a></li>
        <li><a href="#">Livraisons Belgique</a></li>
        <li><a href="#">Retours</a></li>
        <li><a href="#">Contact</a></li>
        <li><a href="#">Mentions Légales</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2025 RISE UP Belgium · Tous droits réservés · Fait avec 🌿 pour nos jeunes</p>
    <div class="socials">
      <a href="#" class="soc">▶</a>
      <a href="#" class="soc">📷</a>
      <a href="#" class="soc">🎵</a>
      <a href="#" class="soc">in</a>
    </div>
  </div>
</footer>

<script>
/* ── CURSOR ── */
const c1=document.getElementById('cur'),c2=document.getElementById('cur2');
let mx=0,my=0,tx=0,ty=0;
document.addEventListener('mousemove',e=>{
  mx=e.clientX;my=e.clientY;
  c1.style.cssText=`left:${mx-5}px;top:${my-5}px;`;
});
setInterval(()=>{
  tx+=(mx-tx)*.12;ty+=(my-ty)*.12;
  c2.style.cssText=`left:${tx-18}px;top:${ty-18}px;`;
},14);

/* ── NAV STICKY ── */
const nav=document.getElementById('nav');
window.addEventListener('scroll',()=>nav.classList.toggle('stuck',scrollY>60));

/* ── REVEAL OBSERVER ── */
const obs=new IntersectionObserver(entries=>{
  entries.forEach((e,i)=>{
    if(e.isIntersecting)setTimeout(()=>e.target.classList.add('on'),i*90);
  });
},{threshold:.1});
document.querySelectorAll('.reveal,.reveal-left,.reveal-right').forEach(el=>obs.observe(el));

/* ── PRODUCT TABS ── */
function switchTab(btn,id){
  document.querySelectorAll('.tab').forEach(b=>b.classList.remove('on'));
  document.querySelectorAll('.tab-content').forEach(p=>p.classList.remove('on'));
  btn.classList.add('on');
  document.getElementById(id).classList.add('on');
  document.querySelectorAll('#'+id+' .reveal').forEach(el=>{
    el.classList.remove('on');
    setTimeout(()=>el.classList.add('on'),120);
  });
}
// Init soin tab reveals
setTimeout(()=>{document.querySelectorAll('#t-soin .reveal').forEach(el=>el.classList.add('on'));},400);

/* ── TOAST ── */
const toast=document.getElementById('toast'),toastMsg=document.getElementById('toastMsg');
function showToast(m){
  toastMsg.textContent=m;
  toast.classList.add('show');
  setTimeout(()=>toast.classList.remove('show'),3200);
}
function addCart(n){showToast('✦ '+n+' ajouté au panier !');}

/* ── NEWSLETTER ── */
function sub(){
  const v=document.getElementById('emailIn').value;
  if(!v||!v.includes('@')){showToast('Entre un email valide 🙏');return;}
  document.getElementById('emailIn').value='';
  showToast('🌿 Bienvenue dans le mouvement RISE UP !');
}

/* ── QUOTES ── */
const qs=[
  {t:'"La discipline est le pont entre les objectifs et les accomplissements."',a:'— Jim Rohn'},
  {t:'"Tu n\'as pas à être parfait. Tu as juste à te lever chaque matin et décider de te battre."',a:'— Rise Up'},
  {t:'"Le succès, c\'est la somme de petits efforts répétés chaque jour."',a:'— Robert Collier'},
  {t:'"Prends soin de ton corps. C\'est le seul endroit où tu sois obligé de vivre."',a:'— Jim Rohn'},
];
let qi=0;
function sq(i){
  qi=i;
  const qt=document.getElementById('qt'),qa=document.getElementById('qa');
  qt.style.opacity=qa.style.opacity='0';
  setTimeout(()=>{
    qt.textContent='"'+qs[i].t.replace(/"/g,'')+'"';
    qa.textContent=qs[i].a;
    qt.style.opacity=qa.style.opacity='1';
  },350);
  document.querySelectorAll('.q-dot').forEach((d,j)=>d.classList.toggle('on',j===i));
}
document.getElementById('qt').style.transition=document.getElementById('qa').style.transition='opacity .4s';
setInterval(()=>sq((qi+1)%qs.length),5500);
</script>

</body>
</html>