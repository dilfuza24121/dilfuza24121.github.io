<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TrustPay UZ — Xavfsiz Escrow Platformasi (Demo)</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ======= GLOBAL ======= */
:root {
  --navy: #042C53;
  --blue: #185FA5;
  --lblue: #B5D4F4;
  --eblue: #E6F1FB;
  --white: #FFFFFF;
  --off: #F8F9FB;
  --green: #3B6D11;
  --egreen: #EAF3DE;
  --muted: #64748B;
  --border: #E2E8F0;
  --text: #0F172A;
  --radius: 12px;
  --radius-sm: 8px;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;background:var(--white);color:var(--text);line-height:1.6}

/* ======= NAV ======= */
nav{position:sticky;top:0;z-index:100;background:rgba(255,255,255,0.95);backdrop-filter:blur(12px);border-bottom:1px solid var(--border);padding:0 24px}
.nav-inner{max-width:1100px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;height:60px}
.logo{font-size:20px;font-weight:600;color:var(--navy);letter-spacing:-0.5px}
.logo span{color:var(--blue)}
.lang-bar{display:flex;gap:4px}
.lang-btn{padding:5px 14px;border-radius:50px;border:1px solid var(--border);background:transparent;cursor:pointer;font-size:13px;font-family:'DM Sans',sans-serif;color:var(--muted);transition:all 0.15s}
.lang-btn.active{background:var(--navy);color:var(--white);border-color:var(--navy)}
.nav-links{display:flex;gap:24px}
.nav-links a{font-size:14px;color:var(--muted);text-decoration:none;transition:color 0.15s}
.nav-links a:hover{color:var(--navy)}

/* ======= HERO ======= */
.hero{background:var(--navy);padding:80px 24px 70px;text-align:center;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;top:-80px;right:-80px;width:400px;height:400px;border-radius:50%;background:rgba(24,95,165,0.25);pointer-events:none}
.hero::after{content:'';position:absolute;bottom:-100px;left:-60px;width:300px;height:300px;border-radius:50%;background:rgba(24,95,165,0.15);pointer-events:none}
.hero-inner{max-width:700px;margin:0 auto;position:relative;z-index:1}
.hero-pill{display:inline-flex;align-items:center;gap:6px;background:rgba(255,255,255,0.1);border:1px solid rgba(255,255,255,0.2);border-radius:50px;padding:6px 16px;font-size:12px;color:var(--lblue);margin-bottom:24px;letter-spacing:0.5px}
.hero h1{font-size:clamp(36px,6vw,64px);font-weight:600;color:var(--white);line-height:1.1;letter-spacing:-1.5px;margin-bottom:20px}
.hero h1 span{color:#85B7EB}
.hero-sub{font-size:17px;color:var(--lblue);line-height:1.7;margin-bottom:36px;max-width:560px;margin-left:auto;margin-right:auto}
.hero-btns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-bottom:48px}
.btn-primary{padding:13px 28px;background:var(--white);color:var(--navy);border-radius:50px;font-size:15px;font-weight:600;cursor:pointer;border:none;transition:all 0.15s;text-decoration:none;font-family:'DM Sans',sans-serif}
.btn-primary:hover{background:var(--lblue)}
.btn-outline{padding:13px 28px;background:transparent;color:var(--white);border:1.5px solid rgba(255,255,255,0.35);border-radius:50px;font-size:15px;font-weight:500;cursor:pointer;transition:all 0.15s;text-decoration:none;font-family:'DM Sans',sans-serif}
.btn-outline:hover{background:rgba(255,255,255,0.1)}
.hero-stats{display:flex;gap:16px;justify-content:center;flex-wrap:wrap}
.hstat{background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.15);border-radius:var(--radius-sm);padding:16px 24px;text-align:center;min-width:120px}
.hstat-val{font-size:24px;font-weight:600;color:var(--white)}
.hstat-lbl{font-size:12px;color:var(--lblue);margin-top:2px}

