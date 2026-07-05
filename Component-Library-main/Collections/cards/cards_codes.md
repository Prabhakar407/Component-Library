# Premium Custom Card Code Database

This file contains the complete, self-contained HTML, CSS, JS, and React snippets for the premium card components featured in the showcase.

---

## Table of Contents
1. [Card #1: Neon Cyberpunk Glowing Card](#card-1-neon-cyberpunk-glowing-card)
2. [Card #2: Glassmorphic Floating Card](#card-2-glassmorphic-floating-card)
3. [Card #3: 3D Perspective Tilt Card](#card-3-3d-perspective-tilt-card)
4. [Card #4: E-Commerce Product Spotlight Card](#card-4-e-commerce-product-spotlight-card)
5. [Card #5: Dynamic Gradient Mesh Card](#card-5-dynamic-gradient-mesh-card)
6. [Card #6: Minimalistic Article Card with Progress Bar](#card-6-minimalistic-article-card-with-progress-bar)
7. [Card #7: 3D Stack Carousel Hero](#card-7-3d-stack-carousel-hero)
8. [Card #8: Circular 3D Gallery](#card-8-circular-3d-gallery)
9. [Card #9: Elastic Fan Social Cards](#card-9-elastic-fan-social-cards)
10. [Card #10: MagicUI Infinite Review Marquee](#card-10-magicui-infinite-review-marquee)
11. [Card #11: Volumetric 3D Interactive Cylinder Cards](#card-11-volumetric-3d-interactive-cylinder-cards)
12. [Card #12: Home Essentials Grid](#card-12-home-essentials-grid)
13. [Card #13: Vaultic Interactive Pricing Card](#card-13-vaultic-interactive-pricing-card)
14. [Card #14: Spring Physics Card Stack](#card-14-spring-physics-card-stack)
15. [Card #15: MUI Joy UI Gradient Cover Card](#card-15-mui-joy-ui-gradient-cover-card)

---

## Card #1: Neon Cyberpunk Glowing Card

### HTML
```html
<div class="card-neon">
    <div class="card-neon-glow"></div>
    <div class="card-neon-content">
        <span class="card-neon-tag">SYSTEM OK</span>
        <h3>Mainframe Interface</h3>
        <p>Access the core systems, modify permissions, and monitor cluster workloads in real-time.</p>
        <button class="card-neon-btn">Initialize Terminal</button>
    </div>
</div>
```

### CSS
```css
.card-neon {
    position: relative;
    width: 320px;
    background: #0d111a;
    border: 1px solid rgba(99, 102, 241, 0.2);
    border-radius: 16px;
    padding: 24px;
    overflow: hidden;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    transition: all 0.3s ease;
}

.card-neon:hover {
    transform: translateY(-5px);
    border-color: #6366f1;
    box-shadow: 0 15px 40px rgba(99, 102, 241, 0.25);
}

.card-neon-glow {
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.15) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
    transition: all 0.5s ease;
}

.card-neon:hover .card-neon-glow {
    background: radial-gradient(circle, rgba(99, 102, 241, 0.25) 0%, transparent 50%);
}

.card-neon-content {
    position: relative;
    z-index: 1;
}

.card-neon-tag {
    display: inline-block;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 1.5px;
    color: #6366f1;
    border: 1px solid rgba(99, 102, 241, 0.3);
    background: rgba(99, 102, 241, 0.1);
    padding: 4px 8px;
    border-radius: 4px;
    margin-bottom: 16px;
}

.card-neon-content h3 {
    color: #ffffff;
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 8px;
}

.card-neon-content p {
    color: #94a3b8;
    font-size: 0.9rem;
    line-height: 1.5;
    margin-bottom: 20px;
}

.card-neon-btn {
    background: transparent;
    color: #6366f1;
    border: 1px solid #6366f1;
    padding: 8px 16px;
    border-radius: 6px;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
}

.card-neon-btn:hover {
    background: #6366f1;
    color: #ffffff;
    box-shadow: 0 0 15px rgba(99, 102, 241, 0.5);
}
```

---

## Card #2: Glassmorphic Floating Card

### HTML
```html
<div class="card-glass">
    <div class="card-glass-sheen"></div>
    <div class="card-glass-circle-1"></div>
    <div class="card-glass-circle-2"></div>
    <div class="card-glass-body">
        <div class="card-glass-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <polygon points="12 2 2 7 12 12 22 7 12 2"></polygon>
                <polyline points="2 17 12 22 22 17"></polyline>
                <polyline points="2 12 12 17 22 12"></polyline>
            </svg>
        </div>
        <h3>Glass Layers</h3>
        <p>Premium card effect with frosted background, subtle border glow, and floating background shapes.</p>
        <a href="#" class="card-glass-link">Explore Details &rarr;</a>
    </div>
</div>
```

### CSS
```css
.card-glass {
    position: relative;
    width: 320px;
    height: auto;
    border-radius: 20px;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    padding: 24px;
    overflow: hidden;
    transition: all 0.4s ease;
}

.card-glass:hover {
    transform: translateY(-8px);
    border-color: rgba(255, 255, 255, 0.2);
    box-shadow: 0 12px 40px 0 rgba(0, 0, 0, 0.5);
}

.card-glass-sheen {
    position: absolute;
    top: 0;
    left: -150%;
    width: 50%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.15), transparent);
    transform: skewX(-20deg);
    transition: 0.8s;
}

.card-glass:hover .card-glass-sheen {
    left: 150%;
}

.card-glass-body {
    position: relative;
    z-index: 2;
}

.card-glass-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    background: rgba(255, 255, 255, 0.08);
    border: 1px solid rgba(255, 255, 255, 0.15);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #ffffff;
    margin-bottom: 20px;
}

.card-glass-body h3 {
    color: #ffffff;
    font-size: 1.3rem;
    font-weight: 600;
    margin-bottom: 10px;
}

.card-glass-body p {
    color: #cbd5e1;
    font-size: 0.9rem;
    line-height: 1.6;
    margin-bottom: 24px;
}

.card-glass-link {
    color: #38bdf8;
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 500;
    transition: color 0.3s;
}

.card-glass-link:hover {
    color: #bae6fd;
}
```

---

## Card #3: 3D Perspective Tilt Card

### HTML
```html
<div class="card-tilt" id="tiltCard">
    <div class="card-tilt-inner">
        <div class="card-tilt-badge">NEW</div>
        <div class="card-tilt-logo">
            <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="10"></circle>
                <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path>
                <path d="M2 12h20"></path>
            </svg>
        </div>
        <h3>3D Matrix Perspective</h3>
        <p>Interactive tilt physics mapped directly to your mouse coordinates. Experience true depth.</p>
    </div>
</div>
```

### CSS
```css
.card-tilt {
    width: 320px;
    height: 220px;
    perspective: 1000px;
    cursor: pointer;
}

.card-tilt-inner {
    position: relative;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #1e293b, #0f172a);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 20px;
    padding: 24px;
    transform-style: preserve-3d;
    transition: transform 0.15s ease-out;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.card-tilt-badge {
    position: absolute;
    top: 20px;
    right: 20px;
    background: #ec4899;
    color: #ffffff;
    font-size: 10px;
    font-weight: 700;
    padding: 4px 8px;
    border-radius: 4px;
    transform: translateZ(30px);
}

.card-tilt-logo {
    color: #ec4899;
    margin-bottom: 16px;
    transform: translateZ(40px);
}

.card-tilt-inner h3 {
    color: #ffffff;
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 8px;
    transform: translateZ(35px);
}

.card-tilt-inner p {
    color: #94a3b8;
    font-size: 0.9rem;
    line-height: 1.5;
    transform: translateZ(20px);
}
```

### JavaScript
```javascript
const el = document.getElementById('tiltCard');
if (el) {
    const inner = el.querySelector('.card-tilt-inner');
    el.addEventListener('mousemove', (e) => {
        const rect = el.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        const xc = rect.width / 2;
        const yc = rect.height / 2;
        const angleX = (yc - y) / 10;
        const angleY = (x - xc) / 10;
        inner.style.transform = `rotateX(${angleX}deg) rotateY(${angleY}deg)`;
    });
    
    el.addEventListener('mouseleave', () => {
        inner.style.transform = 'rotateX(0) rotateY(0)';
    });
}
```

---

## Card #4: E-Commerce Product Spotlight Card

### HTML
```html
<div class="product-card">
    <div class="product-img-wrapper">
        <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=600&auto=format&fit=crop&q=80" alt="Sport Sneaker">
        <div class="product-tag">SALE</div>
    </div>
    <div class="product-details">
        <span class="product-category">Athletic Footwear</span>
        <h3>Velocity X1 Sneaker</h3>
        <div class="product-rating">
            <span class="stars">&#9733;&#9733;&#9733;&#9733;&#9734;</span>
            <span class="reviews">(48 reviews)</span>
        </div>
        <div class="product-footer">
            <div class="product-price">
                <span class="price-old">$180.00</span>
                <span class="price-current">$129.99</span>
            </div>
            <button class="product-btn" aria-label="Add Sneaker to Cart">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <circle cx="9" cy="21" r="1"></circle>
                    <circle cx="20" cy="21" r="1"></circle>
                    <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
                </svg>
            </button>
        </div>
    </div>
</div>
```

### CSS
```css
.product-card {
    width: 320px;
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    overflow: hidden;
    transition: all 0.3s ease;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
}

.product-card:hover {
    transform: translateY(-6px);
    border-color: rgba(255, 255, 255, 0.15);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
}

.product-img-wrapper {
    position: relative;
    height: 180px;
    overflow: hidden;
    background: #1f2937;
}

.product-img-wrapper img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.5s ease;
}

.product-card:hover .product-img-wrapper img {
    transform: scale(1.1);
}

.product-tag {
    position: absolute;
    top: 12px;
    left: 12px;
    background: #ef4444;
    color: white;
    font-size: 10px;
    font-weight: 700;
    padding: 4px 8px;
    border-radius: 4px;
}

.product-details {
    padding: 20px;
}

.product-category {
    font-size: 0.75rem;
    color: #9ca3af;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.product-details h3 {
    color: #ffffff;
    font-size: 1.15rem;
    margin: 6px 0 8px 0;
    font-weight: 600;
}

.product-rating {
    display: flex;
    align-items: center;
    gap: 6px;
    margin-bottom: 16px;
}

.product-rating .stars {
    color: #fbbf24;
    font-size: 0.9rem;
}

.product-rating .reviews {
    color: #6b7280;
    font-size: 0.8rem;
}

.product-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.product-price {
    display: flex;
    flex-direction: column;
}

.price-old {
    text-decoration: line-through;
    color: #6b7280;
    font-size: 0.8rem;
}

.price-current {
    color: #10b981;
    font-size: 1.2rem;
    font-weight: 700;
}

.product-btn {
    background: #10b981;
    color: white;
    border: none;
    width: 38px;
    height: 38px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
}

.product-btn:hover {
    background: #059669;
    box-shadow: 0 0 10px rgba(16, 185, 129, 0.4);
    transform: scale(1.05);
}
```

---

## Card #5: Dynamic Gradient Mesh Card

### HTML
```html
<div class="card-mesh">
    <div class="card-mesh-bg"></div>
    <div class="card-mesh-overlay"></div>
    <div class="card-mesh-content">
        <h3>Gradient Mesh</h3>
        <p>A beautiful aesthetic combining glowing CSS linear and radial gradients moving dynamically beneath a blur mask.</p>
        <div class="card-mesh-action">
            <span>Discover Pattern</span>
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="5" y1="12" x2="19" y2="12"></line>
                <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
        </div>
    </div>
</div>
```

### CSS
```css
.card-mesh {
    position: relative;
    width: 320px;
    height: 220px;
    border-radius: 16px;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.08);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
    display: flex;
    align-items: flex-end;
    cursor: pointer;
    transition: transform 0.3s ease, border-color 0.3s ease;
}

.card-mesh:hover {
    transform: translateY(-5px);
    border-color: rgba(255, 255, 255, 0.18);
}

.card-mesh-bg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 1;
    background: linear-gradient(45deg, #1e1b4b, #311042);
}

.card-mesh-bg::before {
    content: '';
    position: absolute;
    top: -20%;
    left: -20%;
    width: 140%;
    height: 140%;
    background: radial-gradient(circle, #ec4899 0%, transparent 60%);
    opacity: 0.6;
    animation: mesh-glow 8s ease infinite;
}

.card-mesh-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 2;
    background: rgba(10, 10, 20, 0.4);
    backdrop-filter: blur(12px);
}

.card-mesh-content {
    position: relative;
    z-index: 3;
    padding: 24px;
    width: 100%;
}

.card-mesh-content h3 {
    color: #ffffff;
    font-size: 1.25rem;
    margin-bottom: 8px;
    font-weight: 600;
}

.card-mesh-content p {
    color: #cbd5e1;
    font-size: 0.9rem;
    line-height: 1.5;
    margin-bottom: 16px;
}

.card-mesh-action {
    display: flex;
    align-items: center;
    gap: 8px;
    color: #f472b6;
    font-size: 0.85rem;
    font-weight: 600;
    transition: gap 0.3s;
}

.card-mesh:hover .card-mesh-action {
    gap: 12px;
}

@keyframes mesh-glow {
    0% { transform: translate(0, 0) scale(1); }
    50% { transform: translate(10%, 15%) scale(1.1); }
    100% { transform: translate(0, 0) scale(1); }
}
```

---

## Card #6: Minimalistic Article Card with Progress Bar

### HTML
```html
<div class="article-card" id="articleCard1">
    <div class="article-bar" id="progressBar1"></div>
    <div class="article-content">
        <div class="article-meta">
            <span class="article-date">July 4, 2026</span>
            <span class="article-readtime">5 min read</span>
        </div>
        <h3>Designing premium Web Elements</h3>
        <p>Understanding details like borders, glowing mesh backdrops, micro-animations, and dynamic feedback systems.</p>
        <div class="article-footer">
            <div class="author">
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=80&auto=format&fit=crop&q=80" alt="Author avatar">
                <span>Sarah Jenkins</span>
            </div>
            <button class="article-arrow" aria-label="Read full article">
                &rarr;
            </button>
        </div>
    </div>
</div>
```

### CSS
```css
.article-card {
    position: relative;
    width: 320px;
    background: #0f172a;
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.35);
    transition: all 0.3s;
}

.article-card:hover {
    transform: translateY(-4px);
    border-color: rgba(255, 255, 255, 0.12);
}

.article-bar {
    position: absolute;
    top: 0;
    left: 0;
    height: 3px;
    width: 0%;
    background: #6366f1;
    transition: width 0.3s ease;
}

.article-content {
    padding: 24px;
}

.article-meta {
    display: flex;
    justify-content: space-between;
    font-size: 0.75rem;
    color: #64748b;
    margin-bottom: 12px;
}

.article-content h3 {
    color: #ffffff;
    font-size: 1.15rem;
    margin-bottom: 8px;
    line-height: 1.4;
    font-weight: 600;
}

.article-content p {
    color: #94a3b8;
    font-size: 0.88rem;
    line-height: 1.5;
    margin-bottom: 20px;
}

.article-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(255, 255, 255, 0.05);
    padding-top: 14px;
}

.author {
    display: flex;
    align-items: center;
    gap: 8px;
}

.author img {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    object-fit: cover;
}

.author span {
    color: #cbd5e1;
    font-size: 0.8rem;
    font-weight: 500;
}

.article-arrow {
    background: transparent;
    border: none;
    color: #6366f1;
    font-size: 1.1rem;
    cursor: pointer;
    transition: transform 0.2s;
}

.article-card:hover .article-arrow {
    transform: translateX(4px);
}
```

---

## Card #7: 3D Stack Carousel Hero

*(See previous records for complete codebase of Card #7, Card #8, and Card #9)*

