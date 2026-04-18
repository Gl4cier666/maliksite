<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>I'MTEA — Wellness Botanical Tea</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --deep:    #1A083A;
  --mid:     #3D1F5C;
  --soft:    #7A5C9A;
  --lav:     #C4A0E0;
  --pale:    #F3EFF8;
  --white:   #FAF8FC;
  --fog:     rgba(196,160,224,0.12);
  --border:  rgba(196,160,224,0.18);
}

html { scroll-behavior: smooth; }

body {
  background: var(--deep);
  color: var(--pale);
  font-family: 'Cormorant Garamond', Georgia, serif;
  overflow-x: hidden;
}

/* ── NAV ── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  display: flex; align-items: center; justify-content: space-between;
  padding: 1.4rem 3rem;
  transition: background 0.4s, border-color 0.4s;
}
nav.scrolled {
  background: rgba(26,8,58,0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border);
}
.nav-logo {
  font-size: 1.45rem; font-weight: 300; letter-spacing: 0.1em;
  color: var(--white); text-decoration: none;
}
.nav-logo em { font-style: italic; color: var(--lav); }
.nav-links { display: flex; gap: 2rem; list-style: none; }
.nav-links a {
  font-family: 'DM Mono', monospace; font-size: 0.65rem;
  letter-spacing: 0.14em; text-transform: uppercase;
  color: var(--pale); text-decoration: none; opacity: 0.5;
  transition: opacity 0.2s;
}
.nav-links a:hover { opacity: 1; }
.nav-order {
  font-family: 'DM Mono', monospace; font-size: 0.65rem;
  letter-spacing: 0.12em; text-transform: uppercase;
  background: var(--soft); color: var(--white);
  border: none; padding: 0.6rem 1.4rem; cursor: pointer;
  transition: background 0.2s;
  text-decoration: none; display: inline-block;
}
.nav-order:hover { background: #9B7BBB; }

/* ── HERO ── */
.hero {
  min-height: 100vh;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  text-align: center;
  padding: 9rem 2rem 6rem;
  position: relative; overflow: hidden;
}
.hero-rings {
  position: absolute; inset: 0;
  display: flex; align-items: center; justify-content: center;
  pointer-events: none;
}
.hero-rings svg { position: absolute; }

