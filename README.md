[index.html.html](https://github.com/user-attachments/files/28905392/index.html.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dr. José Rafael Alves Toledo — Advogado OAB/DF 71.232</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'Inter', sans-serif;
      background: #050816;
      color: #F5F7FB;
      min-height: 100vh;
      overflow-x: hidden;
    }
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: -2; pointer-events: none;
      background:
        radial-gradient(900px 420px at 72% 18%, rgba(255,120,180,.14) 0%, transparent 42%),
        radial-gradient(800px 380px at 35% 20%, rgba(35,110,255,.14) 0%, transparent 42%),
        linear-gradient(180deg, #0A0F24 0%, #070B1D 45%, #050816 100%);
    }
    body::after {
      content: '';
      position: fixed; inset: 0; z-index: -1; pointer-events: none; opacity: .25;
      background-image: radial-gradient(rgba(255,255,255,.06) .8px, transparent .8px);
      background-size: 24px 24px;
    }

    .progress {
      position: fixed; top: 0; left: 0;
      height: 3px; width: 0; z-index: 1000;
      background: linear-gradient(90deg, #2E6BFF, #C86DD7, #2E6BFF);
      background-size: 200% auto;
      animation: shimmer 3s linear infinite;
      transition: width .15s ease;
    }

    /* ── TOC ── */
    .toc {
      position: fixed; left: 0; top: 0; bottom: 0; width: 248px;
      padding: 24px 20px 24px;
      background: rgba(5,8,22,.8);
      backdrop-filter: blur(18px);
      border-right: 1px solid rgba(255,255,255,.05);
      z-index: 100;
      display: flex; flex-direction: column;
      overflow-y: auto; overflow-x: hidden;
      scrollbar-width: thin;
      scrollbar-color: rgba(255,255,255,.08) transparent;
    }
    .toc::-webkit-scrollbar { width: 3px; }
    .toc::-webkit-scrollbar-thumb { background: rgba(255,255,255,.1); border-radius: 2px; }

    .toc-logo-wrap {
      width: 100%;
      display: flex; align-items: center; justify-content: center;
      margin-bottom: 20px;
      padding-bottom: 18px;
      border-bottom: 1px solid rgba(255,255,255,.06);
    }
    .toc-logo-wrap img {
      width: 160px; height: auto; object-fit: contain;
      filter: drop-shadow(0 0 10px rgba(46,107,255,.3)) brightness(1.06);
      transition: filter .4s ease, transform .4s ease;
    }
    .toc-logo-wrap:hover img {
      filter: drop-shadow(0 0 20px rgba(46,107,255,.5)) brightness(1.14);
      transform: scale(1.04);
    }
    .toc-oab {
      font-size: 10px; font-weight: 700; color: #5B3FD6;
      letter-spacing: .12em; text-transform: uppercase;
      text-align: center; margin-bottom: 20px;
    }
    .toc nav { flex: 1; }
    .toc ul { list-style: none; }
    .toc li { margin-bottom: 3px; }
    .toc a {
      display: flex; align-items: center; gap: 10px;
      padding: 9px 14px; border-radius: 11px;
      color: #7E879B; font-size: 13px; font-weight: 500; text-decoration: none;
      transition: all .3s ease; border-left: 2px solid transparent;
    }
    .toc a .nav-ico { font-size: 14px; flex-shrink: 0; opacity: .6; transition: opacity .3s; }
    .toc a:hover { color: #F5F7FB; background: rgba(255,255,255,.04); transform: translateX(3px); }
    .toc a:hover .nav-ico { opacity: 1; }
    .toc a.active { color: #8FAEFF; background: rgba(46,107,255,.1); border-left-color: #2E6BFF; font-weight: 600; }
    .toc a.active .nav-ico { opacity: 1; }

    /* ── CONTENT ── */
    .content {
      margin-left: calc(248px + max(0px, (100vw - 248px - 1080px) / 2));
      margin-right: auto;
      padding: 72px 60px 120px;
      max-width: 1080px;
    }
    @media (min-width: 1600px) {
      .content { max-width: 1200px; margin-left: calc(248px + max(0px, (100vw - 248px - 1200px) / 2)); }
    }
    section { margin-bottom: 96px; scroll-margin-top: 36px; }
    section > h2 { font-size: clamp(32px, 4.2vw, 50px); font-weight: 800; letter-spacing: -.025em; margin-bottom: 30px; line-height: 1.12; }

    /* ── UTILS ── */
    .gt {
      background: linear-gradient(135deg, #2E6BFF 0%, #C86DD7 50%, #2E6BFF 100%);
      background-size: 200% auto;
      -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
      animation: shimmer 4s linear infinite;
    }
    @keyframes shimmer { 0% { background-position: -200% center } 100% { background-position: 200% center } }
    .gl { width: 68px; height: 4px; border-radius: 2px; background: linear-gradient(90deg, #2E6BFF, #C86DD7); margin-bottom: 18px; transform-origin: left; }

    /* ── HERO ── */
    #hero {
      min-height: 95vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      gap: 60px;
      padding: 60px 0;
    }
    .hero-left { display: flex; flex-direction: column; justify-content: center; }
    .hero-right { display: flex; flex-direction: column; align-items: center; justify-content: center; }

    /* LOGO ACIMA DO TÍTULO */
    .hero-logo-top {
      display: flex; align-items: center; justify-content: flex-start;
      margin-bottom: 18px;
    }
    .hero-logo-top img {
      width: 200px; height: auto; object-fit: contain;
      filter: drop-shadow(0 0 14px rgba(46,107,255,.4)) brightness(1.1);
      transition: filter .5s ease, transform .5s cubic-bezier(.22,1,.36,1);
    }
    .hero-logo-top img:hover {
      filter: drop-shadow(0 0 26px rgba(46,107,255,.6)) brightness(1.18);
      transform: scale(1.05);
    }

    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 7px 18px; border-radius: 999px;
      background: rgba(91,63,214,.12); border: 1px solid rgba(91,63,214,.3);
      font-size: 12px; font-weight: 700; color: #A98BFF;
      letter-spacing: .07em; text-transform: uppercase;
      margin-bottom: 16px; width: fit-content;
    }
    #hero h1 {
      font-size: clamp(38px, 5vw, 68px); font-weight: 900;
      letter-spacing: -.03em; line-height: 1.06; margin-bottom: 14px;
    }
    .hero-role { font-size: clamp(15px, 1.8vw, 20px); color: #AAB3C5; font-weight: 500; margin-bottom: 16px; }
    .hero-tagline {
      font-size: clamp(13px, 1.3vw, 16px); color: #7E879B;
      max-width: 500px; line-height: 1.75; margin-bottom: 26px;
    }
    .hero-loc {
      display: inline-flex; align-items: center; gap: 6px;
      font-size: 13px; color: #7E879B; letter-spacing: .04em;
    }

    /* STATS HERO */
    .hero-stats { display: flex; gap: 28px; margin-top: 34px; flex-wrap: wrap; }
    .h-stat { cursor: default; }
    .h-stat .hs-val {
      font-size: 40px; font-weight: 900; letter-spacing: -.03em; line-height: 1;
      margin-bottom: 6px; display: block; transition: transform .4s cubic-bezier(.22,1,.36,1);
    }
    .h-stat:hover .hs-val { transform: scale(1.1) translateY(-2px); }
    .hs-val.blue { color: #2E6BFF; }
    .hs-val.purple { color: #5B3FD6; }
    .hs-val.pink { color: #C86DD7; }
    .hs-val.green { color: #5EE89A; }
    .h-stat .hs-lbl { font-size: 11px; color: #7E879B; letter-spacing: .07em; text-transform: uppercase; font-weight: 600; }

    /* FOTO HERO */
    .photo-hero-wrap {
      position: relative;
      width: 100%; max-width: 400px;
    }

    /* Card OAB flutuante */
    .oab-float {
      position: absolute; bottom: 28px; left: -22px; z-index: 10;
      padding: 12px 18px; border-radius: 16px;
      background: rgba(10,15,36,.92); border: 1px solid rgba(91,63,214,.28);
      backdrop-filter: blur(14px);
      box-shadow: 0 16px 40px rgba(0,0,0,.45);
      transition: transform .4s ease;
    }
    .oab-float:hover { transform: translateY(-3px); }
    .oab-float .oab-num { font-size: 17px; font-weight: 900; color: #A98BFF; letter-spacing: -.01em; }
    .oab-float .oab-lbl { font-size: 10px; color: #7E879B; letter-spacing: .09em; text-transform: uppercase; font-weight: 600; margin-top: 2px; }

    /* FOTO PRINCIPAL */
    .photo-main {
      width: 100%; border-radius: 26px; overflow: hidden; position: relative;
      box-shadow: 0 30px 80px rgba(0,0,0,.6), 0 0 60px rgba(46,107,255,.14);
      border: 1px solid rgba(255,255,255,.07);
    }
    .photo-main img {
      width: 100%; height: 100%; object-fit: cover; object-position: center top;
      display: block;
      filter: url(#duotone) contrast(1.04) brightness(1.03) saturate(1.1);
      transition: filter .7s ease, transform .7s cubic-bezier(.22,1,.36,1);
    }
    .photo-main:hover img { filter: contrast(1.05) brightness(1.05) saturate(1.12); transform: scale(1.03); }
    .photo-main::after {
      content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 40%;
      background: linear-gradient(to top, rgba(5,8,22,.65), transparent);
      pointer-events: none;
    }

    /* ── CARDS ── */
    .card {
      background: rgba(255,255,255,.03); border: 1px solid rgba(255,255,255,.07);
      border-radius: 22px; box-shadow: 0 14px 44px rgba(0,0,0,.4), inset 0 1px 0 rgba(255,255,255,.04);
      padding: 30px 26px; backdrop-filter: blur(8px);
      transition: transform .5s cubic-bezier(.22,1,.36,1), border-color .4s, box-shadow .4s, background .4s;
      position: relative; overflow: hidden;
    }
    .card::before {
      content: ''; position: absolute; inset: 0; border-radius: 22px; padding: 1px;
      background: linear-gradient(135deg, transparent 40%, rgba(46,107,255,.4), rgba(200,109,215,.35), transparent 60%);
      -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
      -webkit-mask-composite: xor; mask-composite: exclude;
      opacity: 0; transition: opacity .5s; pointer-events: none;
    }
    .card:hover { border-color: rgba(46,107,255,.22); transform: translateY(-6px) scale(1.01); box-shadow: 0 30px 68px rgba(0,0,0,.55), 0 0 38px rgba(46,107,255,.1); background: rgba(255,255,255,.042); }
    .card:hover::before { opacity: 1; }

    .cp {
      background: linear-gradient(145deg, rgba(18,11,43,.95), rgba(10,15,36,.98) 55%, rgba(5,8,22,1));
      border: 1px solid rgba(255,255,255,.08); border-radius: 22px;
      box-shadow: 0 18px 48px rgba(0,0,0,.45), 0 0 36px rgba(46,107,255,.07);
      padding: 32px 28px; backdrop-filter: blur(10px);
      transition: transform .5s cubic-bezier(.22,1,.36,1), border-color .4s, box-shadow .4s;
      position: relative; overflow: hidden;
    }
    .cp::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(600px circle at var(--mx,50%) var(--my,50%), rgba(46,107,255,.09), transparent 40%);
      opacity: 0; transition: opacity .5s; pointer-events: none;
    }
    .cp:hover { border-color: rgba(46,107,255,.28); transform: translateY(-6px) scale(1.015); box-shadow: 0 34px 78px rgba(0,0,0,.6), 0 0 56px rgba(46,107,255,.16); }
    .cp:hover::before { opacity: 1; }

    /* ── SUPERPODERES ── */
    .sp-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 16px; }
    .sp-card { padding: 26px 22px; }
    .sp-card .sp-ic {
      width: 46px; height: 46px; border-radius: 13px; background: rgba(46,107,255,.1);
      display: flex; align-items: center; justify-content: center; margin-bottom: 14px;
      transition: transform .5s cubic-bezier(.22,1,.36,1), box-shadow .4s, background .4s;
    }
    .sp-card .sp-ic svg { width: 22px; height: 22px; color: #2E6BFF; transition: transform .4s; }
    .sp-card:hover .sp-ic { transform: rotate(-8deg) scale(1.1); box-shadow: 0 10px 28px rgba(46,107,255,.25); background: rgba(46,107,255,.18); }
    .sp-card:hover .sp-ic svg { transform: scale(1.1); }
    .sp-card h3 { font-size: 16px; margin-bottom: 8px; font-weight: 700; transition: color .3s; letter-spacing: -.01em; color: #F5F7FB; }
    .sp-card:hover h3 { background: linear-gradient(135deg, #2E6BFF, #C86DD7); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
    .sp-card p { font-size: 13px; color: #AAB3C5; line-height: 1.65; }
    .sp-card:nth-child(2) .sp-ic { background: rgba(91,63,214,.1); } .sp-card:nth-child(2) .sp-ic svg { color: #5B3FD6; }
    .sp-card:nth-child(2):hover .sp-ic { background: rgba(91,63,214,.18); box-shadow: 0 10px 28px rgba(91,63,214,.25); }
    .sp-card:nth-child(3) .sp-ic { background: rgba(200,109,215,.1); } .sp-card:nth-child(3) .sp-ic svg { color: #C86DD7; }
    .sp-card:nth-child(3):hover .sp-ic { background: rgba(200,109,215,.18); box-shadow: 0 10px 28px rgba(200,109,215,.25); }
    .sp-card:nth-child(4) .sp-ic { background: rgba(94,232,154,.1); } .sp-card:nth-child(4) .sp-ic svg { color: #5EE89A; }
    .sp-card:nth-child(4):hover .sp-ic { background: rgba(94,232,154,.18); box-shadow: 0 10px 28px rgba(94,232,154,.2); }
    .sp-card:nth-child(5) .sp-ic { background: rgba(255,212,96,.1); } .sp-card:nth-child(5) .sp-ic svg { color: #FFD460; }
    .sp-card:nth-child(5):hover .sp-ic { background: rgba(255,212,96,.18); box-shadow: 0 10px 28px rgba(255,212,96,.18); }

    /* ── TIMELINE ── */
    .tl { position: relative; padding-left: 38px; }
    .tl::before { content: ''; position: absolute; left: 11px; top: 0; bottom: 0; width: 2px; background: linear-gradient(180deg, #2E6BFF 0%, #5B3FD6 50%, #C86DD7 100%); opacity: .3; }
    .tl-item { position: relative; margin-bottom: 42px; }
    .tl-item::before { content: ''; position: absolute; left: -33px; top: 8px; width: 14px; height: 14px; border-radius: 50%; background: #2E6BFF; box-shadow: 0 0 14px rgba(46,107,255,.6), 0 0 0 4px rgba(5,8,22,1); }
    .tl-period { font-size: 11px; font-weight: 700; color: #7E879B; letter-spacing: .09em; text-transform: uppercase; margin-bottom: 5px; }
    .tl-role { font-size: 20px; font-weight: 700; color: #F5F7FB; margin-bottom: 3px; letter-spacing: -.01em; }
    .tl-company { font-size: 14px; color: #8FAEFF; font-weight: 600; margin-bottom: 13px; }
    .tl-item ul { list-style: none; margin-top: 8px; }
    .tl-item ul li { position: relative; padding-left: 17px; margin-bottom: 9px; color: #AAB3C5; font-size: 14px; line-height: 1.65; }
    .tl-item ul li::before { content: ''; position: absolute; left: 0; top: 9px; width: 6px; height: 6px; border-radius: 50%; background: rgba(200,109,215,.6); }

    /* ── CASES ── */
    .cases-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 16px; }
    .case-card { padding: 30px 26px; display: flex; flex-direction: column; gap: 12px; }
    .case-metric {
      font-size: 50px; font-weight: 900; letter-spacing: -.03em; line-height: 1;
      background: linear-gradient(135deg, #2E6BFF, #C86DD7, #2E6BFF); background-size: 200% auto;
      -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
      display: inline-block; transition: background-position .8s, transform .4s cubic-bezier(.22,1,.36,1);
    }
    .case-card:hover .case-metric { background-position: 200% center; transform: scale(1.05); }
    .case-title { font-size: 17px; font-weight: 700; color: #F5F7FB; letter-spacing: -.01em; }
    .case-ctx { font-size: 13px; color: #AAB3C5; line-height: 1.6; }

    /* ── ÁREAS ── */
    .areas-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(168px, 1fr)); gap: 13px; }
    .area-tile {
      padding: 22px 16px; border-radius: 16px;
      background: rgba(255,255,255,.03); border: 1px solid rgba(255,255,255,.08); text-align: center;
      transition: transform .4s cubic-bezier(.22,1,.36,1), border-color .3s, background .3s, box-shadow .3s; cursor: default;
    }
    .area-tile:hover { border-color: rgba(46,107,255,.38); background: rgba(46,107,255,.07); transform: translateY(-5px); box-shadow: 0 14px 34px rgba(46,107,255,.14); }
    .area-icon { font-size: 26px; margin-bottom: 10px; display: block; }
    .area-name { font-size: 13px; font-weight: 700; color: #F5F7FB; margin-bottom: 5px; transition: color .3s; }
    .area-tile:hover .area-name { color: #8FAEFF; }
    .area-sub { font-size: 11px; color: #7E879B; line-height: 1.55; }

    /* ── COMPETÊNCIAS ── */
    .comp-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 11px; }
    .comp-item {
      display: flex; align-items: center; gap: 13px;
      padding: 14px 18px; border-radius: 13px;
      background: rgba(255,255,255,.03); border: 1px solid rgba(255,255,255,.07);
      transition: all .35s ease;
    }
    .comp-item:hover { border-color: rgba(46,107,255,.28); background: rgba(46,107,255,.06); transform: translateX(4px); }
    .ci-dot { width: 7px; height: 7px; border-radius: 50%; background: linear-gradient(135deg, #2E6BFF, #C86DD7); flex-shrink: 0; }
    .comp-item span { font-size: 13px; color: #AAB3C5; font-weight: 500; }

    /* ── DIFERENCIAIS ── */
    .dif-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 13px; }
    .dif-item {
      display: flex; align-items: flex-start; gap: 13px;
      padding: 17px 20px; border-radius: 14px;
      background: rgba(255,255,255,.03); border: 1px solid rgba(255,255,255,.07);
      transition: all .35s ease;
    }
    .dif-item:hover { border-color: rgba(200,109,215,.28); background: rgba(200,109,215,.04); transform: translateY(-3px); }
    .di-ic { font-size: 20px; flex-shrink: 0; margin-top: 1px; }
    .dif-item p { font-size: 13px; color: #AAB3C5; line-height: 1.65; }

    /* ── PILL ── */
    .pill {
      display: inline-flex; align-items: center;
      padding: 5px 13px; border-radius: 999px;
      background: rgba(255,255,255,.04); border: 1px solid rgba(255,255,255,.08);
      color: #AAB3C5; font-size: 12px; font-weight: 500;
      margin: 3px 5px 3px 0; transition: all .3s;
    }
    .pill:hover { background: rgba(46,107,255,.1); border-color: rgba(46,107,255,.3); color: #F5F7FB; }
    .pill.highlight { background: rgba(46,107,255,.1); border-color: rgba(46,107,255,.3); color: #8FAEFF; }

    /* ── OBJETIVO ── */
    .obj-banner {
      padding: 36px 40px; border-radius: 22px;
      background: linear-gradient(135deg, rgba(46,107,255,.07), rgba(91,63,214,.07), rgba(200,109,215,.05));
      border: 1px solid rgba(46,107,255,.14); position: relative; overflow: hidden;
    }
    .obj-banner::before {
      content: '"'; position: absolute; top: -30px; right: 20px;
      font-size: 160px; font-weight: 900; line-height: 1;
      background: linear-gradient(135deg, rgba(46,107,255,.15), rgba(200,109,215,.12));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
      pointer-events: none;
    }
    .obj-banner p { font-size: 16px; color: #C8D0E0; line-height: 1.8; font-style: italic; position: relative; z-index: 1; }

    /* ── CONTATO ── */
    .contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 13px; }
    .contact-card {
      padding: 19px 22px; display: flex; align-items: center; gap: 15px;
      transition: transform .5s cubic-bezier(.22,1,.36,1), border-color .4s, box-shadow .4s, background .4s;
      min-width: 0;
    }
    .contact-card:hover { border-color: rgba(46,107,255,.38); transform: translateY(-4px) scale(1.02); box-shadow: 0 14px 38px rgba(46,107,255,.14); background: rgba(46,107,255,.04); }
    .ct-ic {
      width: 42px; height: 42px; border-radius: 12px; background: rgba(46,107,255,.1);
      display: flex; align-items: center; justify-content: center; flex-shrink: 0;
      transition: transform .4s cubic-bezier(.22,1,.36,1), background .3s;
    }
    .contact-card:hover .ct-ic { background: rgba(46,107,255,.2); transform: rotate(-6deg) scale(1.08); }
    .ct-ic svg { width: 19px; height: 19px; color: #8FAEFF; }
    .ct-info { min-width: 0; flex: 1; }
    .ct-lbl { font-size: 10px; color: #7E879B; letter-spacing: .1em; text-transform: uppercase; font-weight: 700; margin-bottom: 4px; }
    .ct-val { font-size: 13px; color: #F5F7FB; font-weight: 600; overflow-wrap: anywhere; line-height: 1.4; }
    .ct-val a { color: #F5F7FB; text-decoration: none; overflow-wrap: anywhere; }
    .ct-val a:hover { color: #8FAEFF; }

    /* ── FORMAÇÃO ── */
    .edu-card { display: flex; align-items: flex-start; gap: 20px; padding: 28px 26px; border-radius: 20px; margin-bottom: 14px; }
    .edu-icon { width: 50px; height: 50px; border-radius: 14px; background: rgba(46,107,255,.1); display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
    .edu-icon svg { width: 24px; height: 24px; color: #2E6BFF; }
    .edu-period { font-size: 11px; font-weight: 700; color: #7E879B; letter-spacing: .09em; text-transform: uppercase; margin-bottom: 5px; }
    .edu-degree { font-size: 20px; font-weight: 700; color: #F5F7FB; margin-bottom: 4px; letter-spacing: -.01em; }
    .edu-inst { font-size: 14px; color: #8FAEFF; font-weight: 600; margin-bottom: 8px; }
    .edu-note { font-size: 13px; color: #7E879B; }

    /* ── FLOATS ── */
    .fs-btn, .print-btn {
      position: fixed; z-index: 999;
      background: rgba(255,255,255,.04); border: 1px solid rgba(255,255,255,.08);
      color: #7E879B; padding: 11px 16px; border-radius: 12px; cursor: pointer;
      font-family: 'Inter', sans-serif; font-size: 11px; font-weight: 600;
      display: flex; align-items: center; gap: 7px;
      transition: all .3s; backdrop-filter: blur(8px);
      letter-spacing: .05em; text-transform: uppercase;
    }
    .fs-btn { top: 18px; right: 18px; }
    .print-btn { top: 18px; right: 144px; }
    .fs-btn:hover, .print-btn:hover { background: rgba(255,255,255,.08); color: #F5F7FB; border-color: rgba(46,107,255,.3); }
    .fs-btn svg, .print-btn svg { width: 15px; height: 15px; }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp { from { opacity:0; transform:translateY(32px) } to { opacity:1; transform:translateY(0) } }
    @keyframes fadeScale { from { opacity:0; transform:scale(.93) } to { opacity:1; transform:scale(1) } }
    .au { opacity:0; animation:fadeUp .8s ease both; animation-play-state:paused; }
    .as { opacity:0; animation:fadeScale .8s ease both; animation-play-state:paused; }
    .au.in-view, .as.in-view { animation-play-state:running; }
    .d1{animation-delay:.08s}.d2{animation-delay:.18s}.d3{animation-delay:.28s}
    .d4{animation-delay:.38s}.d5{animation-delay:.48s}.d6{animation-delay:.58s}.d7{animation-delay:.68s}

    /* ── RESPONSIVE ── */
    @media (max-width: 1060px) {
      #hero { grid-template-columns: 1fr; gap: 44px; min-height: auto; padding: 40px 0 60px; }
      .hero-right { order: -1; }
      .photo-hero-wrap { max-width: 300px; margin: 0 auto; }
      .oab-float { left: -10px; }
      .hero-logo-top { justify-content: center; }
      #hero h1 { text-align: center; }
      .hero-role, .hero-tagline { text-align: center; margin-left: auto; margin-right: auto; }
      .hero-badge { margin: 0 auto 16px; }
      .hero-loc { margin: 0 auto; }
      .hero-stats { justify-content: center; }
    }
    @media (max-width: 900px) {
      .toc {
        position: sticky; top: 0; width: 100%; height: auto; flex-direction: row;
        padding: 12px 18px; overflow-x: auto; overflow-y: hidden;
        border-right: none; border-bottom: 1px solid rgba(255,255,255,.05); gap: 12px;
      }
      .toc-logo-wrap { width: auto; margin-bottom: 0; padding: 0; border-bottom: none; }
      .toc-logo-wrap img { width: 90px; }
      .toc .toc-oab { display: none; }
      .toc nav { flex: none; }
      .toc ul { display: flex; gap: 3px; }
      .toc li { margin: 0; }
      .toc a { padding: 7px 11px; }
      .toc a .nav-ico { display: none; }
      .content { margin-left: 0; margin-right: 0; padding: 34px 20px 80px; max-width: 100%; }
      .fs-btn { top: auto; bottom: 18px; right: 18px; }
      .print-btn { top: auto; bottom: 18px; right: 128px; }
    }
    @media print {
      body::before, body::after { display: none; }
      .toc, .fs-btn, .print-btn, .progress { display: none; }
      .content { margin-left: 0; padding: 20px; max-width: 100%; }
      section { margin-bottom: 36px; page-break-inside: avoid; }
      .photo-main::after { display: none; }
      .au, .as { opacity: 1; animation: none; }
      .card, .cp { page-break-inside: avoid; }
      h1, h2, h3 { page-break-after: avoid; }
    }
  </style>
</head>
<body>

<!-- SVG Duotone Filter -->
<svg width="0" height="0" style="position:absolute;pointer-events:none">
  <filter id="duotone">
    <feColorMatrix type="matrix" values=".33 .33 .33 0 0 .33 .33 .33 0 0 .33 .33 .33 0 0 0 0 0 1 0"/>
    <feComponentTransfer color-interpolation-filters="sRGB">
      <feFuncR tableValues="0.18 0.78"/>
      <feFuncG tableValues="0.12 0.43"/>
      <feFuncB tableValues="0.35 0.84"/>
    </feComponentTransfer>
  </filter>
</svg>

<div class="progress" id="prog"></div>

<!-- ── TOC ── -->
<aside class="toc">
  <div class="toc-logo-wrap">
    <img
      src="https://media.canva.com/v2/image-resize/format:JPG/height:500/quality:92/uri:ifs%3A%2F%2FM%2F09956a1b-4de4-4132-96eb-6d0b31eeeed4/watermark:F/width:500?csig=AAAAAAAAAAAAAAAAAAAAAEC6aVaVUbPCIh00DpwQGLOPxSPjabuF-TmR-w5RKUDG&exp=1781326174&osig=AAAAAAAAAAAAAAAAAAAAAFVU1_iE6BDr3zpqxxe40AkABsypI3JknEPlN6a9JMEL&signer=media-rpc&x-canva-quality=thumbnail_large"
      alt="Direito em Ação"
      onerror="this.style.display='none'"
    >
  </div>
  <div class="toc-oab">OAB/DF nº 71.232</div>
  <nav>
    <ul>
      <li><a href="#hero"><span class="nav-ico">🏠</span>Início</a></li>
      <li><a href="#objetivo"><span class="nav-ico">🎯</span>Objetivo</a></li>
      <li><a href="#superpoderes"><span class="nav-ico">⚡</span>Diferenciais</a></li>
      <li><a href="#trajetoria"><span class="nav-ico">📋</span>Trajetória</a></li>
      <li><a href="#cases"><span class="nav-ico">🏆</span>Destaques</a></li>
      <li><a href="#atuacao"><span class="nav-ico">⚖️</span>Atuação</a></li>
      <li><a href="#competencias"><span class="nav-ico">🧠</span>Competências</a></li>
      <li><a href="#formacao"><span class="nav-ico">🎓</span>Formação</a></li>
      <li><a href="#contato"><span class="nav-ico">📩</span>Contato</a></li>
    </ul>
  </nav>
</aside>

<main class="content">

  <!-- ── HERO ── -->
  <section id="hero">

    <div class="hero-left">

      <!-- LOGO ACIMA DO TÍTULO -->
      <div class="hero-logo-top au d1">
        <img
          src="https://media.canva.com/v2/image-resize/format:JPG/height:500/quality:92/uri:ifs%3A%2F%2FM%2F09956a1b-4de4-4132-96eb-6d0b31eeeed4/watermark:F/width:500?csig=AAAAAAAAAAAAAAAAAAAAAEC6aVaVUbPCIh00DpwQGLOPxSPjabuF-TmR-w5RKUDG&exp=1781326174&osig=AAAAAAAAAAAAAAAAAAAAAFVU1_iE6BDr3zpqxxe40AkABsypI3JknEPlN6a9JMEL&signer=media-rpc&x-canva-quality=thumbnail_large"
          alt="Direito em Ação"
          onerror="this.style.display='none'"
        >
      </div>

      <div class="hero-badge au d2">
        <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        OAB/DF nº 71.232
      </div>

      <h1 class="au d3">
        Dr. <span class="gt">José Rafael</span><br>Alves Toledo
      </h1>
      <p class="hero-role au d4">Advogado · Direito de Família, Cível &amp; Correlatas</p>
      <p class="hero-tagline au d5">
        Estratégia processual com rigor técnico e atendimento humanizado — condução integral das demandas, do primeiro atendimento à execução.
      </p>
      <div class="hero-loc au d6">
        <span>📍</span> Brasília, Distrito Federal
      </div>

      <div class="hero-stats au d7">
        <div class="h-stat">
          <span class="hs-val blue">4+</span>
          <div class="hs-lbl">Anos de<br>Advocacia</div>
        </div>
        <div class="h-stat">
          <span class="hs-val purple">5+</span>
          <div class="hs-lbl">Áreas de<br>Atuação</div>
        </div>
        <div class="h-stat">
          <span class="hs-val pink">DP</span>
          <div class="hs-lbl">Formação<br>Defensoria</div>
        </div>
        <div class="h-stat">
          <span class="hs-val green">360°</span>
          <div class="hs-lbl">Condução<br>Integral</div>
        </div>
      </div>
    </div>

    <!-- FOTO HERO -->
    <div class="hero-right">
      <div class="photo-hero-wrap as d1">
        <div class="photo-main">
          <img
            src="https://media.canva.com/v2/image-resize/format:JPG/height:550/quality:92/uri:ifs%3A%2F%2FM%2FpQM_Tb2CqlRPRrK4JArRycGPX85RZoSz0Nrz-WiCnWA.jpg/watermark:F/width:309?csig=AAAAAAAAAAAAAAAAAAAAAFkMY5aXLTTHIIQpOKhyt7j4Q67NL0RNJ2u3Jzv49xcn&exp=1781327813&osig=AAAAAAAAAAAAAAAAAAAAAB5smThQ54Vk2t4ibrroVLkKrxm-_vFQzJP9WirAUiOn&signer=media-rpc&x-canva-quality=thumbnail_large"
            alt="Dr. José Rafael Alves Toledo"
            onerror="this.parentElement.innerHTML='<div style=\'width:100%;height:480px;display:flex;align-items:center;justify-content:center;background:linear-gradient(135deg,#2E6BFF,#5B3FD6,#C86DD7);font-size:96px;font-weight:900;color:#F5F7FB;letter-spacing:-.02em\'>JR</div>'"
          >
        </div>
        <div class="oab-float">
          <div class="oab-num">OAB/DF</div>
          <div class="oab-lbl">71.232 · Inscrito</div>
        </div>
      </div>
    </div>

  </section>

  <!-- ── OBJETIVO ── -->
  <section id="objetivo">
    <div class="gl au"></div>
    <h2 class="au">Objetivo <span class="gt">Profissional</span></h2>
    <div class="obj-banner au d1">
      <p>
        Atuação na área jurídica com foco em estratégia processual, condução integral de demandas e resolução eficiente de conflitos — especialmente nas áreas de Direito de Família, Cível e correlatas, incluindo casos de alta sensibilidade envolvendo medidas protetivas.
      </p>
    </div>
  </section>

  <!-- ── DIFERENCIAIS ── -->
  <section id="superpoderes">
    <div class="gl au"></div>
    <h2 class="au">Diferenciais <span class="gt">Profissionais</span></h2>
    <div class="sp-grid">
      <div class="card sp-card au d1">
        <div class="sp-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        </div>
        <h3>Estratégia Processual</h3>
        <p>Estrutura teses jurídicas sólidas com análise de risco, tese principal e subsidiária, e preparação estratégica para audiências.</p>
      </div>
      <div class="card sp-card au d2">
        <div class="sp-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
        </div>
        <h3>Família &amp; Alta Sensibilidade</h3>
        <p>Formação humanizada na Defensoria Pública aplicada a casos de violência doméstica, medidas protetivas e conflitos familiares complexos.</p>
      </div>
      <div class="card sp-card au d3">
        <div class="sp-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
        </div>
        <h3>Visão Multidisciplinar</h3>
        <p>Atuação integrada em Família, Cível, Trabalhista, Previdenciário e Penal — atendimento completo e coordenado ao cliente.</p>
      </div>
      <div class="card sp-card au d4">
        <div class="sp-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
        </div>
        <h3>Perfil Analítico</h3>
        <p>Condução autônoma de processos com foco em resultado — da petição inicial à execução, com rigor técnico em cada fase.</p>
      </div>
      <div class="card sp-card au d5">
        <div class="sp-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>
        </div>
        <h3>Elaboração de Peças</h3>
        <p>Petições iniciais, contestações, manifestações e recursos redigidos com precisão técnica e argumentação estratégica.</p>
      </div>
    </div>
  </section>

  <!-- ── TRAJETÓRIA ── -->
  <section id="trajetoria">
    <div class="gl au"></div>
    <h2 class="au">Trajetória <span class="gt">Profissional</span></h2>
    <div class="tl">
      <div class="tl-item au d1">
        <div class="tl-period">2022 — Atual</div>
        <div class="tl-role">Advogado Autônomo</div>
        <div class="tl-company">Parcerias Jurídicas · Brasília, DF</div>
        <ul>
          <li>Condução integral de demandas de Direito de Família: alimentos, guarda, divórcio e inventário.</li>
          <li>Atuação estratégica em casos de violência doméstica, com acompanhamento de medidas protetivas e desdobramentos cíveis.</li>
          <li>Representação em demandas cíveis: cobrança, responsabilidade civil, relações contratuais e golpes digitais.</li>
          <li>Atuação previdenciária com análise de benefícios e requerimentos administrativos junto ao INSS.</li>
          <li>Elaboração completa de peças processuais: petições iniciais, contestações, manifestações e recursos.</li>
          <li>Gestão de relacionamento com clientes em cenários de conflito de alta carga emocional e jurídica.</li>
          <li>Atuação colaborativa com advogados nas áreas empresarial, trabalhista e penal para soluções integradas.</li>
        </ul>
      </div>
      <div class="tl-item au d2">
        <div class="tl-period">2020 — 2021</div>
        <div class="tl-role">Estagiário Jurídico</div>
        <div class="tl-company">Defensoria Pública do DF · Núcleo de Iniciais – Família</div>
        <ul>
          <li>Atendimento jurídico a população em situação de vulnerabilidade social e econômica.</li>
          <li>Elaboração de petições iniciais em demandas de Família: alimentos, guarda e divórcio.</li>
          <li>Triagem jurídica, análise de casos e encaminhamento estratégico ao defensor responsável.</li>
          <li>Base humanizada consolidada no atendimento a conflitos familiares e situações de violência doméstica.</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- ── DESTAQUES ── -->
  <section id="cases">
    <div class="gl au"></div>
    <h2 class="au">Destaques <span class="gt">da Trajetória</span></h2>
    <div class="cases-grid">
      <div class="cp case-card au d1">
        <div class="case-metric">4+</div>
        <div class="case-title">Anos de Advocacia Autônoma</div>
        <div class="case-ctx">Desde 2022 conduzindo demandas de forma independente e em parceria com especialistas — reputação construída em resultado e confiança.</div>
      </div>
      <div class="cp case-card au d2">
        <div class="case-metric">5+</div>
        <div class="case-title">Áreas de Atuação Simultâneas</div>
        <div class="case-ctx">Família, Cível, Previdenciário, Penal e Trabalhista — perfil raro que permite ao cliente ter um único ponto de confiança jurídica.</div>
      </div>
      <div class="cp case-card au d3">
        <div class="case-metric">DP</div>
        <div class="case-title">Formação na Defensoria Pública</div>
        <div class="case-ctx">Núcleo de Família da DPDF — base técnica e ética construída no atendimento a populações vulneráveis, diferencial que molda o atendimento até hoje.</div>
      </div>
      <div class="cp case-card au d4">
        <div class="case-metric">360°</div>
        <div class="case-title">Condução Integral de Demandas</div>
        <div class="case-ctx">Da análise de risco à execução — estruturação de tese, peças processuais, audiência e gestão do cliente em cada fase.</div>
      </div>
    </div>
  </section>

  <!-- ── ÁREAS ── -->
  <section id="atuacao">
    <div class="gl au"></div>
    <h2 class="au">Áreas de <span class="gt">Atuação</span></h2>
    <div class="areas-grid">
      <div class="area-tile au d1"><span class="area-icon">👨‍👩‍👧</span><div class="area-name">Direito de Família</div><div class="area-sub">Alimentos · Guarda · Divórcio · Inventário · Medidas Protetivas</div></div>
      <div class="area-tile au d2"><span class="area-icon">⚖️</span><div class="area-name">Cível</div><div class="area-sub">Cobrança · Responsabilidade Civil · Contratos · Golpes Digitais</div></div>
      <div class="area-tile au d3"><span class="area-icon">🛡️</span><div class="area-name">Violência Doméstica</div><div class="area-sub">Medidas Protetivas · Lei Maria da Penha · Desdobramentos Cíveis</div></div>
      <div class="area-tile au d4"><span class="area-icon">📋</span><div class="area-name">Previdenciário</div><div class="area-sub">Concessão de Benefícios · Requerimentos Administrativos · INSS</div></div>
      <div class="area-tile au d5"><span class="area-icon">🔒</span><div class="area-name">Penal</div><div class="area-sub">Crimes contra a Honra · Lesões · Furto · Roubo · Execução Penal</div></div>
      <div class="area-tile au d6"><span class="area-icon">💼</span><div class="area-name">Trabalhista</div><div class="area-sub">Reconhecimento de Vínculo · Rescisão Indireta · Atuação Colaborativa</div></div>
    </div>
  </section>

  <!-- ── COMPETÊNCIAS ── -->
  <section id="competencias">
    <div class="gl au"></div>
    <h2 class="au"><span class="gt">Competências</span> Técnicas</h2>
    <div class="comp-grid">
      <div class="comp-item au d1"><div class="ci-dot"></div><span>Estratégia processual e condução integral de demandas</span></div>
      <div class="comp-item au d2"><div class="ci-dot"></div><span>Estruturação de teses jurídicas</span></div>
      <div class="comp-item au d3"><div class="ci-dot"></div><span>Direito de Família e demandas de alta sensibilidade</span></div>
      <div class="comp-item au d4"><div class="ci-dot"></div><span>Medidas protetivas e Lei Maria da Penha</span></div>
      <div class="comp-item au d5"><div class="ci-dot"></div><span>Análise de risco processual</span></div>
      <div class="comp-item au d6"><div class="ci-dot"></div><span>Elaboração de peças jurídicas completas</span></div>
      <div class="comp-item au d7"><div class="ci-dot"></div><span>Comunicação jurídica e negociação</span></div>
      <div class="comp-item au d1"><div class="ci-dot"></div><span>Atuação interdisciplinar e colaborativa</span></div>
      <div class="comp-item au d2"><div class="ci-dot"></div><span>Tecnologia aplicada ao Direito</span></div>
      <div class="comp-item au d3"><div class="ci-dot"></div><span>Gestão de clientes em situações de conflito</span></div>
    </div>

    <div style="margin-top:44px;">
      <div class="gl au"></div>
      <h3 class="au" style="font-size:21px;font-weight:700;margin-bottom:18px;color:#F5F7FB;letter-spacing:-.01em;">Diferenciais <span class="gt">Pessoais</span></h3>
      <div class="dif-grid">
        <div class="dif-item au d1"><div class="di-ic">🎯</div><p>Experiência prática consistente desde o início da carreira, com atuação direta em conflitos de alta sensibilidade jurídica e emocional.</p></div>
        <div class="dif-item au d2"><div class="di-ic">🧠</div><p>Perfil analítico com foco em solução de problemas — capacidade de condução autônoma e completa de processos complexos.</p></div>
        <div class="dif-item au d3"><div class="di-ic">🔄</div><p>Facilidade de adaptação a diferentes áreas do Direito, com integração entre atuação técnica e visão estratégica.</p></div>
        <div class="dif-item au d4"><div class="di-ic">💻</div><p>Familiaridade com tecnologia aplicada ao Direito e abertura para novos ambientes de equipe e desafios institucionais.</p></div>
      </div>
    </div>
  </section>

  <!-- ── FORMAÇÃO ── -->
  <section id="formacao">
    <div class="gl au"></div>
    <h2 class="au"><span class="gt">Formação</span> Acadêmica</h2>
    <div class="card edu-card au d1">
      <div class="edu-icon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>
      </div>
      <div>
        <div class="edu-period">Graduação · 2016 – 2021</div>
        <div class="edu-degree">Bacharelado em Direito</div>
        <div class="edu-inst">Faculdade Estácio · Brasília, DF</div>
        <div class="edu-note">Inscrito na OAB/DF sob o nº 71.232</div>
      </div>
    </div>
    <div class="card au d2" style="margin-top:14px;padding:26px;">
      <div style="font-size:11px;color:#7E879B;letter-spacing:.07em;text-transform:uppercase;font-weight:600;margin-bottom:14px;">Especialidades &amp; Áreas de Enfoque</div>
      <div>
        <span class="pill highlight">Direito de Família</span>
        <span class="pill highlight">Medidas Protetivas</span>
        <span class="pill highlight">Direito Cível</span>
        <span class="pill">Direito Previdenciário</span>
        <span class="pill">Direito Penal</span>
        <span class="pill">Direito do Trabalho</span>
        <span class="pill">Processo Civil</span>
        <span class="pill">Execução Penal</span>
        <span class="pill">Direito Digital</span>
      </div>
    </div>
  </section>

  <!-- ── CONTATO ── -->
  <section id="contato">
    <div class="gl au"></div>
    <h2 class="au">Entre em <span class="gt">Contato</span></h2>
    <p class="au" style="color:#AAB3C5;font-size:16px;margin-bottom:30px;max-width:520px;line-height:1.75;">
      Precisa de orientação jurídica ou quer discutir uma parceria? Atendo em Brasília/DF e remotamente em todo o Brasil.
    </p>
    <div class="contact-grid">

      <div class="card contact-card au d1">
        <div class="ct-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        </div>
        <div class="ct-info">
          <div class="ct-lbl">E-mail</div>
          <div class="ct-val"><a href="mailto:joeraff@outlook.com">joeraff@outlook.com</a></div>
        </div>
      </div>

      <div class="card contact-card au d2">
        <div class="ct-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.59 1.23h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L8 8.09a16 16 0 0 0 6 6l.86-.86a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 21.73 16a2 2 0 0 1 .19.92z"/></svg>
        </div>
        <div class="ct-info">
          <div class="ct-lbl">WhatsApp · Linha 1</div>
          <div class="ct-val"><a href="https://wa.me/5561984420642">(61) 98442-0642</a></div>
        </div>
      </div>

      <div class="card contact-card au d3">
        <div class="ct-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.59 1.23h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L8 8.09a16 16 0 0 0 6 6l.86-.86a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 21.73 16a2 2 0 0 1 .19.92z"/></svg>
        </div>
        <div class="ct-info">
          <div class="ct-lbl">WhatsApp · Linha 2</div>
          <div class="ct-val"><a href="https://wa.me/5561985280508">(61) 98528-0508</a></div>
        </div>
      </div>

      <div class="card contact-card au d4">
        <div class="ct-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
        </div>
        <div class="ct-info">
          <div class="ct-lbl">Instagram</div>
          <div class="ct-val"><a href="https://instagram.com/cantinho_dodireito" target="_blank" rel="noopener">@cantinho_dodireito</a></div>
        </div>
      </div>

      <div class="card contact-card au d5">
        <div class="ct-ic">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg>
        </div>
        <div class="ct-info">
          <div class="ct-lbl">Localização</div>
          <div class="ct-val">Brasília, Distrito Federal</div>
        </div>
      </div>

    </div>
  </section>

</main>

<button class="print-btn" onclick="doPrint()">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 6 2 18 2 18 9"/><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"/><rect x="6" y="14" width="12" height="8"/></svg>
  PDF
</button>
<button class="fs-btn" onclick="toggleFs()">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>
  Tela Cheia
</button>

<script>
  // Scroll progress
  const prog = document.getElementById('prog');
  window.addEventListener('scroll', () => {
    const h = document.documentElement;
    prog.style.width = (h.scrollTop / (h.scrollHeight - h.clientHeight) * 100) + '%';
  }, { passive: true });

  // Active TOC
  const sections = document.querySelectorAll('section[id]');
  const tocLinks = document.querySelectorAll('.toc a');
  sections.forEach(s => {
    new IntersectionObserver(entries => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          const id = e.target.id;
          tocLinks.forEach(a => a.classList.toggle('active', a.getAttribute('href') === '#' + id));
        }
      });
    }, { rootMargin: '-40% 0px -40% 0px' }).observe(s);
  });

  // Smooth scroll
  tocLinks.forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const t = document.querySelector(a.getAttribute('href'));
      if (t) t.scrollIntoView({ behavior: 'smooth', block: 'start' });
    });
  });

  // Animate on viewport
  const animObs = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('in-view'); });
  }, { threshold: .1 });
  document.querySelectorAll('.au, .as').forEach(el => animObs.observe(el));

  // Radial glow
  document.querySelectorAll('.cp').forEach(card => {
    card.addEventListener('mousemove', e => {
      const r = card.getBoundingClientRect();
      card.style.setProperty('--mx', ((e.clientX - r.left) / r.width * 100) + '%');
      card.style.setProperty('--my', ((e.clientY - r.top) / r.height * 100) + '%');
    });
  });

  function toggleFs() {
    if (!document.fullscreenElement) document.documentElement.requestFullscreen().catch(() => {});
    else document.exitFullscreen();
  }
  function doPrint() { window.print(); }
</script>
</body>
</html>