/* ======= SECTIONS ======= */
section{padding:72px 24px}
.section-inner{max-width:1100px;margin:0 auto}
.section-tag{font-size:12px;font-weight:500;color:var(--blue);letter-spacing:1.5px;text-transform:uppercase;margin-bottom:12px}
.section-title{font-size:clamp(26px,4vw,38px);font-weight:600;color:var(--navy);letter-spacing:-0.8px;margin-bottom:12px;line-height:1.2}
.section-sub{font-size:16px;color:var(--muted);max-width:540px;line-height:1.7}

/* ======= FOOTER ======= */
footer{background:var(--navy);padding:48px 24px 32px;color:var(--lblue)}
.footer-inner{max-width:1100px;margin:0 auto}
.footer-top{display:flex;justify-content:space-between;align-items:flex-start;flex-wrap:wrap;gap:24px;margin-bottom:32px}
.footer-logo{font-size:22px;font-weight:600;color:var(--white)}
.footer-logo span{color:#85B7EB}
.footer-tagline{font-size:13px;color:var(--lblue);margin-top:4px}
.footer-contact{font-size:13px;line-height:2}
.footer-contact a{color:var(--lblue);text-decoration:none}
.footer-bottom{border-top:1px solid rgba(255,255,255,0.1);padding-top:20px;font-size:13px;color:rgba(181,212,244,0.6);display:flex;justify-content:space-between;flex-wrap:wrap;gap:8px}

/* ======= MEDIA ======= */
@media(max-width:640px){
  .cards3{grid-template-columns:1fr}
  .nav-links{display:none}
  .hero h1{font-size:32px}
  .hstat{min-width:100px}
  .footer-top{flex-direction:column}
}
</style>
</head>
<body>

<nav>
  <div class="nav-inner">
    <div class="logo">Trust<span>Pay</span> UZ</div>
    <div class="nav-links">
      <a href="#how">Qanday ishlaydi</a>
      <a href="#demo">Demo</a>
      <a href="#pricing">Tariflar</a>
      <a href="#faq">Savol-javob</a>
    </div>
    <div class="lang-bar">
      <button class="lang-btn active">UZ</button>
      <button class="lang-btn">RU</button>
      <button class="lang-btn">EN</button>
    </div>
  </div>
</nav>

<section class="hero">
  <div class="hero-inner">
    <div class="hero-pill">O'zbekiston #1 Escrow Platformasi</div>
    <h1>Onlayn savdoda <span>ishonch</span> siz bilan</h1>
    <p class="hero-sub">Xaridor ham, sotuvchi ham himoyalangan. Pul tovar yetib kelgach, sotuvchiga o'tkaziladi. Firibgarlikka barham.</p>
    <div class="hero-btns">
      <a href="#demo" class="btn-primary">Demo ko'rish</a>
      <a href="#how" class="btn-outline">Qanday ishlaydi?</a>
    </div>
    <div class="hero-stats">
      <div class="hstat"><div class="hstat-val">53K+</div><div class="hstat-lbl">Telegram do'konlar</div></div>
      <div class="hstat"><div class="hstat-val">$47M</div><div class="hstat-lbl">Yillik zarar</div></div>
      <div class="hstat"><div class="hstat-val">1.5%</div><div class="hstat-lbl">Komissiya</div></div>
      <div class="hstat"><div class="hstat-val">24h</div><div class="hstat-lbl">Bahslarni hal qilish</div></div>
    </div>
  </div>
</section>

<footer>
  <div class="footer-inner">
    <div class="footer-top">
      <div>
        <div class="footer-logo">Trust<span>Pay</span> UZ</div>
        <div class="footer-tagline">O'zbekiston #1 Escrow Platformasi</div>
      </div>
      <div class="footer-contact">
        <p>Email: <a href="mailto:info@trustpay.uz">info@trustpay.uz</a></p>
        <p>Telegram: <a href="#">@TrustPayUZ</a></p>
        <p>Telefon: +998 90 123 45 67</p>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2026 TrustPay UZ. Barcha huquqlar himoyalangan.</span>
      <span>Developed by Dilfuza</span>
    </div>
  </div>
</footer>

</body>
</html>