.hero-eyebrow {
  font-family: 'DM Mono', monospace; font-size: 0.62rem;
  letter-spacing: 0.24em; text-transform: uppercase;
  color: var(--soft); margin-bottom: 1.6rem;
}
.hero-title {
  font-size: clamp(5rem, 14vw, 10rem);
  font-weight: 300; line-height: 0.9;
  letter-spacing: -0.02em; color: var(--white);
  margin-bottom: 0.2rem;
}
.hero-title em { font-style: italic; color: var(--lav); }
.hero-sub {
  font-size: clamp(1.1rem, 2vw, 1.35rem);
  font-weight: 300; line-height: 1.7;
  color: rgba(243,239,248,0.5);
  max-width: 42ch; margin: 2rem auto 3rem;
}
.hero-pills {
  display: flex; flex-wrap: wrap; gap: 0.5rem;
  justify-content: center; margin-bottom: 3rem;
}
.pill {
  font-family: 'DM Mono', monospace; font-size: 0.58rem;
  letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--lav); border: 1px solid rgba(196,160,224,0.28);
  padding: 0.28rem 0.85rem; border-radius: 99px;
}
.hero-cta {
  display: inline-block;
  font-family: 'DM Mono', monospace; font-size: 0.7rem;
  letter-spacing: 0.18em; text-transform: uppercase;
  background: var(--soft); color: var(--white);
  padding: 1rem 2.8rem; text-decoration: none;
  transition: background 0.2s, transform 0.15s;
}
.hero-cta:hover { background: #9B7BBB; transform: translateY(-2px); }

/* ── SECTION SHARED ── */
.section-label {
  font-family: 'DM Mono', monospace; font-size: 0.62rem;
  letter-spacing: 0.22em; text-transform: uppercase;
  color: var(--soft); margin-bottom: 0.8rem;
}
.section-title {
  font-size: clamp(2rem, 4vw, 3.2rem);
  font-weight: 300; line-height: 1.1; color: var(--white);
}
.section-title em { font-style: italic; color: var(--lav); }

.divider {
  display: flex; align-items: center; gap: 1rem;
  opacity: 0.18; margin: 0;
}
.divider::before, .divider::after {
  content: ''; flex: 1; height: 1px; background: var(--lav);
}
.divider-diamond {
  width: 5px; height: 5px;
  background: var(--lav); transform: rotate(45deg); flex-shrink: 0;
}

/* ── INGREDIENTS ── */
.ingredients {
  padding: 7rem 3rem;
  max-width: 1100px; margin: 0 auto;
}
.ingredients-header { margin-bottom: 4rem; }
.ingredient-grid {
  display: grid; grid-template-columns: repeat(4, 1fr);
  border: 1px solid var(--border);
}
.ing-card {
  padding: 2.5rem 2rem;
  border-right: 1px solid var(--border);
  transition: background 0.3s;
}
.ing-card:last-child { border-right: none; }
.ing-card:hover { background: rgba(196,160,224,0.05); }
.ing-num {
  font-family: 'DM Mono', monospace; font-size: 0.58rem;
  letter-spacing: 0.18em; color: var(--lav);
  opacity: 0.5; margin-bottom: 1.5rem;
}
.ing-icon { width: 2.8rem; height: 2.8rem; margin-bottom: 1.2rem; }
.ing-name {
  font-size: 1.55rem; font-weight: 400;
  color: var(--white); margin-bottom: 0.2rem; line-height: 1;
}
.ing-origin {
  font-family: 'DM Mono', monospace; font-size: 0.58rem;
  letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--soft); margin-bottom: 1rem;
}
.ing-desc {
  font-size: 0.95rem; font-weight: 300;
  line-height: 1.65; color: rgba(243,239,248,0.5);
}
.ing-benefit {
  margin-top: 1.2rem;
  display: inline-flex; align-items: center; gap: 0.4rem;
  font-family: 'DM Mono', monospace; font-size: 0.58rem;
  letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--lav);
}
.ing-benefit::before {
  content: ''; display: block;
  width: 0.35rem; height: 0.35rem;
  background: var(--lav); border-radius: 50%;
}

/* ── BENEFITS ── */
.benefits-wrap {
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  background: rgba(196,160,224,0.04);
}
.benefits {
  max-width: 1100px; margin: 0 auto;
  padding: 7rem 3rem;
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 5rem; align-items: center;
}
.benefits-list { list-style: none; margin-top: 2.5rem; }
.benefits-list li {
  display: flex; gap: 1.5rem;
  padding: 1.4rem 0;
  border-bottom: 1px solid var(--border);
  align-items: flex-start;
}
.benefits-list li:first-child { border-top: 1px solid var(--border); }
.b-num {
  font-family: 'DM Mono', monospace; font-size: 0.58rem;
  color: var(--lav); letter-spacing: 0.1em;
  padding-top: 0.25rem; flex-shrink: 0; opacity: 0.6;
}
.b-text strong {
  display: block; font-size: 1.15rem;
  font-weight: 400; color: var(--white); margin-bottom: 0.25rem;
}
.b-text span {
  font-size: 0.95rem; font-weight: 300;
  color: rgba(243,239,248,0.45); line-height: 1.55;
}
.benefits-visual {
  display: flex; align-items: center; justify-content: center;
}

