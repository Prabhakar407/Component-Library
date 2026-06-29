# Premium Custom Features Code Database

This file contains the complete, self-contained HTML, CSS, and React code snippets for all **5 Premium Features** featured in the interactive showcase. Each feature is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Feature #1: Interactive Bento Grid](#feature-1-interactive-bento-grid)
2. [Feature #2: 3D Tilt Hologram Card](#feature-2-3d-tilt-hologram-card)
3. [Feature #3: Accordion Interactive Row](#feature-3-accordion-interactive-row)
4. [Feature #4: Focus Features Grid](#feature-4-focus-features-grid)
5. [Feature #5: Global Operations Grid](#feature-5-global-operations-grid)

---

## Feature #1: Interactive Bento Grid
*A modern 3-column glassmorphic grid with custom glowing icons, subtle translation animations, and absolute coordinates-tracking glow layers.*

### HTML
```html
<div class="bento-container-1">
    <div class="bento-card bento-hero">
        <div class="bento-glow"></div>
        <div class="bento-header">
            <span class="bento-icon">⚡</span>
            <h3>Neural Performance</h3>
        </div>
        <p>Accelerate workflows with next-gen edge intelligence running asynchronously inside your browser window.</p>
    </div>
    <div class="bento-card bento-side-1">
        <div class="bento-glow"></div>
        <div class="bento-header">
            <span class="bento-icon">🔒</span>
            <h3>Secure Vault</h3>
        </div>
        <p>Advanced client-side cryptographic storage node.</p>
    </div>
    <div class="bento-card bento-side-2">
        <div class="bento-glow"></div>
        <div class="bento-header">
            <span class="bento-icon">🌐</span>
            <h3>Global Sync</h3>
        </div>
        <p>Instant edge-state replication across multiple instances.</p>
    </div>
</div>
```

### CSS
```css
.bento-container-1 {
    display: grid;
    grid-template-columns: 2fr 1fr;
    grid-template-rows: auto auto;
    gap: 12px;
    width: 100%;
    max-width: 360px;
    font-family: inherit;
}

.bento-card {
    background: rgba(18, 24, 38, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 12px;
    padding: 1.2rem;
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.bento-card:hover {
    border-color: rgba(99, 102, 241, 0.3);
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(99, 102, 241, 0.05);
}

.bento-hero {
    grid-column: span 2;
    min-height: 100px;
}

.bento-header {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 6px;
}

.bento-icon {
    font-size: 1.25rem;
}

.bento-card h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: #fff;
}

.bento-card p {
    font-size: 0.75rem;
    color: #94a3b8;
    line-height: 1.4;
}

.bento-glow {
    position: absolute;
    width: 150px;
    height: 150px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.1) 0%, transparent 70%);
    top: -50px;
    right: -50px;
    pointer-events: none;
    transition: all 0.5s ease;
}

.bento-card:hover .bento-glow {
    width: 200px;
    height: 200px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.15) 0%, transparent 70%);
}
```

### JavaScript
```javascript
document.querySelectorAll('.bento-card').forEach(card => {
    card.addEventListener('mousemove', (e) => {
        const rect = card.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        const glow = card.querySelector('.bento-glow');
        if (glow) {
            glow.style.left = (x - 75) + 'px';
            glow.style.top = (y - 75) + 'px';
        }
    });
});
```

---

## Feature #2: 3D Tilt Hologram Card
*An interactive tilt card with high-fidelity depth projection, spatial translations on hover, and custom floating gradients responding to cursor coordinates.*

### HTML
```html
<div class="tilt-card-2" id="tilt-card-2">
    <div class="hologram-effect"></div>
    <div class="card-content">
        <div class="badge">PRO</div>
        <h3>Spatial Core</h3>
        <p>Render premium, dynamic workspaces with real-time mouse coordinate calculations.</p>
        <div class="progress-wrap">
            <span>Interface Status</span>
            <div class="bar"><div class="fill"></div></div>
        </div>
    </div>
</div>
```

### CSS
```css
.tilt-card-2 {
    width: 260px;
    height: 200px;
    background: linear-gradient(135deg, #111827 0%, #1f2937 100%);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 16px;
    position: relative;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    transform-style: preserve-3d;
    perspective: 1000px;
    transition: box-shadow 0.3s;
}

.tilt-card-2:hover {
    box-shadow: 0 15px 45px rgba(99, 102, 241, 0.15);
}

.hologram-effect {
    position: absolute;
    inset: 0;
    background: linear-gradient(
        125deg,
        transparent 0%,
        rgba(99, 102, 241, 0.15) 30%,
        rgba(236, 72, 153, 0.1) 50%,
        transparent 100%
    );
    z-index: 1;
    pointer-events: none;
    transition: background-position 0.1s ease-out;
    background-size: 200% 200%;
    background-position: 0% 0%;
}

.card-content {
    position: relative;
    z-index: 2;
    padding: 1.25rem;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transform: translateZ(40px);
}

.badge {
    align-self: flex-start;
    background: rgba(99, 102, 241, 0.2);
    border: 1px solid #6366f1;
    color: #a5b4fc;
    font-size: 0.65rem;
    font-weight: 700;
    padding: 2px 6px;
    border-radius: 4px;
    letter-spacing: 0.5px;
}

.card-content h3 {
    font-size: 1.1rem;
    font-weight: 700;
    color: #fff;
    margin-top: 10px;
}

.card-content p {
    font-size: 0.75rem;
    color: #94a3b8;
    line-height: 1.4;
    margin-top: 4px;
}

.progress-wrap {
    margin-top: 12px;
}

.progress-wrap span {
    font-size: 0.65rem;
    color: #64748b;
    text-transform: uppercase;
    font-weight: 600;
    display: block;
    margin-bottom: 4px;
}

.bar {
    width: 100%;
    height: 4px;
    background: rgba(255,255,255,0.05);
    border-radius: 2px;
    overflow: hidden;
}

.fill {
    width: 78%;
    height: 100%;
    background: linear-gradient(90deg, #6366f1, #ec4899);
}
```

### JavaScript
```javascript
const card = document.getElementById('tilt-card-2');
const holo = card.querySelector('.hologram-effect');

card.addEventListener('mousemove', (e) => {
    const rect = card.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;

    const xc = rect.width / 2;
    const yc = rect.height / 2;

    const rotateY = -(xc - x) / 10;
    const rotateX = (yc - y) / 10;

    card.style.transform = `rotateY(${rotateY}deg) rotateX(${rotateX}deg)`;

    if (holo) {
        const xPercent = (x / rect.width) * 100;
        const yPercent = (y / rect.height) * 100;
        holo.style.backgroundPosition = `${xPercent}% ${yPercent}%`;
    }
});

card.addEventListener('mouseleave', () => {
    card.style.transform = 'rotateY(0deg) rotateX(0deg)';
    if (holo) holo.style.backgroundPosition = '0% 0%';
});
```

---

## Feature #3: Accordion Interactive Row
*A clean detail accordion layout that opens active panels with smooth transition, updating relative icon rotations and backgrounds.*

### HTML
```html
<div class="accordion-container-3" id="accordion-3">
    <div class="accordion-item active" onclick="toggleAccordionItem(this)">
        <div class="item-head">
            <span class="item-number">01</span>
            <span class="item-title">Adaptive Layouts</span>
            <span class="item-arrow">▼</span>
        </div>
        <div class="item-body">
            <p>Responsive design system adapting instantly to grids, lists, or custom dashboard configurations.</p>
        </div>
    </div>
    <div class="accordion-item" onclick="toggleAccordionItem(this)">
        <div class="item-head">
            <span class="item-number">02</span>
            <span class="item-title">Vibrant Aesthetics</span>
            <span class="item-arrow">▼</span>
        </div>
        <div class="item-body">
            <p>Crafted with premium glassmorphism, glowing micro-animations, and harmoniously curated palettes.</p>
        </div>
    </div>
    <div class="accordion-item" onclick="toggleAccordionItem(this)">
        <div class="item-head">
            <span class="item-number">03</span>
            <span class="item-title">Instant Integration</span>
            <span class="item-arrow">▼</span>
        </div>
        <div class="item-body">
            <p>Vanilla CSS and pure JS ensures out-of-the-box performance and lightweight build profiles.</p>
        </div>
    </div>
</div>
```

### CSS
```css
.accordion-container-3 {
    width: 100%;
    max-width: 320px;
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.accordion-item {
    background: rgba(18, 24, 38, 0.4);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 8px;
    overflow: hidden;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.accordion-item:hover {
    border-color: rgba(99, 102, 241, 0.2);
    background: rgba(18, 24, 38, 0.6);
}

.accordion-item.active {
    border-color: rgba(99, 102, 241, 0.4);
    background: rgba(24, 32, 50, 0.8);
    box-shadow: inset 0 0 10px rgba(99, 102, 241, 0.05);
}

.item-head {
    padding: 12px 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.item-number {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    font-weight: 600;
    color: #6366f1;
}

.item-title {
    font-size: 0.85rem;
    font-weight: 600;
    color: #fff;
    flex: 1;
    margin-left: 12px;
}

.item-arrow {
    font-size: 0.65rem;
    color: #64748b;
    transition: transform 0.3s;
}

.accordion-item.active .item-arrow {
    transform: rotate(180deg);
    color: #6366f1;
}

.item-body {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease;
    padding: 0 16px;
}

.accordion-item.active .item-body {
    max-height: 60px;
    padding-bottom: 12px;
}

.item-body p {
    font-size: 0.75rem;
    color: #94a3b8;
    line-height: 1.4;
}
```

### JavaScript
```javascript
function toggleAccordionItem(element) {
    const parent = element.parentElement;
    const items = parent.querySelectorAll('.accordion-item');
    const isActive = element.classList.contains('active');

    items.forEach(item => {
        item.classList.remove('active');
    });

    if (!isActive) {
        element.classList.add('active');
    }
}
```

---

## Feature #4: Focus Features Grid
*A Tailwind CSS features grid displaying focus-centric product traits with visual indicators and highlighted gradient nodes.*

### HTML
```html
<section class="mt-8">
  <div class="text-center">
    <p class="text-neutral-600 text-xs transition-colors hover:text-emerald-600">Core features</p>
    <h2 class="mt-1 text-4xl font-semibold tracking-tight text-neutral-900 transition-colors hover:text-emerald-700">
      Built for deep focus</h2>
  </div>

  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-4 mt-6">
    <div class="group rounded-2xl bg-white ring-1 ring-black/10 p-5 transition-colors">
      <div class="flex items-center justify-between">
        <span class="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ 01 }</span>
      </div>
      <div class="mt-6">
        <div class="h-10 w-10 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="moon"
            class="lucide lucide-moon h-5 w-5">
            <path
              d="M20.985 12.486a9 9 0 1 1-9.473-9.472c.405-.022.617.46.402.803a6 6 0 0 0 8.268 8.268c.344-.215.825-.004.803.401">
            </path>
          </svg>
        </div>
        <p class="mt-4 text-neutral-900 font-medium tracking-tight transition-colors group-hover:text-emerald-700">E-ink
          Display</p>
        <p class="text-neutral-600 text-sm transition-colors group-hover:text-emerald-600">Paper-like clarity</p>
      </div>
    </div>

    <div class="group rounded-2xl bg-white ring-1 ring-black/10 p-5 transition-colors">
      <div class="flex items-center justify-between">
        <span class="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ 02 }</span>
      </div>
      <div class="mt-6">
        <div class="h-10 w-10 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="battery"
            class="lucide lucide-battery h-5 w-5">
            <path d="M 22 14 L 22 10"></path>
            <rect x="2" y="6" width="16" height="12" rx="2"></rect>
          </svg>
        </div>
        <p class="mt-4 text-neutral-900 font-medium tracking-tight transition-colors group-hover:text-emerald-700">Long
          Battery</p>
        <p class="text-neutral-600 text-sm transition-colors group-hover:text-emerald-600">3 days of use</p>
      </div>
    </div>

    <div class="group rounded-2xl bg-white ring-1 ring-black/10 p-5 transition-colors">
      <div class="flex items-center justify-between">
        <span class="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ 03 }</span>
      </div>
      <div class="mt-6">
        <div class="h-10 w-10 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="target"
            class="lucide lucide-target h-5 w-5">
            <circle cx="12" cy="12" r="10"></circle>
            <circle cx="12" cy="12" r="6"></circle>
            <circle cx="12" cy="12" r="2"></circle>
          </svg>
        </div>
        <p class="mt-4 text-neutral-900 font-medium tracking-tight transition-colors group-hover:text-emerald-700">
          Minimal OS</p>
        <p class="text-neutral-600 text-sm transition-colors group-hover:text-emerald-600">Zero distractions</p>
      </div>
    </div>

    <div class="group rounded-2xl bg-white ring-1 ring-black/10 p-5 transition-colors">
      <div class="flex items-center justify-between">
        <span class="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ 04 }</span>
      </div>
      <div class="mt-6">
        <div class="h-10 w-10 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="keyboard"
            class="lucide lucide-keyboard h-5 w-5">
            <path d="M10 8h.01"></path>
            <path d="M12 12h.01"></path>
            <path d="M14 8h.01"></path>
            <path d="M16 12h.01"></path>
            <path d="M18 8h.01"></path>
            <path d="M6 8h.01"></path>
            <path d="M7 16h10"></path>
            <path d="M8 12h.01"></path>
            <rect width="20" height="16" x="2" y="4" rx="2"></rect>
          </svg>
        </div>
        <p class="mt-4 text-neutral-900 font-medium tracking-tight transition-colors group-hover:text-emerald-700">
          Tactile Keys</p>
        <p class="text-neutral-600 text-sm transition-colors group-hover:text-emerald-600">Satisfying typing</p>
      </div>
    </div>

    <div class="group rounded-2xl bg-white ring-1 ring-black/10 p-5 transition-colors">
      <div class="flex items-center justify-between">
        <span class="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ 05 }</span>
      </div>
      <div class="mt-6">
        <div class="h-10 w-10 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="wifi"
            class="lucide lucide-wifi h-5 w-5">
            <path d="M12 20h.01"></path>
            <path d="M2 8.82a15 15 0 0 1 20 0"></path>
            <path d="M5 12.859a10 10 0 0 1 14 0"></path>
            <path d="M8.5 16.429a5 5 0 0 1 7 0"></path>
          </svg>
        </div>
        <p class="mt-4 text-neutral-900 font-medium tracking-tight transition-colors group-hover:text-emerald-700">
          Always Connected</p>
        <p class="text-neutral-600 text-sm transition-colors group-hover:text-emerald-600">Built-in WiFi</p>
      </div>
    </div>

    <div
      class="relative overflow-hidden rounded-2xl ring-1 ring-emerald-300 p-5 bg-gradient-to-tr from-emerald-700 to-emerald-500 text-white">
      <div class="absolute inset-0"
        style="background: radial-gradient(160px 160px at 30% 30%, rgba(255,255,255,0.25), transparent 60%), radial-gradient(220px 220px at 70% 70%, rgba(0,0,0,0.25), transparent 60%);">
      </div>
      <div class="relative flex items-center justify-between">
        <span class="text-[11px] text-white/80">{ 06 }</span>
      </div>
      <div class="relative mt-6">
        <p class="text-white font-medium tracking-tight">Premium Build</p>
        <p class="text-white/90 text-sm">Aluminum body</p>
      </div>
      <button class="relative mt-8 h-9 w-9 rounded-full bg-white text-neutral-900 flex items-center justify-center shadow-sm transition-colors hover:text-emerald-700">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="arrow-up-right" class="lucide lucide-arrow-up-right h-4 w-4"><path d="M7 7h10v10"></path><path d="M7 17 17 7"></path></svg>
      </button>
    </div>

    <div class="group rounded-2xl bg-white ring-1 ring-black/10 p-5 transition-colors">
      <div class="flex items-center justify-between">
        <span class="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ 07 }</span>
      </div>
      <div class="mt-6">
        <div class="h-10 w-10 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="sun"
            class="lucide lucide-sun h-5 w-5">
            <circle cx="12" cy="12" r="4"></circle>
            <path d="M12 2v2"></path>
            <path d="M12 20v2"></path>
            <path d="m4.93 4.93 1.41 1.41"></path>
            <path d="m17.66 17.66 1.41 1.41"></path>
            <path d="M2 12h2"></path>
            <path d="M20 12h2"></path>
            <path d="m6.34 17.66-1.41 1.41"></path>
            <path d="m19.07 4.93-1.41 1.41"></path>
          </svg>
        </div>
        <p class="mt-4 text-neutral-900 font-medium tracking-tight transition-colors group-hover:text-emerald-700">
          Ambient Light</p>
        <p class="text-neutral-600 text-sm transition-colors group-hover:text-emerald-600">Auto adjusting</p>
      </div>
    </div>

    <div class="group rounded-2xl bg-white ring-1 ring-black/10 p-5 transition-colors">
      <div class="flex items-center justify-between">
        <span class="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ 08 }</span>
      </div>
      <div class="mt-6">
        <div class="h-10 w-10 rounded-lg bg-emerald-100 text-emerald-700 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="cloud"
            class="lucide lucide-cloud h-5 w-5">
            <path d="M17.5 19H9a7 7 0 1 1 6.71-9h1.79a4.5 4.5 0 1 1 0 9Z"></path>
          </svg>
        </div>
        <p class="mt-4 text-neutral-900 font-medium tracking-tight transition-colors group-hover:text-emerald-700">Cloud
          Sync</p>
        <p class="text-neutral-600 text-sm transition-colors group-hover:text-emerald-600">Seamless backup</p>
      </div>
    </div>
  </div>
</section>
```

### React (Tailwind CSS + Lucide Icons)
```tsx
import React from "react"
import { Moon, Battery, Target, Keyboard, Wifi, ArrowUpRight, Sun, Cloud } from "lucide-react"

export function FeaturesFocus() {
  const features = [
    { id: "01", title: "E-ink Display", description: "Paper-like clarity", icon: Moon },
    { id: "02", title: "Long Battery", description: "3 days of use", icon: Battery },
    { id: "03", title: "Minimal OS", description: "Zero distractions", icon: Target },
    { id: "04", title: "Tactile Keys", description: "Satisfying typing", icon: Keyboard },
    { id: "05", title: "Always Connected", description: "Built-in WiFi", icon: Wifi },
    { id: "06", title: "Premium Build", description: "Aluminum body", highlight: true },
    { id: "07", title: "Ambient Light", description: "Auto adjusting", icon: Sun },
    { id: "08", title: "Cloud Sync", description: "Seamless backup", icon: Cloud }
  ];

  return (
    <section className="mt-8 max-w-5xl mx-auto px-4">
      <div className="text-center">
        <p className="text-neutral-600 text-xs transition-colors hover:text-emerald-600 dark:text-neutral-400">Core features</p>
        <h2 className="mt-1 text-4xl font-semibold tracking-tight text-neutral-900 transition-colors hover:text-emerald-700 dark:text-white">
          Built for deep focus
        </h2>
      </div>

      <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-4 mt-6">
        {features.map((feat) => {
          if (feat.highlight) {
            return (
              <div key={feat.id} className="relative overflow-hidden rounded-2xl ring-1 ring-emerald-300 p-5 bg-gradient-to-tr from-emerald-700 to-emerald-500 text-white shadow-md">
                <div className="absolute inset-0 bg-[radial-gradient(160px_160px_at_30%_30%,rgba(255,255,255,0.25),transparent_60%)]" />
                <div className="relative flex items-center justify-between">
                  <span className="text-[11px] text-white/80">{ `{ ${feat.id} }` }</span>
                </div>
                <div className="relative mt-6">
                  <p className="text-white font-medium tracking-tight">{feat.title}</p>
                  <p className="text-white/90 text-sm">{feat.description}</p>
                </div>
                <button className="relative mt-8 h-9 w-9 rounded-full bg-white text-neutral-900 flex items-center justify-center shadow-sm transition-colors hover:text-emerald-700">
                  <ArrowUpRight className="h-4 w-4" />
                </button>
              </div>
            );
          }

          const Icon = feat.icon;
          return (
            <div key={feat.id} className="group rounded-2xl bg-white dark:bg-neutral-900 ring-1 ring-black/10 dark:ring-white/10 p-5 transition-all hover:shadow-md">
              <div className="flex items-center justify-between">
                <span className="text-[11px] text-neutral-400 transition-colors group-hover:text-emerald-600">{ `{ ${feat.id} }` }</span>
              </div>
              <div className="mt-6">
                <div className="h-10 w-10 rounded-lg bg-emerald-100 dark:bg-emerald-950/50 text-emerald-700 dark:text-emerald-400 flex items-center justify-center">
                  <Icon className="h-5 w-5" />
                </div>
                <p className="mt-4 text-neutral-900 dark:text-neutral-100 font-medium tracking-tight transition-colors group-hover:text-emerald-700 dark:group-hover:text-emerald-400">
                  {feat.title}
                </p>
                <p className="text-neutral-600 dark:text-neutral-400 text-sm transition-colors group-hover:text-emerald-600 dark:group-hover:text-emerald-500">
                  {feat.description}
                </p>
              </div>
            </div>
          );
        })}
      </div>
    </section>
  );
}
```

---

## Feature #5: Global Operations Grid
*A dynamic Tailwind CSS dashboard layout detailing multi-column platform capabilities, international logistics solutions, and SLA configurations.*

### HTML
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-6 gap-6 max-w-5xl">
  <!-- Card A -->
  <section
    class="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
    <div class="absolute inset-0 opacity-[0.12]">
      <svg class="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs class="">
          <pattern id="gridA" width="24" height="24" patternUnits="userSpaceOnUse" class="">
            <path d="M24 0H0V24" stroke="#a3e635" stroke-opacity="0.25" stroke-width="0.5" class=""></path>
          </pattern>
        </defs>
        <rect width="400" height="300" fill="url(#gridA)" class=""></rect>
        <circle cx="60" cy="90" r="2" fill="#a3e635" class=""></circle>
        <circle cx="210" cy="60" r="2" fill="#a3e635" class=""></circle>
        <circle cx="320" cy="140" r="2" fill="#a3e635" class=""></circle>
        <path d="M50 210C100 160 170 170 220 130C270 90 320 100 350 70" stroke="#a3e635" stroke-opacity="0.35"
          stroke-width="1.2" fill="none" class=""></path>
      </svg>
    </div>
    <div class="relative z-10">
      <div
        class="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
          stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="globe-2"
          class="lucide lucide-globe-2 h-5 w-5 text-lime-400 stroke-[1.5]">
          <path d="M21.54 15H17a2 2 0 0 0-2 2v4.54" class=""></path>
          <path d="M7 3.34V5a3 3 0 0 0 3 3a2 2 0 0 1 2 2c0 1.1.9 2 2 2a2 2 0 0 0 2-2c0-1.1.9-2 2-2h3.17" class="">
          </path>
          <path d="M11 21.95V18a2 2 0 0 0-2-2a2 2 0 0 1-2-2v-1a2 2 0 0 0-2-2H2.05" class=""></path>
          <circle cx="12" cy="12" r="10" class=""></circle>
        </svg>
      </div>
      <h3 class="text-xl md:text-2xl tracking-tight font-geist" style="">One
        platform.<br><span class="text-lime-400 font-geist" style="">Global operations.</span></h3>
      <p class="mt-3 text-sm md:text-base text-slate-400 font-geist">
        Unify orders, shipping, and returns in a single console to cut costs and ship faster.
      </p>
    </div>
  </section>

  <!-- Card B (Large) -->
  <section
    class="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-4 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
    <div class="absolute inset-0 opacity-[0.09]">
      <svg class="h-full w-full" viewBox="0 0 800 300" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs class="">
          <linearGradient id="fadeLine" x1="0%" y1="0%" x2="100%" y2="0%">
            <stop offset="0%" stop-color="#a3e635" stop-opacity="0" />
            <stop offset="50%" stop-color="#a3e635" stop-opacity="1" />
            <stop offset="100%" stop-color="#a3e635" stop-opacity="0" />
          </linearGradient>
        </defs>
        <rect x="0" y="0" width="800" height="300" fill="none" class=""></rect>
        <path
          d="M20 160C60 90 140 90 200 150C235 185 270 185 315 150C370 107 430 120 480 165C520 200 560 200 610 165C660 130 700 140 780 110"
          stroke="url(#fadeLine)" stroke-width="2" stroke-linecap="round" class=""></path>
        <g stroke="#a3e635" stroke-opacity="0.25" class="">
          <path d="M0 40H800M0 80H800M0 120H800M0 160H800M0 200H800M0 240H800" class=""></path>
          <path d="M80 0V300M160 0V300M240 0V300M320 0V300M400 0V300M480 0V300M560 0V300M640 0V300M720 0V300" class="">
          </path>
        </g>
      </svg>
    </div>
    <div class="relative z-10">
      <div
        class="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
          stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="package"
          class="lucide lucide-package h-5 w-5 text-lime-400 stroke-[1.5]">
          <path
            d="M11 21.73a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73z"
            class=""></path>
          <path d="M12 22V12" class=""></path>
          <polyline points="3.29 7 12 12 20.71 7" class=""></polyline>
          <path d="m7.5 4.27 9 5.15" class=""></path>
        </svg>
      </div>
      <h3 class="text-xl md:text-2xl tracking-tight font-geist text-white" style="">Sell without
        borders.<br><span class="text-lime-400 font-geist" style="">Grow beyond limits.</span></h3>
      <p class="mt-3 text-sm md:text-base text-slate-400 max-w-2xl font-geist">
        We remove operational friction so expansion is a strategy, not a headache.
      </p>
      <div class="mt-6 grid grid-cols-2 md:grid-cols-4 gap-4">
        <div
          class="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="ship"
            class="lucide lucide-ship h-4 w-4 text-lime-400 stroke-[1.5]">
            <path d="M12 10.189V14" class=""></path>
            <path d="M12 2v3" class=""></path>
            <path d="M19 13V7a2 2 0 0 0-2-2H7a2 2 0 0 0-2 2v6" class=""></path>
            <path d="M19.38 20A11.6 11.6 0 0 0 21 14l-8.188-3.639a2 2 0 0 0-1.624 0L3 14a11.6 11.6 0 0 0 2.81 7.76"
              class=""></path>
            <path
              d="M2 21c.6.5 1.2 1 2.5 1 2.5 0 2.5-2 5-2 1.3 0 1.9.5 2.5 1s1.2 1 2.5 1c2.5 0 2.5-2 5-2 1.3 0 1.9.5 2.5 1"
              class=""></path>
          </svg>
          <p class="text-sm text-slate-300 font-geist">Global shipping</p>
        </div>
        <div
          class="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
            data-lucide="shield-check" class="lucide lucide-shield-check h-4 w-4 text-lime-400 stroke-[1.5]">
            <path
              d="M20 13c0 5-3.5 7.5-7.66 8.95a1 1 0 0 1-.67-.01C7.5 20.5 4 18 4 13V6a1 1 0 0 1 1-1c2 0 4.5-1.2 6.24-2.72a1.17 1.17 0 0 1 1.52 0C14.51 3.81 17 5 19 5a1 1 0 0 1 1 1z"
              class=""></path>
            <path d="m9 12 2 2 4-4" class=""></path>
          </svg>
          <p class="text-sm text-slate-300 font-geist">Compliance</p>
        </div>
        <div
          class="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="wallet"
            class="lucide lucide-wallet h-4 w-4 text-lime-400 stroke-[1.5]">
            <path
              d="M19 7V4a1 1 0 0 0-1-1H5a2 2 0 0 0 0 4h15a1 1 0 0 1 1 1v4h-3a2 2 0 0 0 0 4h3a1 1 0 0 0 1-1v-2a1 1 0 0 0-1-1"
              class=""></path>
            <path d="M3 5v14a2 2 0 0 0 2 2h15a1 1 0 0 0 1-1v-4" class=""></path>
          </svg>
          <p class="text-sm text-slate-300 font-geist">Localized payments</p>
        </div>
        <div
          class="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
            data-lucide="badge-check" class="lucide lucide-badge-check h-4 w-4 text-lime-400 stroke-[1.5]">
            <path
              d="M3.85 8.62a4 4 0 0 1 4.78-4.77 4 4 0 0 1 6.74 0 4 4 0 0 1 4.78 4.78 4 4 0 0 1 0 6.74 4 4 0 0 1-4.77 4.78 4 4 0 0 1-6.75 0 4 4 0 0 1-4.78-4.77 4 4 0 0 1 0-6.76Z"
              class=""></path>
            <path d="m9 12 2 2 4-4" class=""></path>
          </svg>
          <p class="text-sm text-slate-300 font-geist">SLA-backed</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Card C -->
  <section
    class="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
    <div class="absolute inset-0 opacity-[0.12]">
      <svg class="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs class="">
          <pattern id="gridC" width="22" height="22" patternUnits="userSpaceOnUse" class="">
            <path d="M22 0H0V22" stroke="#a3e635" stroke-opacity="0.25" stroke-width="0.5" class=""></path>
          </pattern>
        </defs>
        <rect width="400" height="300" fill="url(#gridC)" class=""></rect>
        <path d="M40 230C110 180 180 80 350 120" stroke="#a3e635" stroke-opacity="0.35" stroke-width="1.2" fill="none"
          class=""></path>
        <circle cx="140" cy="150" r="3" fill="#a3e635" class=""></circle>
        <circle cx="260" cy="120" r="3" fill="#a3e635" class=""></circle>
        <circle cx="330" cy="140" r="3" fill="#a3e635" class=""></circle>
      </svg>
    </div>
    <div class="relative z-10">
      <div
        class="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
          stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="satellite"
          class="lucide lucide-satellite h-5 w-5 text-lime-400 stroke-[1.5]">
          <path d="m13.5 6.5-3.148-3.148a1.205 1.205 0 0 0-1.704 0L6.352 5.648a1.205 1.205 0 0 0 0 1.704L9.5 10.5"
            class=""></path>
          <path d="M16.5 7.5 19 5" class=""></path>
          <path d="m17.5 10.5 3.148 3.148a1.205 1.205 0 0 1 0 1.704l-2.296 2.296a1.205 1.205 0 0 1-1.704 0L13.5 14.5"
            class=""></path>
          <path d="M9 21a6 6 0 0 0-6-6" class=""></path>
          <path
            d="M9.352 10.648a1.205 1.205 0 0 0 0 1.704l2.296 2.296a1.205 1.205 0 0 0 1.704 0l4.296-4.296a1.205 1.205 0 0 0 0-1.704l-2.296-2.296a1.205 1.205 0 0 0-1.704 0z"
            class=""></path>
        </svg>
      </div>
      <h3 class="text-xl md:text-2xl tracking-tight font-geist text-white" style="">International
        logistics<br><span class="text-lime-400 font-geist" style="">made simple.</span></h3>
      <p class="mt-3 text-sm md:text-base text-slate-400 font-geist">
        Deliver anywhere with optimized routing, transparent tracking, and reliable SLAs.
      </p>
    </div>
  </section>

  <!-- Card D -->
  <section
    class="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
    <div class="absolute inset-0 opacity-[0.10]">
      <svg class="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs class="">
          <pattern id="dotsD" width="20" height="20" patternUnits="userSpaceOnUse" class="">
            <circle cx="1" cy="1" r="1" fill="#a3e635" fill-opacity="0.25" class=""></circle>
          </pattern>
        </defs>
        <rect width="400" height="300" fill="url(#dotsD)" class=""></rect>
        <circle cx="200" cy="150" r="70" stroke="#a3e635" stroke-opacity="0.35" stroke-width="1.2" fill="none" class="">
        </circle>
        <circle cx="200" cy="150" r="36" stroke="#a3e635" stroke-opacity="0.45" stroke-width="1.2" fill="none" class="">
        </circle>
        <circle cx="200" cy="150" r="4" fill="#a3e635" class=""></circle>
      </svg>
    </div>
    <div class="relative z-10">
      <div
        class="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
          stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="sparkles"
          class="lucide lucide-sparkles h-5 w-5 text-lime-400 stroke-[1.5]">
          <path
            d="M11.017 2.814a1 1 0 0 1 1.966 0l1.051 5.558a2 2 0 0 0 1.594 1.594l5.558 1.051a1 1 0 0 1 0 1.966l-5.558 1.051a2 2 0 0 0-1.594 1.594l-1.051 5.558a1 1 0 0 1-1.966 0l-1.051-5.558a2 2 0 0 0-1.594-1.594l-5.558-1.051a1 1 0 0 1 0-1.966l5.558-1.051a2 2 0 0 0 1.594-1.594z"
            class=""></path>
          <path d="M20 2v4" class=""></path>
          <path d="M22 4h-4" class=""></path>
          <circle cx="4" cy="20" r="2" class=""></circle>
        </svg>
      </div>
      <h3 class="text-xl md:text-2xl tracking-tight font-geist text-white" style="">Smart
        returns.<br><span class="text-lime-400 font-geist" style="">Happier customers.</span></h3>
      <p class="mt-3 text-sm md:text-base text-slate-400 font-geist">
        Offer convenient portals, dynamic policies, and instant credit to boost loyalty.
      </p>
    </div>
  </section>

  <!-- Card E -->
  <section
    class="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
    <div class="absolute inset-0 opacity-[0.12]">
      <svg class="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs class="">
          <pattern id="gridE" width="24" height="24" patternUnits="userSpaceOnUse" class="">
            <path d="M24 0H0V24" stroke="#a3e635" stroke-opacity="0.2" stroke-width="0.5" class=""></path>
          </pattern>
        </defs>
        <rect width="400" height="300" fill="url(#gridE)" class=""></rect>
        <path d="M20 180C60 120 120 180 160 160C200 140 230 150 260 120C290 90 320 120 360 110" stroke="#a3e635"
          stroke-opacity="0.45" stroke-width="1.6" fill="none" class=""></path>
      </svg>
    </div>
    <div class="relative z-10">
      <div
        class="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none"
          stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" data-lucide="rotate-ccw"
          class="lucide lucide-rotate-ccw h-5 w-5 text-lime-400 stroke-[1.5]">
          <path d="M3 12a9 9 0 1 0 9-9 9.75 9.75 0 0 0-6.74 2.74L3 8" class=""></path>
          <path d="M3 3v5h5" class=""></path>
        </svg>
      </div>
      <h3 class="text-xl md:text-2xl tracking-tight font-geist text-white" style="">Instant refunds &amp;
        exchanges.<br><span class="text-lime-400 font-geist" style="">Zero risk.</span></h3>
      <p class="mt-3 text-sm md:text-base text-slate-400 font-geist">
        Real‑time eligibility checks ensure seamless outcomes with fewer support tickets.
      </p>
    </div>
  </section>
</div>
```

### React (Tailwind CSS + Lucide Icons)
```tsx
import React from "react"
import { Globe2, Package, Ship, ShieldCheck, Wallet, BadgeCheck, Satellite, Sparkles, RotateCcw } from "lucide-react"

export function GlobalOperations() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-6 gap-6 max-w-5xl mx-auto px-4 py-8 text-white">
      {/* Card A */}
      <section className="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
        <div className="absolute inset-0 opacity-[0.12] pointer-events-none">
          <svg className="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <pattern id="gridA" width="24" height="24" patternUnits="userSpaceOnUse">
                <path d="M24 0H0V24" stroke="#a3e635" strokeOpacity="0.25" strokeWidth="0.5"></path>
              </pattern>
            </defs>
            <rect width="400" height="300" fill="url(#gridA)"></rect>
            <circle cx="60" cy="90" r="2" fill="#a3e635"></circle>
            <circle cx="210" cy="60" r="2" fill="#a3e635"></circle>
            <circle cx="320" cy="140" r="2" fill="#a3e635"></circle>
            <path d="M50 210C100 160 170 170 220 130C270 90 320 100 350 70" stroke="#a3e635" strokeOpacity="0.35" strokeWidth="1.2" fill="none"></path>
          </svg>
        </div>
        <div className="relative z-10">
          <div className="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
            <Globe2 className="h-5 w-5 text-lime-400 stroke-[1.5]" />
          </div>
          <h3 className="text-xl md:text-2xl tracking-tight font-sans">
            One platform.<br /><span className="text-lime-400">Global operations.</span>
          </h3>
          <p className="mt-3 text-sm md:text-base text-slate-400">
            Unify orders, shipping, and returns in a single console to cut costs and ship faster.
          </p>
        </div>
      </section>

      {/* Card B (Large) */}
      <section className="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-4 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
        <div className="absolute inset-0 opacity-[0.09] pointer-events-none">
          <svg className="h-full w-full" viewBox="0 0 800 300" fill="none" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <linearGradient id="fadeLine" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" stopColor="#a3e635" stopOpacity="0" />
                <stop offset="50%" stopColor="#a3e635" stopOpacity="1" />
                <stop offset="100%" stopColor="#a3e635" stopOpacity="0" />
              </linearGradient>
            </defs>
            <rect x="0" y="0" width="800" height="300" fill="none"></rect>
            <path d="M20 160C60 90 140 90 200 150C235 185 270 185 315 150C370 107 430 120 480 165C520 200 560 200 610 165C660 130 700 140 780 110" stroke="url(#fadeLine)" strokeWidth="2" strokeLinecap="round"></path>
            <g stroke="#a3e635" strokeOpacity="0.25">
              <path d="M0 40H800M0 80H800M0 120H800M0 160H800M0 200H800M0 240H800"></path>
              <path d="M80 0V300M160 0V300M240 0V300M320 0V300M400 0V300M480 0V300M560 0V300M640 0V300M720 0V300"></path>
            </g>
          </svg>
        </div>
        <div className="relative z-10">
          <div className="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
            <Package className="h-5 w-5 text-lime-400 stroke-[1.5]" />
          </div>
          <h3 className="text-xl md:text-2xl tracking-tight font-sans">
            Sell without borders.<br /><span className="text-lime-400">Grow beyond limits.</span>
          </h3>
          <p className="mt-3 text-sm md:text-base text-slate-400 max-w-2xl">
            We remove operational friction so expansion is a strategy, not a headache.
          </p>
          <div className="mt-6 grid grid-cols-2 md:grid-cols-4 gap-4">
            <div className="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
              <Ship className="h-4 w-4 text-lime-400 stroke-[1.5]" />
              <p className="text-sm text-slate-300">Global shipping</p>
            </div>
            <div className="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
              <ShieldCheck className="h-4 w-4 text-lime-400 stroke-[1.5]" />
              <p className="text-sm text-slate-300">Compliance</p>
            </div>
            <div className="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
              <Wallet className="h-4 w-4 text-lime-400 stroke-[1.5]" />
              <p className="text-sm text-slate-300">Localized payments</p>
            </div>
            <div className="flex items-center gap-3 rounded-2xl border border-white/10 bg-white/5 p-3 hover:border-lime-400/30 transition">
              <BadgeCheck className="h-4 w-4 text-lime-400 stroke-[1.5]" />
              <p className="text-sm text-slate-300">SLA-backed</p>
            </div>
          </div>
        </div>
      </section>

      {/* Card C */}
      <section className="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
        <div className="absolute inset-0 opacity-[0.12] pointer-events-none">
          <svg className="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <pattern id="gridC" width="22" height="22" patternUnits="userSpaceOnUse">
                <path d="M22 0H0V22" stroke="#a3e635" strokeOpacity="0.25" strokeWidth="0.5"></path>
              </pattern>
            </defs>
            <rect width="400" height="300" fill="url(#gridC)"></rect>
            <path d="M40 230C110 180 180 80 350 120" stroke="#a3e635" strokeOpacity="0.35" strokeWidth="1.2" fill="none"></path>
            <circle cx="140" cy="150" r="3" fill="#a3e635"></circle>
            <circle cx="260" cy="120" r="3" fill="#a3e635"></circle>
            <circle cx="330" cy="140" r="3" fill="#a3e635"></circle>
          </svg>
        </div>
        <div className="relative z-10">
          <div className="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
            <Satellite className="h-5 w-5 text-lime-400 stroke-[1.5]" />
          </div>
          <h3 className="text-xl md:text-2xl tracking-tight font-sans">
            International logistics<br /><span className="text-lime-400">made simple.</span>
          </h3>
          <p className="mt-3 text-sm md:text-base text-slate-400">
            Deliver anywhere with optimized routing, transparent tracking, and reliable SLAs.
          </p>
        </div>
      </section>

      {/* Card D */}
      <section className="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
        <div className="absolute inset-0 opacity-[0.10] pointer-events-none">
          <svg className="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <pattern id="dotsD" width="20" height="20" patternUnits="userSpaceOnUse">
                <circle cx="1" cy="1" r="1" fill="#a3e635" fillOpacity="0.25"></circle>
              </pattern>
            </defs>
            <rect width="400" height="300" fill="url(#dotsD)"></rect>
            <circle cx="200" cy="150" r="70" stroke="#a3e635" strokeOpacity="0.35" strokeWidth="1.2" fill="none"></circle>
            <circle cx="200" cy="150" r="36" stroke="#a3e635" strokeOpacity="0.45" strokeWidth="1.2" fill="none"></circle>
            <circle cx="200" cy="150" r="4" fill="#a3e635"></circle>
          </svg>
        </div>
        <div className="relative z-10">
          <div className="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
            <Sparkles className="h-5 w-5 text-lime-400 stroke-[1.5]" />
          </div>
          <h3 className="text-xl md:text-2xl tracking-tight font-sans">
            Smart returns.<br /><span className="text-lime-400">Happier customers.</span>
          </h3>
          <p className="mt-3 text-sm md:text-base text-slate-400">
            Offer convenient portals, dynamic policies, and instant credit to boost loyalty.
          </p>
        </div>
      </section>

      {/* Card E */}
      <section className="relative overflow-hidden rounded-3xl border border-white/10 bg-[#0b2421] p-6 md:p-8 lg:col-span-2 hover:border-lime-400/30 hover:bg-[#0d2825] transition">
        <div className="absolute inset-0 opacity-[0.12] pointer-events-none">
          <svg className="h-full w-full" viewBox="0 0 400 300" fill="none" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <pattern id="gridE" width="24" height="24" patternUnits="userSpaceOnUse">
                <path d="M24 0H0V24" stroke="#a3e635" strokeOpacity="0.2" strokeWidth="0.5"></path>
              </pattern>
            </defs>
            <rect width="400" height="300" fill="url(#gridE)"></rect>
            <path d="M20 180C60 120 120 180 160 160C200 140 230 150 260 120C290 90 320 120 360 110" stroke="#a3e635" strokeOpacity="0.45" strokeWidth="1.6" fill="none"></path>
          </svg>
        </div>
        <div className="relative z-10">
          <div className="mb-5 inline-flex h-11 w-11 items-center justify-center rounded-xl bg-lime-500/10 ring-1 ring-lime-400/30">
            <RotateCcw className="h-5 w-5 text-lime-400 stroke-[1.5]" />
          </div>
          <h3 className="text-xl md:text-2xl tracking-tight font-sans">
            Instant refunds &amp; exchanges.<br /><span className="text-lime-400">Zero risk.</span>
          </h3>
          <p className="mt-3 text-sm md:text-base text-slate-400">
            Real‑time eligibility checks ensure seamless outcomes with fewer support tickets.
          </p>
        </div>
      </section>
    </div>
  )
}
```
