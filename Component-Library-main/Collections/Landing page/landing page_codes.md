# Premium Landing Page Sections Code Database

This file contains the complete HTML, CSS, JS, and React snippets for premium landing page components/sections featured in the interactive showcase.

---

## Table of Contents
1. [Landing Page #1: Ambient Cyberpunk Hero Section](#landing-page-1-ambient-cyberpunk-hero-section)
2. [Landing Page #2: Glassmorphic Floating Header Navbar](#landing-page-2-glassmorphic-floating-header-navbar)
3. [Landing Page #3: Interactive Bento Features Grid](#landing-page-3-interactive-bento-features-grid)
4. [Landing Page #4: Testimonial Card slider](#landing-page-4-testimonial-card-slider)
5. [Landing Page #5: Interactive Tiered Pricing Table](#landing-page-5-interactive-tiered-pricing-table)
6. [Landing Page #6: Geometric Gradient CTA Banner](#landing-page-6-geometric-gradient-cta-banner)
7. [Landing Page #7: Scroll Video Background & Fixed Card Reveal](#landing-page-7-scroll-video-background--fixed-card-reveal)
8. [Landing Page #8: Liquid Glass Morphism Capabilites Showcase](#landing-page-8-liquid-glass-morphism-capabilites-showcase)

---

## Landing Page #1: Ambient Cyberpunk Hero Section

### HTML
```html
<section class="lp-hero">
    <div class="lp-hero-grid"></div>
    <div class="lp-hero-radial"></div>
    <div class="lp-hero-content">
        <div class="lp-hero-tag">ANTIGRAVITY v2.0 LAUNCH</div>
        <h1>Build Next-Gen Web Interfaces</h1>
        <p>A curated directory of highly-interactive CSS animations, premium layouts, and modular UI templates ready for modern web apps.</p>
        <div class="lp-hero-actions">
            <button class="lp-hero-btn-primary">Explore Showcases</button>
            <button class="lp-hero-btn-secondary">Read Docs</button>
        </div>
    </div>
</section>
```

### CSS
```css
.lp-hero {
    position: relative;
    width: 100%;
    min-height: 450px;
    background: #070a13;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 60px 24px;
    overflow: hidden;
    border-radius: 16px;
    border: 1px solid rgba(255, 255, 255, 0.05);
}

.lp-hero-grid {
    position: absolute;
    inset: 0;
    background-image: linear-gradient(rgba(99, 102, 241, 0.05) 1px, transparent 1px),
                      linear-gradient(90deg, rgba(99, 102, 241, 0.05) 1px, transparent 1px);
    background-size: 30px 30px;
    z-index: 1;
}

.lp-hero-radial {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 400px;
    height: 400px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.15) 0%, transparent 70%);
    z-index: 2;
    pointer-events: none;
}

.lp-hero-content {
    position: relative;
    z-index: 3;
    max-width: 650px;
    text-align: center;
}

.lp-hero-tag {
    display: inline-block;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    color: #818cf8;
    background: rgba(99, 102, 241, 0.12);
    border: 1px solid rgba(99, 102, 241, 0.25);
    padding: 6px 14px;
    border-radius: 30px;
    margin-bottom: 24px;
}

.lp-hero-content h1 {
    color: #ffffff;
    font-size: 2.5rem;
    font-weight: 800;
    line-height: 1.2;
    letter-spacing: -1px;
    margin-bottom: 16px;
}

.lp-hero-content p {
    color: #94a3b8;
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: 30px;
}

.lp-hero-actions {
    display: flex;
    gap: 16px;
    justify-content: center;
}

.lp-hero-btn-primary {
    background: #6366f1;
    color: #ffffff;
    border: none;
    padding: 12px 24px;
    border-radius: 8px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.lp-hero-btn-primary:hover {
    background: #4f46e5;
    box-shadow: 0 0 15px rgba(99, 102, 241, 0.4);
}

.lp-hero-btn-secondary {
    background: transparent;
    color: #cbd5e1;
    border: 1px solid rgba(255, 255, 255, 0.15);
    padding: 12px 24px;
    border-radius: 8px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.lp-hero-btn-secondary:hover {
    background: rgba(255, 255, 255, 0.05);
    color: #ffffff;
    border-color: rgba(255, 255, 255, 0.3);
}
```

---

## Landing Page #2: Glassmorphic Floating Header Navbar

### HTML
```html
<header class="lp-navbar-wrapper">
    <div class="lp-navbar">
        <div class="lp-navbar-logo">
            <span class="lp-logo-dot"></span>
            <span>AETHER</span>
        </div>
        <nav class="lp-navbar-links">
            <a href="#" class="active" onclick="event.preventDefault()">Features</a>
            <a href="#" onclick="event.preventDefault()">Showcase</a>
            <a href="#" onclick="event.preventDefault()">Pricing</a>
        </nav>
        <button class="lp-navbar-cta">Get Started</button>
    </div>
</header>
```

### CSS
```css
.lp-navbar-wrapper {
    width: 100%;
    padding: 12px;
}

.lp-navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(15, 23, 42, 0.6);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 50px;
    padding: 8px 24px;
    max-width: 900px;
    margin: 0 auto;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

.lp-navbar-logo {
    display: flex;
    align-items: center;
    gap: 8px;
    color: #ffffff;
    font-weight: 700;
    font-size: 0.95rem;
    letter-spacing: 1px;
}

.lp-logo-dot {
    width: 8px;
    height: 8px;
    background: #10b981;
    border-radius: 50%;
    box-shadow: 0 0 8px #10b981;
}

.lp-navbar-links {
    display: flex;
    gap: 20px;
}

.lp-navbar-links a {
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 500;
    transition: color 0.3s;
    position: relative;
    padding: 4px 0;
}

.lp-navbar-links a:hover, 
.lp-navbar-links a.active {
    color: #ffffff;
}

.lp-navbar-links a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    width: 0;
    height: 2px;
    background: #10b981;
    transition: width 0.3s ease, left 0.3s ease;
}

.lp-navbar-links a:hover::after, 
.lp-navbar-links a.active::after {
    width: 100%;
    left: 0;
}

.lp-navbar-cta {
    background: #ffffff;
    color: #0f172a;
    border: none;
    padding: 8px 18px;
    border-radius: 30px;
    font-size: 0.8rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.lp-navbar-cta:hover {
    background: #e2e8f0;
    transform: scale(1.02);
}
```

---

## Landing Page #3: Interactive Bento Features Grid

### HTML
```html
<div class="lp-bento-grid">
    <div class="bento-card bento-wide">
        <div class="bento-icon">&#9889;</div>
        <h3>Ultra High Performance</h3>
        <p>Optimized with pre-compiled templates, fast-loading stylesheets, and zero initial bundle overhead.</p>
    </div>
    <div class="bento-card">
        <div class="bento-icon">&#128274;</div>
        <h3>Secure Sandbox</h3>
        <p>Built with safe standards.</p>
    </div>
    <div class="bento-card">
        <div class="bento-icon">&#128173;</div>
        <h3>AI Integration</h3>
        <p>Automate custom generation.</p>
    </div>
</div>
```

### CSS
```css
.lp-bento-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
    width: 100%;
    max-width: 800px;
    margin: 0 auto;
}

.bento-card {
    background: #0f172a;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    padding: 20px;
    transition: all 0.3s;
    text-align: left;
}

.bento-card:hover {
    transform: translateY(-4px);
    border-color: rgba(255, 255, 255, 0.15);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.bento-wide {
    grid-column: span 2;
}

.bento-icon {
    font-size: 1.5rem;
    margin-bottom: 12px;
}

.bento-card h3 {
    color: #ffffff;
    font-size: 1.05rem;
    font-weight: 600;
    margin-bottom: 6px;
}

.bento-card p {
    color: #94a3b8;
    font-size: 0.85rem;
    line-height: 1.5;
}
```

---

## Landing Page #4: Testimonial Card slider

### HTML
```html
<div class="lp-testimonial">
    <div class="testimonial-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
    <p class="testimonial-quote">"This component library saved us dozens of development hours. The animations are clean, fluid, and optimized right out of the box."</p>
    <div class="testimonial-author">
        <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=80&auto=format&fit=crop&q=80" alt="Avatar">
        <div class="author-info">
            <span class="author-name">Marcus Vance</span>
            <span class="author-title">VP of Product at Aetheric</span>
        </div>
    </div>
</div>
```

### CSS
```css
.lp-testimonial {
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 20px;
    padding: 28px;
    width: 100%;
    max-width: 480px;
    margin: 0 auto;
    text-align: left;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}

.testimonial-stars {
    color: #fbbf24;
    font-size: 1rem;
    margin-bottom: 16px;
}

.testimonial-quote {
    color: #e5e7eb;
    font-size: 0.95rem;
    font-style: italic;
    line-height: 1.6;
    margin-bottom: 20px;
}

.testimonial-author {
    display: flex;
    align-items: center;
    gap: 12px;
}

.testimonial-author img {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    object-fit: cover;
}

.author-info {
    display: flex;
    flex-direction: column;
}

.author-name {
    color: #ffffff;
    font-size: 0.88rem;
    font-weight: 600;
}

.author-title {
    color: #9ca3af;
    font-size: 0.75rem;
}
```

---

## Landing Page #5: Interactive Tiered Pricing Table

### HTML
```html
<div class="lp-pricing">
    <div class="pricing-card popular">
        <div class="pricing-badge">MOST POPULAR</div>
        <span class="pricing-plan">Pro Tier</span>
        <div class="pricing-price">
            <span class="price-val">$49</span>
            <span class="price-period">/ month</span>
        </div>
        <ul class="pricing-features">
            <li>&#10003; Access to all 100+ components</li>
            <li>&#10003; Lifetime free updates</li>
            <li>&#10003; Advanced JS widgets</li>
            <li>&#10003; Priority support</li>
        </ul>
        <button class="pricing-btn">Upgrade Plan</button>
    </div>
</div>
```

### CSS
```css
.lp-pricing {
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 10px;
}

.pricing-card {
    position: relative;
    width: 290px;
    background: #0f172a;
    border: 1px solid rgba(99, 102, 241, 0.25);
    border-radius: 16px;
    padding: 28px 20px;
    text-align: left;
    box-shadow: 0 10px 30px rgba(99, 102, 241, 0.1);
}

.pricing-badge {
    position: absolute;
    top: -12px;
    left: 50%;
    transform: translateX(-50%);
    background: #6366f1;
    color: white;
    font-size: 9px;
    font-weight: 700;
    padding: 4px 10px;
    border-radius: 20px;
    letter-spacing: 1px;
}

.pricing-plan {
    color: #94a3b8;
    font-size: 0.8rem;
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 0.5px;
}

.pricing-price {
    margin: 12px 0 20px 0;
    display: flex;
    align-items: baseline;
}

.price-val {
    color: #ffffff;
    font-size: 2.2rem;
    font-weight: 800;
}

.price-period {
    color: #94a3b8;
    font-size: 0.85rem;
    margin-left: 4px;
}

.pricing-features {
    list-style: none;
    margin-bottom: 24px;
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.pricing-features li {
    color: #cbd5e1;
    font-size: 0.82rem;
}

.pricing-btn {
    width: 100%;
    background: #6366f1;
    color: white;
    border: none;
    padding: 10px 0;
    border-radius: 8px;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.3s;
}

.pricing-btn:hover {
    background: #4f46e5;
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.4);
}
```

---

## Landing Page #6: Geometric Gradient CTA Banner

### HTML
```html
<section class="lp-cta">
    <div class="lp-cta-glow"></div>
    <div class="lp-cta-content">
        <h2>Unleash Premium Designs Today</h2>
        <p>Integrate modern responsive visual effects and component packages directly into your codebase in seconds.</p>
        <div class="lp-cta-input-group">
            <input type="email" placeholder="Enter your email" aria-label="Email address for subscription">
            <button class="lp-cta-btn">Join Newsletter</button>
        </div>
    </div>
</section>
```

### CSS
```css
.lp-cta {
    position: relative;
    width: 100%;
    background: linear-gradient(135deg, #1e1b4b, #030712);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 20px;
    padding: 40px 24px;
    overflow: hidden;
    text-align: center;
}

.lp-cta-glow {
    position: absolute;
    bottom: -100px;
    right: -100px;
    width: 250px;
    height: 250px;
    background: radial-gradient(circle, rgba(236, 72, 153, 0.15) 0%, transparent 70%);
    pointer-events: none;
}

.lp-cta-content {
    position: relative;
    z-index: 2;
    max-width: 500px;
    margin: 0 auto;
}

.lp-cta-content h2 {
    color: #ffffff;
    font-size: 1.8rem;
    font-weight: 700;
    margin-bottom: 8px;
}

.lp-cta-content p {
    color: #cbd5e1;
    font-size: 0.9rem;
    line-height: 1.5;
    margin-bottom: 24px;
}

.lp-cta-input-group {
    display: flex;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 30px;
    padding: 4px;
    max-width: 400px;
    margin: 0 auto;
}

.lp-cta-input-group input {
    flex: 1;
    background: transparent;
    border: none;
    outline: none;
    color: white;
    padding: 0 16px;
    font-size: 0.85rem;
}

.lp-cta-input-group input::placeholder {
    color: #64748b;
}

.lp-cta-btn {
    background: #ec4899;
    color: white;
    border: none;
    border-radius: 25px;
    padding: 8px 18px;
    font-size: 0.8rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.lp-cta-btn:hover {
    background: #db2777;
    box-shadow: 0 0 10px rgba(236, 72, 153, 0.4);
}
```

---

## Landing Page #7: Scroll Video Background & Fixed Card Reveal

### HTML
```html
<!-- Scroll Video Background Section Mockup -->
<div class="veldara-scroll-showcase">
  <!-- Scroll Video Background Container -->
  <div id="scroll-video-container">
    <canvas id="video-canvas"></canvas>
    <video id="video-fallback" muted playsinline preload="auto" crossorigin="anonymous"
      src="https://d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/hf_20260616_212935_bbf608da-62d1-4f25-9be4-c346e4d09cc8.mp4"
    ></video>
    <div class="overlay"></div>
  </div>

  <!-- Particles Overlay -->
  <canvas id="particles-canvas"></canvas>

  <!-- Fixed Reveal Cards -->
  <div id="fixed-cards">
    <div class="grid">
      <div class="card">
        <h3>Explore Veldara</h3>
        <p>Veldara merges Svelte 5 and Three.js seamlessly. Composable, fast, and simple to grasp.</p>
      </div>
      <div class="card">
        <h3>Unlock Three.js</h3>
        <p>A declarative API designed specifically to scale gorgeous 3D canvas layouts performantly.</p>
      </div>
      <div class="card">
        <h3>Connect Everything</h3>
        <p>Comes with standard packages for physics, XR, layout mesh positioning, and advanced asset loading.</p>
      </div>
    </div>
  </div>

  <!-- Main Hero Layout -->
  <div id="content">
    <section id="hero">
      <div class="gradient-overlay"></div>
      <div class="content">
        <p class="subtitle">Our Purpose:</p>
        <h1>
          Instantly craft immersive
          <span class="underlined"><span class="line"></span><span>3D worlds</span></span>
          on the web.
        </h1>
        <div class="ctas">
          <div class="code-box">
            <span class="prompt">&gt;</span>
            <code>npm i @veldara/core</code>
          </div>
          <a href="#" class="cta-btn" onclick="event.preventDefault()">Get Started <span>&rarr;</span></a>
        </div>
      </div>
    </section>

    <!-- Trigger Spacer Zone -->
    <div id="cards-trigger" style="height:120vh;"></div>

    <section id="section-three">
      <div class="inner" id="section-three-inner">
        <p>Presenting</p>
        <h2>Veldara 8</h2>
      </div>
    </section>
  </div>
</div>
```

### CSS
```css
/* Scroll Video Showcase */
.veldara-scroll-showcase {
  position: relative;
  width: 100%;
  background: #010101;
  color: #fff;
  overflow: hidden;
  border-radius: 20px;
}
#scroll-video-container {
  position: absolute; inset: 0; z-index: 1;
  background: #0a0a0a;
}
#scroll-video-container canvas,
#scroll-video-container video {
  position: absolute; inset: 0; width: 100%; height: 100%; object-fit: cover;
}
#scroll-video-container .overlay { position: absolute; inset: 0; background: rgba(0,0,0,0.3); }

#particles-canvas {
  position: absolute; inset: 0; width: 100%; height: 100%;
  pointer-events: none; z-index: 3;
}

#fixed-cards {
  position: absolute; bottom: 10%; left: 0; right: 0; z-index: 4;
  padding: 2rem; opacity: 0; pointer-events: none;
  transition: opacity 0.3s;
}
#fixed-cards .grid {
  max-width: 72rem; margin: 0 auto;
  display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem;
}
#fixed-cards .card {
  background: rgba(10, 10, 10, 0.7);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 12px;
  padding: 20px;
}
#fixed-cards .card h3 { font-size: 1.15rem; font-weight: 700; color: #fff; margin-bottom: 0.5rem; }
#fixed-cards .card p { color: #d1d5db; font-size: 0.8rem; line-height: 1.5; }

#content { position: relative; z-index: 2; }
#hero {
  position: relative; height: 100vh; width: 100%; display: flex; flex-direction: column;
}
#hero .content {
  position: relative; z-index: 10; flex: 1; display: flex; flex-direction: column;
  align-items: center; justify-content: flex-end; text-align: center;
  padding: 0 1rem 4rem;
}
#hero .subtitle { font-size: 0.8rem; color: #9ca3af; margin-bottom: 0.5rem; letter-spacing: 0.05em; }
#hero h1 { font-size: 2.2rem; font-weight: 600; line-height: 1.2; max-width: 40rem; }
#hero h1 .underlined { position: relative; display: inline-block; }
#hero h1 .underlined .line {
  position: absolute; bottom: 0.2rem; left: 0; width: 100%; height: 6px;
  background: #2C5C88; border-radius: 2px;
}
#hero h1 .underlined span { position: relative; }
#hero .ctas {
  display: flex; align-items: center; gap: 0.8rem; margin-top: 1.5rem; flex-wrap: wrap; justify-content: center;
}
#hero .code-box {
  display: flex; align-items: center; gap: 0.5rem;
  background: #1a1a1a; border: 1px solid rgba(55,65,81,0.5);
  border-radius: 0.5rem; padding: 0.5rem 1rem;
}
#hero .code-box code { font-size: 0.78rem; color: #e5e7eb; font-family: monospace; }
#hero .cta-btn {
  background: #2C5C88; color: #fff; border-radius: 0.5rem;
  padding: 0.5rem 1.25rem; font-size: 0.8rem; text-decoration: none;
}

#section-three {
  position: relative; min-height: 100vh; display: flex; align-items: center;
  justify-content: center; padding-bottom: 4rem;
}
#section-three .inner {
  text-align: center; opacity: 0; transform: translateY(20px);
  transition: opacity 1s, transform 1s;
}
#section-three .inner.visible { opacity: 1; transform: translateY(0); }
#section-three .inner h2 { font-size: 3rem; font-weight: 700; }
```

### JavaScript
```javascript
// --- VIDEO FRAME EXTRACTOR & SCROLL PAINTER ---
const canvas = document.getElementById('video-canvas');
const videoEl = document.getElementById('video-fallback');
const ctx = canvas?.getContext('2d');
if (canvas && videoEl) {
  let progress = 0;
  window.addEventListener('scroll', () => {
    const scrollable = document.documentElement.scrollHeight - window.innerHeight;
    progress = scrollable > 0 ? window.scrollY / scrollable : 0;
    if (videoEl.duration) {
      videoEl.currentTime = progress * videoEl.duration;
    }
  });

  videoEl.addEventListener('seeked', () => {
    ctx.drawImage(videoEl, 0, 0, canvas.width, canvas.height);
  });
}
```

---

## Landing Page #8: Liquid Glass Morphism Capabilites Showcase

### React
```tsx
import React from 'react';
import { motion, useInView } from 'framer-motion';

// --- LIQUID GLASS CSS CLASS EXTENSIONS IN INDEX.CSS ---
// .liquid-glass {
//   background: rgba(255, 255, 255, 0.01);
//   backdrop-filter: blur(4px);
//   box-shadow: inset 0 1px 1px rgba(255,255,255,0.1);
//   position: relative;
//   overflow: hidden;
// }
// ...

    </div>
  );
};
```

---

## Landing Page #9: Scale with Flexible Pricing

### HTML
```html
<div class="pricing-scale-showcase">
  <div class="flex flex-col items-center text-center mb-16">
    <div class="pricing-badge-accent">
      <div class="pricing-pulse-dot"></div>
      <span>Pricing</span>
    </div>
    <h2>Scale with flexible pricing</h2>
    <p>Choose a plan that grows with your data needs and unlocks the intelligence your team deserves.</p>
  </div>
  <div class="pricing-grid">
    <!-- Starter -->
    <article class="price-box">
      <div class="price-box-header">
        <span>01</span>
        <div class="setup-badge">2 weeks setup</div>
      </div>
      <h3>Starter</h3>
      <p class="desc">Perfect for small teams getting started with data-driven insights.</p>
      <div class="price-value">$299<span>/month</span></div>
      <button class="pricing-btn">Get Started &rarr;</button>
      <ul class="pricing-features">
        <li>✔ Up to 10K tracked events</li>
        <li>✔ Basic attribution modeling</li>
        <li>✔ 5 integrations included</li>
      </ul>
    </article>
    <!-- Pro -->
    <article class="price-box featured">
      <div class="price-box-header">
        <span class="active-badge">02</span>
        <div class="setup-badge active">1 week setup</div>
      </div>
      <h3>Professional</h3>
      <p class="desc">Advanced analytics for growing teams and scale-ready insights.</p>
      <div class="price-value">$799<span>/month</span></div>
      <button class="pricing-btn active">Start Professional</button>
      <ul class="pricing-features">
        <li>✔ Everything in Starter</li>
        <li>✔ AI predictive insights</li>
        <li>✔ Unlimited integrations</li>
      </ul>
    </article>
  </div>
</div>
```

### CSS
```css
.pricing-scale-showcase {
  width: 100%;
  max-width: 900px;
  margin: 0 auto;
  padding: 40px 20px;
}
.pricing-badge-accent {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(16, 185, 129, 0.1);
  border: 1px solid rgba(16, 185, 129, 0.2);
  color: #34d399;
  padding: 6px 16px;
  border-radius: 30px;
  font-size: 0.75rem;
  font-weight: 600;
  margin-bottom: 20px;
}
.pricing-pulse-dot {
  width: 6px;
  height: 6px;
  background: #34d399;
  border-radius: 50%;
  animation: pulse 1.5s infinite;
}
.pricing-scale-showcase h2 {
  font-size: 2.2rem;
  font-weight: 300;
  color: #fff;
  margin-bottom: 12px;
}
.pricing-scale-showcase p {
  color: rgba(255, 255, 255, 0.7);
  font-size: 0.95rem;
  max-width: 550px;
  margin: 0 auto 40px;
}
.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
}
.price-box {
  background: linear-gradient(to bottom, #0f1419, #0a0f14);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 24px;
  padding: 28px;
  transition: all 0.3s;
}
.price-box:hover {
  border-color: rgba(16, 185, 129, 0.2);
  box-shadow: 0 15px 35px rgba(16, 185, 129, 0.06);
}
.price-box.featured {
  border-color: rgba(16, 185, 129, 0.3);
  box-shadow: 0 15px 35px rgba(16, 185, 129, 0.1);
  transform: scale(1.02);
}
.price-box-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
.setup-badge {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  color: rgba(255, 255, 255, 0.7);
  font-size: 0.7rem;
  padding: 4px 8px;
  border-radius: 6px;
}
.setup-badge.active {
  background: rgba(16, 185, 129, 0.15);
  border-color: rgba(16, 185, 129, 0.3);
  color: #34d399;
}
.price-box h3 {
  font-size: 1.4rem;
  color: white;
  margin-bottom: 8px;
  font-weight: 400;
}
.price-box .desc {
  font-size: 0.8rem;
  color: rgba(255,255,255,0.5);
  line-height: 1.4;
  margin-bottom: 20px;
}
.price-value {
  font-size: 2rem;
  font-weight: 500;
  color: white;
  margin-bottom: 20px;
}
.price-value span {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.4);
}
.pricing-btn {
  width: 100%;
  background: rgba(255, 255, 255, 0.05);
  color: white;
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 12px;
  padding: 10px;
  font-weight: 600;
  cursor: pointer;
  margin-bottom: 24px;
}
.pricing-btn.active {
  background: linear-gradient(135deg, #10b981, #059669);
  border: none;
  box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);
}
.pricing-features {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.pricing-features li {
  font-size: 0.8rem;
  color: rgba(255,255,255,0.8);
}
@keyframes pulse {
  0% { transform: scale(1); opacity: 1; }
  50% { transform: scale(1.4); opacity: 0.4; }
  100% { transform: scale(1); opacity: 1; }
}
```

---

## Landing Page #10: Ready to Collaborate Contact

### HTML
```html
<section class="collaborate-section">
  <div class="inner-wrap">
    <div class="collab-header">
      <span class="badge-collab">Let's Work Together</span>
      <h2>Ready to <span class="highlight">collaborate?</span></h2>
      <p>Whether you need help with product design, strategy, or education, I'm here to help bring your vision to life.</p>
    </div>
    <div class="collab-grid">
      <!-- Contact Form -->
      <div class="form-container">
        <h3>Send a Message</h3>
        <form onsubmit="event.preventDefault()">
          <div class="row">
            <input type="text" placeholder="Your name">
            <input type="email" placeholder="your@email.com">
          </div>
          <select>
            <option>$5k - $10k</option>
            <option>$10k - $25k</option>
            <option>$25k - $50k</option>
            <option>$50k+</option>
          </select>
          <textarea rows="4" placeholder="Tell me about your project..."></textarea>
          <button type="submit" class="submit-btn">Send Message &rarr;</button>
        </form>
      </div>
      <!-- Info Cards -->
      <div class="info-stack">
        <div class="info-card">
          <h4>Email</h4>
          <p>hello@designer.com</p>
        </div>
        <div class="info-card">
          <h4>Schedule a Call</h4>
          <p>Book a free consultation</p>
        </div>
      </div>
    </div>
  </div>
</section>
```

### CSS
```css
.collaborate-section {
  width: 100%;
  background: #050505;
  border-radius: 20px;
  padding: 60px 24px;
  border: 1px solid rgba(255,255,255,0.05);
}
.inner-wrap {
  max-width: 900px;
  margin: 0 auto;
}
.collab-header {
  text-align: center;
  margin-bottom: 40px;
}
.badge-collab {
  display: inline-block;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.1);
  color: white;
  padding: 6px 14px;
  border-radius: 30px;
  font-size: 0.75rem;
  margin-bottom: 16px;
}
.collab-header h2 {
  font-size: 2.2rem;
  color: white;
}
.collab-header .highlight {
  font-family: serif;
  font-style: italic;
  color: #ccc;
}
.collab-header p {
  color: #888;
  font-size: 0.9rem;
  max-width: 500px;
  margin: 12px auto 0;
}
.collab-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}
.form-container {
  background: rgba(255,255,255,0.02);
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 16px;
  padding: 24px;
}
.form-container h3 {
  font-size: 1.1rem;
  color: white;
  margin-bottom: 20px;
}
.form-container form {
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.form-container .row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}
.form-container input, .form-container select, .form-container textarea {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 8px;
  padding: 10px;
  color: white;
  font-size: 0.8rem;
  outline: none;
}
.form-container input:focus, .form-container select:focus, .form-container textarea:focus {
  border-color: rgba(255,255,255,0.3);
}
.submit-btn {
  background: white;
  color: black;
  border: none;
  padding: 12px;
  border-radius: 8px;
  font-weight: 600;
  cursor: pointer;
}
.info-stack {
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.info-card {
  background: rgba(255,255,255,0.02);
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 12px;
  padding: 20px;
}
.info-card h4 {
  font-size: 0.85rem;
  color: #888;
  margin-bottom: 6px;
}
.info-card p {
  font-size: 1.05rem;
  color: white;
  font-weight: 500;
}
```