/* ── ORDER FORM ── */
.order-section {
  max-width: 640px; margin: 0 auto;
  padding: 7rem 2rem 6rem;
}
.order-header { text-align: center; margin-bottom: 3rem; }
.order-header .section-title { margin-bottom: 0.5rem; }
.order-header p {
  font-family: 'DM Mono', monospace; font-size: 0.6rem;
  letter-spacing: 0.14em; text-transform: uppercase;
  color: var(--soft);
}
.form-card {
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  padding: 2.5rem;
}
.field { margin-bottom: 1.2rem; }
.field-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
label {
  display: block;
  font-family: 'DM Mono', monospace; font-size: 0.58rem;
  letter-spacing: 0.18em; text-transform: uppercase;
  color: var(--soft); margin-bottom: 0.4rem;
}
input, select, textarea {
  width: 100%; background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  color: var(--pale);
  font-family: 'Cormorant Garamond', Georgia, serif;
  font-size: 1.05rem; font-weight: 300;
  padding: 0.7rem 1rem; outline: none;
  transition: border-color 0.2s, background 0.2s;
  -webkit-appearance: none; appearance: none;
}
input::placeholder, textarea::placeholder { color: rgba(196,160,224,0.22); }
input:focus, select:focus, textarea:focus {
  border-color: rgba(196,160,224,0.55);
  background: rgba(255,255,255,0.07);
}
select {
  cursor: pointer;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%237A5C9A' stroke-width='1.5' fill='none' stroke-linecap='round'/%3E%3C/svg%3E");
  background-repeat: no-repeat; background-position: right 1rem center;
  padding-right: 2.5rem;
}
select option { background: #2A1245; color: var(--pale); }
textarea { resize: none; line-height: 1.6; }
.price-note {
  font-family: 'DM Mono', monospace; font-size: 0.57rem;
  letter-spacing: 0.1em; color: rgba(196,160,224,0.3);
  margin-top: 0.35rem;
}
.error-hint {
  font-family: 'DM Mono', monospace; font-size: 0.58rem;
  letter-spacing: 0.08em; color: rgba(220,120,120,0.8);
  margin-top: 0.5rem; display: none;
}
.submit-btn {
  width: 100%; margin-top: 1.75rem;
  background: var(--soft); border: none; color: var(--white);
  font-family: 'DM Mono', monospace; font-size: 0.7rem;
  letter-spacing: 0.18em; text-transform: uppercase;
  padding: 1rem; cursor: pointer;
  transition: background 0.2s, transform 0.15s;
}
.submit-btn:hover { background: #9B7BBB; transform: translateY(-1px); }
.submit-btn:active { transform: translateY(0); }

/* success */
.success-msg {
  display: none; text-align: center; padding: 3rem 0 2rem;
}
.success-icon {
  width: 52px; height: 52px;
  border: 1px solid var(--border); border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  margin: 0 auto 1.5rem;
}
.success-title {
  font-size: 2.2rem; font-weight: 300;
  color: var(--white); margin-bottom: 0.6rem;
}
.success-title em { font-style: italic; color: var(--lav); }
.success-body {
  font-size: 1rem; font-weight: 300;
  color: rgba(243,239,248,0.5); line-height: 1.75;
  max-width: 30ch; margin: 0 auto;
}

/* ── FOOTER ── */
footer {
  text-align: center;
  padding: 2.5rem;
  border-top: 1px solid var(--border);
  font-family: 'DM Mono', monospace; font-size: 0.57rem;
  letter-spacing: 0.14em; text-transform: uppercase;
  color: rgba(122,92,154,0.35);
}
footer a { color: inherit; text-decoration: none; }
footer a:hover { color: var(--soft); }

/* ── FADE-UP ── */
.fade-up {
  opacity: 0; transform: translateY(22px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.fade-up.visible { opacity: 1; transform: translateY(0); }

/* ── RESPONSIVE ── */
@media (max-width: 800px) {
  nav { padding: 1.2rem 1.5rem; }
  .nav-links { display: none; }
  .ingredients { padding: 5rem 1.5rem; }
  .ingredient-grid { grid-template-columns: 1fr 1fr; }
  .ing-card:nth-child(2) { border-right: none; }
  .ing-card:nth-child(3) { border-right: 1px solid var(--border); }
  .ing-card:nth-child(1), .ing-card:nth-child(2) { border-bottom: 1px solid var(--border); }
  .benefits { grid-template-columns: 1fr; padding: 5rem 1.5rem; gap: 3rem; }
  .benefits-visual { display: none; }
  .order-section { padding: 5rem 1.5rem 4rem; }
  .form-card { padding: 1.75rem 1.25rem; }
  .field-row { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
  <a href="#" class="nav-logo">I'M<em>TEA</em></a>
  <ul class="nav-links">
    <li><a href="#ingredients">Ingredients</a></li>
    <li><a href="#benefits">Benefits</a></li>
    <li><a href="#order">Order</a></li>
  </ul>
  <a href="#order" class="nav-order">Order Now</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-rings">
    <svg width="900" height="900" viewBox="0 0 900 900">
      <circle cx="450" cy="450" r="440" fill="none" stroke="rgba(196,160,224,0.06)" stroke-width="1"/>
      <circle cx="450" cy="450" r="320" fill="none" stroke="rgba(196,160,224,0.05)" stroke-width="1"/>
      <circle cx="450" cy="450" r="200" fill="none" stroke="rgba(196,160,224,0.04)" stroke-width="1"/>
    </svg>
  </div>
  <div class="hero-eyebrow">Wellness Botanical Blend</div>
  <h1 class="hero-title">I'M<em>TEA</em></h1>
  <p class="hero-sub">Four botanicals. Real antiviral and antioxidant power. A daily ritual worth making.</p>
  <div class="hero-pills">
    <span class="pill">Kenyan Purple Tea</span>
    <span class="pill">Fennel</span>
    <span class="pill">Rosemary</span>
    <span class="pill">Ginger</span>
  </div>
  <a href="#order" class="hero-cta">Order Your Blend →</a>
</section>

<!-- INGREDIENTS -->
<section id="ingredients">
  <div class="ingredients">
    <div class="ingredients-header fade-up">
      <div class="section-label">The Formula</div>
      <h2 class="section-title">Four ingredients.<br><em>One intention.</em></h2>
    </div>

    <div class="ingredient-grid">
      <!-- Purple Tea -->
      <div class="ing-card fade-up">
        <div class="ing-num">01</div>
        <svg class="ing-icon" viewBox="0 0 48 48" fill="none">
          <ellipse cx="24" cy="30" rx="14" ry="10" fill="rgba(90,56,128,0.25)"/>
          <path d="M24 8 Q33 17 31 27 Q29 35 24 37 Q19 35 17 27 Q15 17 24 8Z" fill="#5A3880" opacity="0.85"/>
          <path d="M24 8 L24 37" stroke="#9A7CBB" stroke-width="0.7"/>
          <path d="M24 17 Q29 19 30 23" stroke="#C4A0E0" stroke-width="0.6" fill="none"/>
          <path d="M24 22 Q19 24 18 28" stroke="#C4A0E0" stroke-width="0.6" fill="none"/>
        </svg>
        <div class="ing-name">Purple Tea</div>
        <div class="ing-origin">Kenyan Highlands</div>
        <p class="ing-desc">A rare cultivar prized for its deep anthocyanin content — the same pigments found in blueberries, in a leaf.</p>
        <div class="ing-benefit">High anthocyanin antioxidants</div>
      </div>

      <!-- Fennel -->
      <div class="ing-card fade-up" style="transition-delay:0.1s">
        <div class="ing-num">02</div>
        <svg class="ing-icon" viewBox="0 0 48 48" fill="none">
          <line x1="24" y1="42" x2="24" y2="8" stroke="#5A8A50" stroke-width="1.5"/>
          <line x1="24" y1="20" x2="36" y2="14" stroke="#8ABE78" stroke-width="1"/>
          <line x1="24" y1="20" x2="12" y2="14" stroke="#8ABE78" stroke-width="1"/>
          <line x1="24" y1="29" x2="38" y2="25" stroke="#8ABE78" stroke-width="1"/>
          <line x1="24" y1="29" x2="10" y2="25" stroke="#8ABE78" stroke-width="1"/>
          <circle cx="37" cy="13" r="2" fill="#C4A0E0" opacity="0.7"/>
          <circle cx="11" cy="13" r="2" fill="#C4A0E0" opacity="0.7"/>
          <circle cx="39" cy="24" r="2" fill="#C4A0E0" opacity="0.7"/>
          <circle cx="9" cy="24" r="2" fill="#C4A0E0" opacity="0.7"/>
          <circle cx="24" cy="8" r="2.5" fill="#C4A0E0" opacity="0.8"/>
        </svg>
        <div class="ing-name">Fennel</div>
        <div class="ing-origin">Mediterranean Herb</div>
        <p class="ing-desc">Aromatic seeds rich in anethole — a compound with documented anti-inflammatory and antimicrobial properties.</p>
        <div class="ing-benefit">Anti-inflammatory support</div>
      </div>

      <!-- Rosemary -->
      <div class="ing-card fade-up" style="transition-delay:0.2s">
        <div class="ing-num">03</div>
        <svg class="ing-icon" viewBox="0 0 48 48" fill="none">
          <path d="M22 42 L26 8" stroke="#3A6A30" stroke-width="1.5" stroke-linecap="round"/>
          <line x1="24" y1="35" x2="34" y2="31" stroke="#4A8040" stroke-width="1"/>
          <line x1="24" y1="35" x2="14" y2="31" stroke="#4A8040" stroke-width="1"/>
          <line x1="24.5" y1="28" x2="35" y2="24" stroke="#4A8040" stroke-width="1"/>
          <line x1="24.5" y1="28" x2="14" y2="24" stroke="#4A8040" stroke-width="1"/>
          <line x1="25" y1="21" x2="34" y2="18" stroke="#4A8040" stroke-width="1"/>
          <line x1="25" y1="21" x2="16" y2="18" stroke="#4A8040" stroke-width="1"/>
          <line x1="25.5" y1="14" x2="32" y2="11" stroke="#4A8040" stroke-width="0.8"/>
          <line x1="25.5" y1="14" x2="19" y2="11" stroke="#4A8040" stroke-width="0.8"/>
        </svg>
        <div class="ing-name">Rosemary</div>
        <div class="ing-origin">Aromatic Evergreen</div>
        <p class="ing-desc">Rosmarinic acid and carnosic acid make rosemary one of the most studied antiviral herbs in botanical medicine.</p>
        <div class="ing-benefit">Antiviral rosmarinic acid</div>
      </div>

      <!-- Ginger -->
      <div class="ing-card fade-up" style="transition-delay:0.3s">
        <div class="ing-num">04</div>
        <svg class="ing-icon" viewBox="0 0 48 48" fill="none">
          <path d="M6 28 Q14 20 22 24 Q30 28 34 22 Q38 16 34 12" fill="none" stroke="#8B5E3C" stroke-width="1.5" stroke-linecap="round"/>
          <path d="M6 28 Q10 35 16 33 Q20 31 22 24" fill="#9B6E4C" opacity="0.35"/>
          <path d="M22 24 Q28 26 34 22" fill="#8B5E3C" opacity="0.35"/>
          <path d="M34 22 Q40 22 42 27 Q44 32 40 34 Q36 36 34 31" fill="#9B6E4C" opacity="0.5" stroke="#6B4226" stroke-width="0.8"/>
          <path d="M16 33 Q14 40 8 40 Q4 40 4 36 Q4 28 6 28" fill="#9B6E4C" opacity="0.5" stroke="#6B4226" stroke-width="0.8"/>
        </svg>
        <div class="ing-name">Ginger</div>
        <div class="ing-origin">Root Rhizome</div>
        <p class="ing-desc">Gingerols and shogaols activate immune pathways and enhance circulation with every cup.</p>
        <div class="ing-benefit">Immune activation</div>
      </div>
    </div>
  </div>
</section>

<!-- BENEFITS -->
<div class="benefits-wrap" id="benefits">
  <div class="benefits">
    <div class="fade-up">
      <div class="section-label">Why It Works</div>
      <h2 class="section-title">Real botanical <em>science</em> in every cup.</h2>
      <ul class="benefits-list">
        <li>
          <span class="b-num">01</span>
          <div class="b-text">
            <strong>Antiviral Defense</strong>
            <span>Rosemary and ginger contain compounds studied for their ability to inhibit viral replication and strengthen immunity.</span>
          </div>
        </li>
        <li>
          <span class="b-num">02</span>
          <div class="b-text">
            <strong>Antioxidant Power</strong>
            <span>Kenyan purple tea delivers anthocyanins that neutralize free radicals — more potent than green or black tea.</span>
          </div>
        </li>
        <li>
          <span class="b-num">03</span>
          <div class="b-text">
            <strong>Anti-inflammatory Action</strong>
            <span>Fennel's anethole and ginger's gingerols work together to modulate the body's inflammatory response.</span>
          </div>
        </li>
        <li>
          <span class="b-num">04</span>
          <div class="b-text">
            <strong>Digestive Support</strong>
            <span>Fennel and ginger calm the gut, improve digestion, and support healthy metabolism daily.</span>
          </div>
        </li>
      </ul>
    </div>

    <!-- Radial diagram -->
    <div class="benefits-visual fade-up" style="transition-delay:0.15s">
      <svg width="380" height="380" viewBox="0 0 380 380">
        <circle cx="190" cy="190" r="170" fill="none" stroke="rgba(196,160,224,0.1)" stroke-width="1"/>
        <circle cx="190" cy="190" r="120" fill="none" stroke="rgba(196,160,224,0.07)" stroke-width="1"/>
        <line x1="190" y1="50" x2="330" y2="190" stroke="rgba(122,92,154,0.3)" stroke-width="1"/>
        <line x1="330" y1="190" x2="190" y2="330" stroke="rgba(122,92,154,0.3)" stroke-width="1"/>
        <line x1="190" y1="330" x2="50" y2="190" stroke="rgba(122,92,154,0.3)" stroke-width="1"/>
        <line x1="50" y1="190" x2="190" y2="50" stroke="rgba(122,92,154,0.3)" stroke-width="1"/>
        <line x1="190" y1="50" x2="190" y2="330" stroke="rgba(122,92,154,0.12)" stroke-width="0.5"/>
        <line x1="50" y1="190" x2="330" y2="190" stroke="rgba(122,92,154,0.12)" stroke-width="0.5"/>

        <!-- Center -->
        <circle cx="190" cy="190" r="40" fill="rgba(61,31,92,0.6)" stroke="rgba(196,160,224,0.35)" stroke-width="1"/>
        <text x="190" y="186" text-anchor="middle" fill="rgba(243,239,248,0.9)" font-family="Georgia,serif" font-size="10" font-style="italic">I'MTEA</text>
        <text x="190" y="200" text-anchor="middle" fill="rgba(196,160,224,0.55)" font-family="monospace" font-size="6.5" letter-spacing="1">BLEND</text>

        <!-- Top: Purple Tea -->
        <circle cx="190" cy="50" r="28" fill="rgba(90,56,128,0.75)" stroke="rgba(196,160,224,0.35)" stroke-width="1"/>
        <text x="190" y="46" text-anchor="middle" fill="rgba(243,239,248,0.9)" font-family="Georgia,serif" font-size="7.5">Purple</text>
        <text x="190" y="58" text-anchor="middle" fill="rgba(243,239,248,0.7)" font-family="Georgia,serif" font-size="7.5">Tea</text>

        <!-- Right: Fennel -->
        <circle cx="330" cy="190" r="28" fill="rgba(42,82,40,0.75)" stroke="rgba(138,190,120,0.3)" stroke-width="1"/>
        <text x="330" y="194" text-anchor="middle" fill="rgba(243,239,248,0.9)" font-family="Georgia,serif" font-size="8.5">Fennel</text>

        <!-- Bottom: Ginger -->
        <circle cx="190" cy="330" r="28" fill="rgba(107,66,38,0.75)" stroke="rgba(196,160,224,0.3)" stroke-width="1"/>
        <text x="190" y="334" text-anchor="middle" fill="rgba(243,239,248,0.9)" font-family="Georgia,serif" font-size="8.5">Ginger</text>

        <!-- Left: Rosemary -->
        <circle cx="50" cy="190" r="28" fill="rgba(30,65,45,0.85)" stroke="rgba(74,128,64,0.4)" stroke-width="1"/>
        <text x="50" y="187" text-anchor="middle" fill="rgba(243,239,248,0.9)" font-family="Georgia,serif" font-size="7.5">Rose-</text>
        <text x="50" y="198" text-anchor="middle" fill="rgba(243,239,248,0.9)" font-family="Georgia,serif" font-size="7.5">mary</text>

        <!-- Corner labels -->
        <text x="272" y="108" text-anchor="middle" fill="rgba(196,160,224,0.4)" font-family="monospace" font-size="5.5" letter-spacing="1">ANTIOXIDANT</text>
        <text x="106" y="108" text-anchor="middle" fill="rgba(196,160,224,0.4)" font-family="monospace" font-size="5.5" letter-spacing="1">ANTIVIRAL</text>
        <text x="272" y="278" text-anchor="middle" fill="rgba(196,160,224,0.4)" font-family="monospace" font-size="5.5" letter-spacing="1">DIGESTIVE</text>
        <text x="106" y="278" text-anchor="middle" fill="rgba(196,160,224,0.4)" font-family="monospace" font-size="5.5" letter-spacing="1">ANTI-INFLAM</text>
      </svg>
    </div>
  </div>
</div>

<!-- ORDER FORM -->
<section id="order" class="order-section">
  <div class="order-header fade-up">
    <div class="section-label">Place Your Order</div>
    <h2 class="section-title">Ready to <em>begin?</em></h2>
    <p>We'll confirm &amp; follow up within 24 hours</p>
  </div>

  <div class="form-card fade-up" style="transition-delay:0.1s">
    <div id="form-wrap">
      <form id="order-form" novalidate>
        <div class="field-row">
          <div class="field">
            <label for="fname">First name</label>
            <input type="text" id="fname" placeholder="Jane" required>
          </div>
          <div class="field">
            <label for="lname">Last name</label>
            <input type="text" id="lname" placeholder="Smith" required>
          </div>
        </div>

        <div class="field">
          <label for="email">Email address</label>
          <input type="email" id="email" placeholder="jane@example.com" required>
        </div>

        <div class="field">
          <label for="qty">Quantity</label>
          <select id="qty">
            <option value="1">1 pouch — 50g · ~25 servings</option>
            <option value="2">2 pouches</option>
            <option value="3">3 pouches</option>
            <option value="6">6 pouches · best value</option>
          </select>
          <div class="price-note">Pricing confirmed on order review</div>
        </div>

        <div class="field">
          <label for="address">Shipping address</label>
          <input type="text" id="address" placeholder="Street address" required>
        </div>

        <div class="field-row">
          <div class="field">
            <label for="city">City</label>
            <input type="text" id="city" placeholder="City" required>
          </div>
          <div class="field">
            <label for="zip">Zip / Postcode</label>
            <input type="text" id="zip" placeholder="00000" required>
          </div>
        </div>

        <div class="field">
          <label for="notes">Notes (optional)</label>
          <textarea id="notes" rows="3" placeholder="Questions, gift notes, or special requests…"></textarea>
        </div>

        <div class="error-hint" id="error-hint">Please fill in all required fields.</div>
        <button type="submit" class="submit-btn">Send Order Request →</button>
      </form>
    </div>

    <div class="success-msg" id="success-msg">
      <div class="success-icon">
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
          <path d="M4 10l4 4 8-8" stroke="#C4A0E0" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
      <div class="success-title">Order <em>received.</em></div>
      <p class="success-body">Thank you! We'll be in touch within 24 hours to confirm your order and arrange payment.</p>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2025 I'MTEA &nbsp;·&nbsp; <a href="mailto:hello@imtea.com">hello@imtea.com</a></p>
</footer>

<script>
  // Sticky nav
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 60);
  });

  // Fade-up on scroll
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
  }, { threshold: 0.12 });
  document.querySelectorAll('.fade-up').forEach(el => obs.observe(el));

  // Form
  document.getElementById('order-form').addEventListener('submit', function(e) {
    e.preventDefault();
    const required = ['fname','lname','email','address','city','zip'];
    let valid = true;
    required.forEach(id => {
      const el = document.getElementById(id);
      if (!el.value.trim()) { el.style.borderColor = 'rgba(220,100,100,0.5)'; valid = false; }
      else { el.style.borderColor = ''; }
    });
    const hint = document.getElementById('error-hint');
    if (!valid) { hint.style.display = 'block'; return; }
    hint.style.display = 'none';
    document.getElementById('form-wrap').style.display = 'none';
    document.getElementById('success-msg').style.display = 'block';
  });
</script>
</body>
</html>
