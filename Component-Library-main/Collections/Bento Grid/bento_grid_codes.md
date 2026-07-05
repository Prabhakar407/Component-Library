# Premium Custom Bento Grid Code Database

This file contains the complete, self-contained HTML, CSS, and React code snippets for all **6 Premium Bento Grid Layouts** featured in the interactive showcase. Each bento grid is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Layout #1: Interactive Product Feature Grid](#layout-1-interactive-product-feature-grid)
2. [Layout #2: Minimalist Creative Portfolio Grid](#layout-2-minimalist-creative-portfolio-grid)
3. [Layout #3: Advanced Analytics & Charts Grid](#layout-3-advanced-analytics--charts-grid)
4. [Layout #4: SaaS Dashboard Hub Bento](#layout-4-saas-dashboard-hub-bento)
5. [Layout #5: MagicUI Retro Grid Bento](#layout-5-magicui-retro-grid-bento)
6. [Layout #6: Animata Educational Bento Grid](#layout-6-animata-educational-bento-grid)

---

## Layout #1: Interactive Product Feature Grid
*A 3-column feature showcase with absolute coordinates spotlight tracking, linear progress indicator nodes, and glassmorphic icons.*

### HTML
```html
<div class="bento-grid-1">
  <!-- Hero Card -->
  <div class="bento-item-1 item-hero" id="bento1-card-1">
    <div class="bento-spotlight"></div>
    <div class="item-content">
      <span class="badge">Performance</span>
      <h3>Neural Sync Core</h3>
      <p>Real-time client calculations running asynchronously inside our edge node network.</p>
      <div class="metric-meter">
        <div class="meter-bar" style="width: 84%"></div>
      </div>
    </div>
  </div>
  <!-- Card 2 -->
  <div class="bento-item-1 item-secondary">
    <div class="item-content">
      <span class="icon-wrap">🔒</span>
      <h4>Encrypted Vault</h4>
      <p>Fully secure local client database nodes.</p>
    </div>
  </div>
  <!-- Card 3 -->
  <div class="bento-item-1 item-secondary">
    <div class="item-content">
      <span class="icon-wrap">⚡</span>
      <h4>Instant Replication</h4>
      <p>State sync across browser tabs.</p>
    </div>
  </div>
  <!-- Card 4 -->
  <div class="bento-item-1 item-span" id="bento1-card-4">
    <div class="bento-spotlight"></div>
    <div class="item-content flex-row">
      <div>
        <h4>Integrations Hub</h4>
        <p>Instantly deploy webhooks and database connections.</p>
      </div>
      <div class="logo-pile">
        <span class="pile-icon">R</span>
        <span class="pile-icon">N</span>
        <span class="pile-icon">T</span>
      </div>
    </div>
  </div>
</div>
```

### CSS
```css
.bento-grid-1 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: minmax(110px, auto);
    gap: 12px;
    width: 100%;
    max-width: 480px;
}

.bento-item-1 {
    background: rgba(18, 24, 38, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 12px;
    padding: 1.25rem;
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.bento-item-1:hover {
    border-color: rgba(99, 102, 241, 0.3);
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(99, 102, 241, 0.05);
}

.item-hero {
    grid-column: span 2;
    grid-row: span 2;
    background: linear-gradient(135deg, rgba(99, 102, 241, 0.15) 0%, rgba(18, 24, 38, 0.6) 100%);
}

.item-span {
    grid-column: span 3;
}

.bento-spotlight {
    position: absolute;
    width: 160px;
    height: 160px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.18) 0%, transparent 70%);
    top: -80px;
    right: -80px;
    pointer-events: none;
    transition: all 0.5s ease;
}

.bento-item-1:hover .bento-spotlight {
    width: 220px;
    height: 220px;
}

.item-content {
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: space-between;
}

.item-content.flex-row {
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
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
}

.item-content h3 {
    font-size: 1.15rem;
    font-weight: 700;
    color: #fff;
    margin-top: 10px;
}

.item-content h4 {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
}

.item-content p {
    font-size: 0.75rem;
    color: #94a3b8;
    line-height: 1.4;
    margin-top: 4px;
}

.metric-meter {
    width: 100%;
    height: 4px;
    background: rgba(255,255,255,0.05);
    border-radius: 2px;
    overflow: hidden;
    margin-top: 12px;
}

.meter-bar {
    height: 100%;
    background: linear-gradient(90deg, #6366f1, #a5b4fc);
}

.icon-wrap {
    font-size: 1.35rem;
    margin-bottom: 6px;
}

.logo-pile {
    display: flex;
    gap: -6px;
}

.pile-icon {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: #182032;
    border: 1px solid rgba(255,255,255,0.1);
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.65rem;
    font-weight: 700;
    margin-left: -6px;
}
```

### JavaScript
```javascript
document.querySelectorAll('.bento-item-1').forEach(item => {
    item.addEventListener('mousemove', (e) => {
        const rect = item.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        const glow = item.querySelector('.bento-spotlight');
        if (glow) {
            glow.style.left = (x - 80) + 'px';
            glow.style.top = (y - 80) + 'px';
        }
    });
});
```

### React
```tsx
import React from "react"

export function BentoGridProduct() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-3 gap-3 max-w-xl mx-auto p-4 text-white">
      {/* Hero Card */}
      <div className="relative overflow-hidden rounded-2xl bg-slate-900 border border-white/5 p-5 md:col-span-2 md:row-span-2 flex flex-col justify-between group hover:border-indigo-500/30 transition duration-300">
        <div className="absolute top-0 right-0 w-40 h-40 bg-indigo-500/10 rounded-full blur-3xl pointer-events-none group-hover:scale-125 transition duration-500" />
        <div>
          <span className="inline-block bg-indigo-500/20 border border-indigo-400 text-indigo-300 text-[10px] font-bold px-2 py-0.5 rounded">Performance</span>
          <h3 className="text-lg font-bold mt-3">Neural Sync Core</h3>
          <p className="text-xs text-slate-400 mt-1">Real-time client calculations running asynchronously inside our edge network.</p>
        </div>
        <div className="w-full h-1 bg-white/5 rounded-full overflow-hidden mt-4">
          <div className="h-full bg-gradient-to-r from-indigo-500 to-indigo-300" style={{ width: "84%" }} />
        </div>
      </div>

      {/* Card 2 */}
      <div className="rounded-2xl bg-slate-900/60 border border-white/5 p-4 flex flex-col justify-between hover:border-indigo-500/30 transition duration-300">
        <span className="text-lg">🔒</span>
        <h4 className="text-sm font-semibold mt-2">Encrypted Vault</h4>
        <p className="text-[11px] text-slate-400">Fully secure local client database nodes.</p>
      </div>

      {/* Card 3 */}
      <div className="rounded-2xl bg-slate-900/60 border border-white/5 p-4 flex flex-col justify-between hover:border-indigo-500/30 transition duration-300">
        <span className="text-lg">⚡</span>
        <h4 className="text-sm font-semibold mt-2">Instant Replication</h4>
        <p className="text-[11px] text-slate-400">State sync across browser tabs.</p>
      </div>

      {/* Card 4 */}
      <div className="relative overflow-hidden rounded-2xl bg-slate-900/60 border border-white/5 p-5 md:col-span-3 flex justify-between items-center hover:border-indigo-500/30 transition duration-300">
        <div>
          <h4 className="text-sm font-semibold">Integrations Hub</h4>
          <p className="text-xs text-slate-400 mt-0.5">Instantly deploy webhooks and database connections.</p>
        </div>
        <div className="flex -space-x-1">
          <span className="w-6 h-6 rounded-full bg-slate-800 border border-white/10 text-white text-[10px] font-bold flex items-center justify-center">R</span>
          <span className="w-6 h-6 rounded-full bg-slate-800 border border-white/10 text-white text-[10px] font-bold flex items-center justify-center">N</span>
          <span className="w-6 h-6 rounded-full bg-slate-800 border border-white/10 text-white text-[10px] font-bold flex items-center justify-center">T</span>
        </div>
      </div>
    </div>
  )
}
```

---

## Layout #2: Minimalist Creative Portfolio Grid
*An asymmetrical creative grid containing profile avatar cards, tech tool stack grids, and interactive coordinate-shifting showreels.*

### HTML
```html
<div class="bento-grid-2">
  <!-- Avatar Card -->
  <div class="bento-item-2 item-avatar">
    <div class="profile-avatar">S</div>
    <div>
      <h3>Simeon Vance</h3>
      <p class="role">Visual Designer</p>
    </div>
    <div class="social-row">
      <span>𝕏</span>
      <span>🌐</span>
      <span>✉</span>
    </div>
  </div>
  <!-- Showreel Card -->
  <div class="bento-item-2 item-reel" id="bento2-card-2">
    <div class="holo-spot"></div>
    <span class="badge-white">Showreel 2026</span>
    <h3 class="mt-4">Simplicity is dynamic.</h3>
  </div>
  <!-- Stack Card -->
  <div class="bento-item-2 item-stack">
    <h4>Toolbox</h4>
    <div class="stack-badges">
      <span class="badge-tech">React</span>
      <span class="badge-tech">Figma</span>
      <span class="badge-tech">Tailwind</span>
      <span class="badge-tech">Node.js</span>
    </div>
  </div>
</div>
```

### CSS
```css
.bento-grid-2 {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: minmax(130px, auto);
    gap: 12px;
    width: 100%;
    max-width: 480px;
}

.bento-item-2 {
    background: #0f131a;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 16px;
    padding: 1.25rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    position: relative;
    overflow: hidden;
}

.bento-item-2:hover {
    border-color: rgba(255, 255, 255, 0.15);
    box-shadow: 0 10px 25px rgba(0,0,0,0.4);
}

.item-avatar {
    grid-row: span 2;
    background: linear-gradient(180deg, #131924 0%, #0d121c 100%);
    align-items: center;
    text-align: center;
    padding: 1.5rem 1.25rem;
}

.profile-avatar {
    width: 64px;
    height: 64px;
    border-radius: 50%;
    background: linear-gradient(135deg, #a5b4fc, #6366f1);
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.75rem;
    font-weight: 700;
    margin-bottom: 12px;
    box-shadow: 0 0 15px rgba(99, 102, 241, 0.25);
}

.item-avatar h3 {
    font-size: 1.1rem;
    color: #fff;
}

.item-avatar .role {
    font-size: 0.75rem;
    color: #94a3b8;
    margin-top: 2px;
}

.social-row {
    display: flex;
    gap: 12px;
    margin-top: 16px;
    color: #94a3b8;
}

.social-row span {
    cursor: pointer;
    font-size: 0.95rem;
    transition: color 0.2s;
}

.social-row span:hover {
    color: #fff;
}

.item-reel {
    background: #1e1e24;
}

.badge-white {
    align-self: flex-start;
    border: 1px solid rgba(255, 255, 255, 0.2);
    color: #fff;
    font-size: 0.65rem;
    font-weight: 600;
    padding: 2px 8px;
    border-radius: 20px;
    background: rgba(255,255,255,0.05);
}

.item-reel h3 {
    font-size: 1.15rem;
    font-weight: 600;
    color: #fff;
}

.holo-spot {
    position: absolute;
    inset: 0;
    background: linear-gradient(125deg, transparent 0%, rgba(255,255,255,0.05) 50%, transparent 100%);
    pointer-events: none;
    transition: background-position 0.2s ease-out;
    background-size: 200% 200%;
    background-position: 0% 0%;
}

.item-stack {
    background: #0f131a;
}

.item-stack h4 {
    font-size: 0.85rem;
    font-weight: 600;
    color: #64748b;
    margin-bottom: 8px;
}

.stack-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
}

.badge-tech {
    font-size: 0.65rem;
    padding: 4px 8px;
    border-radius: 6px;
    border: 1px solid rgba(255,255,255,0.05);
    background: rgba(255,255,255,0.02);
    color: #94a3b8;
    transition: all 0.3s;
}

.badge-tech:hover {
    color: #fff;
    border-color: rgba(255,255,255,0.2);
}
```

### JavaScript
```javascript
const reel = document.getElementById('bento2-card-2');
if (reel) {
    const spot = reel.querySelector('.holo-spot');
    reel.addEventListener('mousemove', (e) => {
        const rect = reel.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        const xPercent = (x / rect.width) * 100;
        const yPercent = (y / rect.height) * 100;
        if (spot) spot.style.backgroundPosition = `${xPercent}% ${yPercent}%`;
    });
    reel.addEventListener('mouseleave', () => {
        if (spot) spot.style.backgroundPosition = '0% 0%';
    });
}
```

### React
```tsx
import React from "react"

export function BentoGridPortfolio() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 gap-3 max-w-xl mx-auto p-4 text-white">
      {/* Avatar Card */}
      <div className="rounded-3xl bg-slate-905 border border-white/5 p-6 flex flex-col items-center text-center justify-between hover:border-white/10 transition duration-300 md:row-span-2">
        <div className="w-16 h-16 rounded-full bg-gradient-to-tr from-indigo-300 to-indigo-600 text-white flex items-center justify-center text-xl font-bold shadow-md shadow-indigo-500/20">
          S
        </div>
        <div className="mt-4">
          <h3 className="font-semibold text-white">Simeon Vance</h3>
          <p className="text-xs text-slate-400 mt-0.5">Visual Designer</p>
        </div>
        <div className="flex gap-3 mt-6 text-slate-400">
          <span className="hover:text-white cursor-pointer text-xs">𝕏</span>
          <span className="hover:text-white cursor-pointer text-xs">🌐</span>
          <span className="hover:text-white cursor-pointer text-xs">✉</span>
        </div>
      </div>

      {/* Showreel Card */}
      <div className="relative overflow-hidden rounded-3xl bg-neutral-900 border border-white/5 p-5 flex flex-col justify-between hover:border-white/10 transition duration-300 group">
        <span className="self-start bg-white/5 border border-white/10 text-white text-[9px] font-semibold px-2 py-0.5 rounded-full">Showreel 2026</span>
        <h3 className="text-md font-semibold text-white mt-4">Simplicity is dynamic.</h3>
      </div>

      {/* Toolbox Card */}
      <div className="rounded-3xl bg-slate-900 border border-white/5 p-5 flex flex-col justify-between hover:border-white/10 transition duration-300">
        <h4 className="text-xs font-semibold text-slate-400 mb-2">Toolbox</h4>
        <div className="flex flex-wrap gap-1.5">
          <span className="text-[10px] px-2 py-0.5 rounded bg-white/5 border border-white/5 text-slate-300 hover:border-white/20 transition">React</span>
          <span className="text-[10px] px-2 py-0.5 rounded bg-white/5 border border-white/5 text-slate-300 hover:border-white/20 transition">Figma</span>
          <span className="text-[10px] px-2 py-0.5 rounded bg-white/5 border border-white/5 text-slate-300 hover:border-white/20 transition">Tailwind</span>
          <span className="text-[10px] px-2 py-0.5 rounded bg-white/5 border border-white/5 text-slate-300 hover:border-white/20 transition">Node.js</span>
        </div>
      </div>
    </div>
  )
}
```

---

## Layout #3: Advanced Analytics & Charts Grid
*An analytical bento grid dashboard featuring a custom SVG weekly visitors curve graph, active SLA system status indicator node, and logs feed.*

### HTML
```html
<div class="bento-grid-3">
  <!-- Chart Card -->
  <div class="bento-item-3 item-chart">
    <div class="item-head">
      <h4>Weekly Visitors</h4>
      <span class="trend">+12.4%</span>
    </div>
    <!-- SVG Mock Chart -->
    <div class="chart-container-svg">
      <svg viewBox="0 0 200 80" class="svg-graph">
        <path d="M 10,70 Q 40,30 70,55 T 130,20 T 190,40" fill="none" stroke="#10b981" stroke-width="2.5" class="line-path"></path>
        <g stroke="rgba(255,255,255,0.05)" stroke-width="0.5">
          <path d="M 0,20 H 200 M 0,40 H 200 M 0,60 H 200"></path>
        </g>
      </svg>
    </div>
  </div>
  <!-- Metrics Card -->
  <div class="bento-item-3 item-metric">
    <div class="metric-top">
      <span class="pulse-indicator"></span>
      <span class="label">SLA HEALTH</span>
    </div>
    <h3 class="metric-value">99.98%</h3>
    <p class="desc">Active system monitors running</p>
  </div>
  <!-- List Feed Card -->
  <div class="bento-item-3 item-feed">
    <h4>Recent Commits</h4>
    <div class="feed-list">
      <div class="feed-row">
        <span class="dot g-dot"></span>
        <span class="msg">Fix layout alignment drawer</span>
      </div>
      <div class="feed-row">
        <span class="dot p-dot"></span>
        <span class="msg">Scale focus feature card sizing</span>
      </div>
    </div>
  </div>
</div>
```

### CSS
```css
.bento-grid-3 {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: minmax(110px, auto);
    gap: 12px;
    width: 100%;
    max-width: 480px;
}

.bento-item-3 {
    background: #0b0e14;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 1.25rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: all 0.3s;
}

.bento-item-3:hover {
    border-color: rgba(16, 185, 129, 0.3);
}

.item-chart {
    grid-column: span 2;
    grid-row: span 2;
}

.item-head {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.item-head h4 {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
}

.trend {
    font-size: 0.75rem;
    font-weight: 700;
    color: #10b981;
    background: rgba(16, 185, 129, 0.15);
    padding: 2px 6px;
    border-radius: 4px;
}

.chart-container-svg {
    width: 100%;
    margin-top: 16px;
}

.svg-graph {
    width: 100%;
    height: auto;
}

.line-path {
    stroke-dasharray: 500;
    stroke-dashoffset: 500;
    animation: drawLine 2.5s forwards cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes drawLine {
    to {
        stroke-dashoffset: 0;
    }
}

.item-metric {
    background: linear-gradient(135deg, rgba(16,185,129,0.06) 0%, rgba(11,14,20,0.6) 100%);
}

.metric-top {
    display: flex;
    align-items: center;
    gap: 6px;
}

.pulse-indicator {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background-color: #10b981;
    box-shadow: 0 0 8px #10b981;
    animation: pulseFlash 1.5s infinite;
}

@keyframes pulseFlash {
    50% { opacity: 0.3; }
}

.label {
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.5px;
    color: #64748b;
}

.metric-value {
    font-size: 1.5rem;
    font-weight: 700;
    color: #fff;
    margin-top: 6px;
}

.desc {
    font-size: 0.7rem;
    color: #64748b;
    margin-top: 2px;
}

.item-feed h4 {
    font-size: 0.85rem;
    font-weight: 600;
    color: #fff;
    margin-bottom: 8px;
}

.feed-list {
    display: flex;
    flex-direction: column;
    gap: 6px;
}

.feed-row {
    display: flex;
    align-items: center;
    gap: 8px;
}

.dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    flex-shrink: 0;
}

.g-dot { background-color: #10b981; }
.p-dot { background-color: #a855f7; }

.msg {
    font-size: 0.7rem;
    color: #94a3b8;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

### React
```tsx
import React from "react"

export function BentoGridAnalytics() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 gap-3 max-w-xl mx-auto p-4 text-white">
      {/* Chart Card */}
      <div className="rounded-2xl bg-slate-950 border border-white/5 p-5 md:col-span-2 hover:border-emerald-500/30 transition duration-300">
        <div className="flex justify-between items-center">
          <h4 className="text-xs font-semibold">Weekly Visitors</h4>
          <span className="text-[10px] font-bold text-emerald-400 bg-emerald-500/10 px-2 py-0.5 rounded">+12.4%</span>
        </div>
        <div className="w-full mt-4">
          <svg viewBox="0 0 200 80" className="w-full h-auto">
            <path d="M 10,70 Q 40,30 70,55 T 130,20 T 190,40" fill="none" stroke="#10b981" strokeWidth="2.5" />
            <g stroke="rgba(255,255,255,0.05)" strokeWidth="0.5">
              <path d="M 0,20 H 200 M 0,40 H 200 M 0,60 H 200" />
            </g>
          </svg>
        </div>
      </div>

      {/* Metrics Card */}
      <div className="rounded-2xl bg-slate-950/80 border border-white/5 p-4 flex flex-col justify-between hover:border-emerald-500/30 transition duration-300">
        <div className="flex items-center gap-1.5">
          <span className="w-1.5 h-1.5 rounded-full bg-emerald-500 animate-pulse" />
          <span className="text-[9px] font-bold text-slate-500 tracking-wider">SLA HEALTH</span>
        </div>
        <h3 className="text-xl font-bold text-white mt-1">99.98%</h3>
        <p className="text-[10px] text-slate-500 mt-1">Active system monitors running</p>
      </div>

      {/* Commit Feed Card */}
      <div className="rounded-2xl bg-slate-950/80 border border-white/5 p-4 flex flex-col justify-between hover:border-emerald-500/30 transition duration-300">
        <h4 className="text-xs font-semibold mb-2">Recent Commits</h4>
        <div className="flex flex-col gap-1.5">
          <div className="flex items-center gap-2">
            <span className="w-1.5 h-1.5 rounded-full bg-emerald-400" />
            <span className="text-[10px] text-slate-400 truncate">Fix layout alignment drawer</span>
          </div>
          <div className="flex items-center gap-2">
            <span className="w-1.5 h-1.5 rounded-full bg-purple-400" />
            <span className="text-[10px] text-slate-400 truncate">Scale focus feature card sizing</span>
          </div>
        </div>
      </div>
    </div>
  )
}
```

---

## Layout #4: SaaS Dashboard Hub Bento
*A SaaS portal widget bento featuring a radial gauge meter for storage capacity alongside user profiles and tool grids.*

### HTML
```html
<div class="bento-grid-4">
  <!-- Storage Gauge -->
  <div class="bento-item-4 item-gauge">
    <div class="gauge-head">
      <h4>Cloud Storage</h4>
      <span class="percent">64%</span>
    </div>
    <div class="circle-meter-box">
      <svg class="radial-svg" viewBox="0 0 36 36">
        <path class="ring-bg" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="3"></path>
        <path class="ring-fill" stroke-dasharray="64, 100" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" fill="none" stroke="#6366f1" stroke-width="3" stroke-linecap="round"></path>
      </svg>
    </div>
    <p class="caption">12.8 GB of 20 GB used</p>
  </div>
  <!-- Profile Card -->
  <div class="bento-item-4 item-profile">
    <div class="avatar-sm">U</div>
    <div class="meta">
      <h3>Nova Vance</h3>
      <p class="email">nova@edge.io</p>
    </div>
    <div class="toggle-btn-box">
      <div class="interactive-switch" onclick="toggleDashboardSwitch(this)">
        <div class="switch-ball"></div>
      </div>
      <span class="toggle-lbl">Pro mode</span>
    </div>
  </div>
  <!-- Features Grid -->
  <div class="bento-item-4 item-features">
    <h4>Platform Tools</h4>
    <div class="small-tools-grid">
      <span class="tool-node">Webhook</span>
      <span class="tool-node">Analytics</span>
      <span class="tool-node">Edge Sync</span>
    </div>
  </div>
</div>
```

### CSS
```css
.bento-grid-4 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-auto-rows: minmax(130px, auto);
    gap: 12px;
    width: 100%;
    max-width: 480px;
}

.bento-item-4 {
    background: rgba(18, 24, 38, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    padding: 1.25rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: all 0.3s ease;
}

.bento-item-4:hover {
    border-color: rgba(99, 102, 241, 0.35);
}

.item-gauge {
    grid-row: span 2;
    align-items: center;
    text-align: center;
    background: linear-gradient(180deg, rgba(99, 102, 241, 0.05) 0%, rgba(18, 24, 38, 0.6) 100%);
}

.gauge-head {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.gauge-head h4 {
    font-size: 0.85rem;
    font-weight: 600;
    color: #94a3b8;
}

.percent {
    font-size: 0.85rem;
    font-weight: 700;
    color: #6366f1;
}

.circle-meter-box {
    width: 90px;
    height: 90px;
    margin: 20px 0;
}

.radial-svg {
    width: 100%;
    height: 100%;
}

.caption {
    font-size: 0.7rem;
    color: #64748b;
}

.item-profile {
    gap: 8px;
}

.avatar-sm {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background: #6366f1;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1rem;
    font-weight: 700;
}

.item-profile h3 {
    font-size: 0.95rem;
    font-weight: 600;
    color: #fff;
}

.email {
    font-size: 0.7rem;
    color: #64748b;
}

.toggle-btn-box {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-top: 4px;
}

.interactive-switch {
    width: 32px;
    height: 18px;
    border-radius: 20px;
    background: rgba(255,255,255,0.08);
    position: relative;
    cursor: pointer;
    transition: all 0.3s;
}

.interactive-switch.active {
    background: #10b981;
}

.switch-ball {
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background: #fff;
    position: absolute;
    top: 2px;
    left: 2px;
    transition: all 0.3s;
}

.interactive-switch.active .switch-ball {
    left: 16px;
}

.toggle-lbl {
    font-size: 0.7rem;
    color: #94a3b8;
}

.item-features h4 {
    font-size: 0.85rem;
    font-weight: 600;
    color: #fff;
    margin-bottom: 8px;
}

.small-tools-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
}

.tool-node {
    font-size: 0.65rem;
    padding: 4px 8px;
    border-radius: 6px;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.06);
    color: #94a3b8;
    cursor: pointer;
    transition: all 0.2s;
}

.tool-node:hover {
    color: #fff;
    border-color: rgba(99,102,241,0.25);
    background: rgba(99,102,241,0.05);
}
```

### JavaScript
```javascript
window.toggleDashboardSwitch = function(switchEl) {
    switchEl.classList.toggle('active');
};
```

### React
```tsx
import React, { useState } from "react"

export function BentoGridDashboard() {
  const [isPro, setIsPro] = useState(false)

  return (
    <div className="grid grid-cols-1 md:grid-cols-2 gap-3 max-w-xl mx-auto p-4 text-white">
      {/* Storage Gauge */}
      <div className="rounded-2xl bg-slate-900 border border-white/5 p-5 md:row-span-2 flex flex-col justify-between items-center text-center hover:border-indigo-500/30 transition duration-300">
        <div className="w-full flex justify-between items-center">
          <h4 className="text-[11px] font-semibold text-slate-400">Cloud Storage</h4>
          <span className="text-[11px] font-bold text-indigo-400">64%</span>
        </div>
        <div className="w-20 h-20 my-4">
          <svg className="w-full h-full" viewBox="0 0 36 36">
            <path className="ring-bg" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" fill="none" stroke="rgba(255,255,255,0.05)" strokeWidth="3" />
            <path className="ring-fill" strokeDasharray="64, 100" d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0 0 1 0 -31.831" fill="none" stroke="#6366f1" strokeWidth="3" strokeLinecap="round" />
          </svg>
        </div>
        <p className="text-[10px] text-slate-500">12.8 GB of 20 GB used</p>
      </div>

      {/* Profile Card */}
      <div className="rounded-2xl bg-slate-900 border border-white/5 p-4 flex flex-col justify-between hover:border-indigo-500/30 transition duration-300 gap-2">
        <div className="flex items-center gap-3">
          <div className="w-9 h-9 rounded-full bg-indigo-500 text-white flex items-center justify-center text-sm font-bold">U</div>
          <div>
            <h3 className="text-xs font-semibold">Nova Vance</h3>
            <p className="text-[10px] text-slate-500">nova@edge.io</p>
          </div>
        </div>
        <div className="flex items-center gap-2 mt-2">
          <div onClick={() => setIsPro(!isPro)} className={`w-8 h-4.5 rounded-full p-0.5 cursor-pointer transition-colors duration-200 ${isPro ? "bg-emerald-500" : "bg-slate-800"}`}>
            <div className={`w-3.5 h-3.5 rounded-full bg-white transition-transform duration-200 ${isPro ? "translate-x-3.5" : "translate-x-0"}`} />
          </div>
          <span className="text-[10px] text-slate-400">Pro mode</span>
        </div>
      </div>

      {/* Tools Card */}
      <div className="rounded-2xl bg-slate-900 border border-white/5 p-4 flex flex-col justify-between hover:border-indigo-500/30 transition duration-300">
        <h4 className="text-xs font-semibold mb-2">Platform Tools</h4>
        <div className="flex flex-wrap gap-1.5">
          <span className="text-[9px] px-2 py-0.5 rounded bg-white/5 border border-white/5 text-slate-300 hover:border-indigo-500/20 hover:bg-indigo-500/5 transition">Webhook</span>
          <span className="text-[9px] px-2 py-0.5 rounded bg-white/5 border border-white/5 text-slate-300 hover:border-indigo-500/20 hover:bg-indigo-500/5 transition">Analytics</span>
          <span className="text-[9px] px-2 py-0.5 rounded bg-white/5 border border-white/5 text-slate-300 hover:border-indigo-500/20 hover:bg-indigo-500/5 transition">Edge Sync</span>
        </div>
      </div>
    </div>
  )
}
```

---

## Layout #5: MagicUI Retro Grid Bento
*A retro-grid bento layout mimicking modern developer elements with grid projections and motion vector indicators.*

### HTML
```html
<div class="bento-grid-5">
  <!-- Grid Card -->
  <div class="bento-item-5 item-retro" id="bento5-card-1">
    <div class="retro-grid-bg"></div>
    <div class="spotlight-layer"></div>
    <div class="retro-content">
      <span class="badge-retro">RETRO GRID</span>
      <h3>Infinite Coordinates</h3>
      <p>A classic matrix background that shifts color elements dynamically on cursor interaction.</p>
    </div>
  </div>
  <!-- Node Card -->
  <div class="bento-item-5 item-node">
    <div class="node-content">
      <span class="node-icon">💫</span>
      <h4>Motion Sync</h4>
    </div>
    <p class="node-desc">Custom physics coordinates.</p>
  </div>
  <!-- Activity Card -->
  <div class="bento-item-5 item-node">
    <div class="node-content">
      <span class="node-icon">🌀</span>
      <h4>Fluid Nodes</h4>
    </div>
    <p class="node-desc">Vector paths tracing.</p>
  </div>
</div>
```

### CSS
```css
.bento-grid-5 {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: minmax(110px, auto);
    gap: 12px;
    width: 100%;
    max-width: 480px;
}

.bento-item-5 {
    background: #060a12;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 1.25rem;
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: all 0.3s;
}

.bento-item-5:hover {
    border-color: rgba(99, 102, 241, 0.3);
}

.item-retro {
    grid-column: span 2;
    grid-row: span 2;
    background: #03070d;
}

.retro-grid-bg {
    position: absolute;
    inset: 0;
    opacity: 0.15;
    background-image: 
        linear-gradient(rgba(99, 102, 241, 0.25) 1px, transparent 1px),
        linear-gradient(90deg, rgba(99, 102, 241, 0.25) 1px, transparent 1px);
    background-size: 24px 24px;
    pointer-events: none;
    transform: perspective(200px) rotateX(60deg) translateY(-20px);
    transform-origin: top center;
}

.spotlight-layer {
    position: absolute;
    width: 200px;
    height: 200px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.22) 0%, transparent 70%);
    top: -100px;
    right: -100px;
    pointer-events: none;
    transition: all 0.4s ease;
}

.bento-item-5:hover .spotlight-layer {
    width: 250px;
    height: 250px;
}

.retro-content {
    position: relative;
    z-index: 10;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100%;
}

.badge-retro {
    align-self: flex-start;
    background: rgba(99, 102, 241, 0.2);
    border: 1px solid rgba(99, 102, 241, 0.4);
    color: #a5b4fc;
    font-size: 0.65rem;
    font-weight: 700;
    padding: 2px 6px;
    border-radius: 4px;
}

.retro-content h3 {
    font-size: 1.15rem;
    color: #fff;
    margin-top: 10px;
}

.retro-content p {
    font-size: 0.75rem;
    color: #94a3b8;
    line-height: 1.4;
    margin-top: 4px;
}

.item-node {
    background: #060a12;
}

.node-content {
    display: flex;
    align-items: center;
    gap: 8px;
}

.node-icon {
    font-size: 1.15rem;
}

.node-content h4 {
    font-size: 0.85rem;
    font-weight: 600;
    color: #fff;
}

.node-desc {
    font-size: 0.7rem;
    color: #64748b;
    margin-top: 8px;
}
```

### JavaScript
```javascript
const retroCard = document.getElementById('bento5-card-1');
if (retroCard) {
    const spot = retroCard.querySelector('.spotlight-layer');
    retroCard.addEventListener('mousemove', (e) => {
        const rect = retroCard.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        if (spot) {
            spot.style.left = (x - 100) + 'px';
            spot.style.top = (y - 100) + 'px';
        }
    });
}
```

### React
```tsx
import React from "react"

export function BentoGridRetro() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 gap-3 max-w-xl mx-auto p-4 text-white">
      {/* Retro Grid Card */}
      <div className="relative overflow-hidden rounded-2xl bg-neutral-950 border border-white/5 p-5 md:col-span-2 md:row-span-2 flex flex-col justify-between hover:border-indigo-500/35 transition duration-300 group">
        {/* Retro Grid Effect */}
        <div className="absolute inset-0 opacity-15 bg-[linear-gradient(rgba(99,102,241,0.25)_1px,transparent_1px),linear-gradient(90deg,rgba(99,102,241,0.25)_1px,transparent_1px)] bg-[size:24px_24px] [transform:perspective(200px)_rotateX(60deg)_translateY(-20px)] origin-top pointer-events-none" />
        <div className="absolute top-0 right-0 w-44 h-44 bg-indigo-500/10 rounded-full blur-3xl pointer-events-none group-hover:scale-110 transition duration-500" />
        
        <div className="relative z-10">
          <span className="inline-block bg-indigo-500/20 border border-indigo-500/40 text-indigo-300 text-[10px] font-bold px-2 py-0.5 rounded">RETRO GRID</span>
          <h3 className="text-md font-semibold text-white mt-4">Infinite Coordinates</h3>
          <p className="text-xs text-slate-400 mt-1">A classic matrix background that shifts color elements dynamically on cursor interaction.</p>
        </div>
      </div>

      {/* Node Card */}
      <div className="rounded-2xl bg-slate-950 border border-white/5 p-4 flex flex-col justify-between hover:border-indigo-500/35 transition duration-300">
        <div className="flex items-center gap-2">
          <span className="text-md">💫</span>
          <h4 className="text-xs font-semibold">Motion Sync</h4>
        </div>
        <p className="text-[10px] text-slate-500 mt-2">Custom physics coordinates.</p>
      </div>

      {/* Activity Card */}
      <div className="rounded-2xl bg-slate-950 border border-white/5 p-4 flex flex-col justify-between hover:border-indigo-500/35 transition duration-300">
        <div className="flex items-center gap-2">
          <span className="text-md">🌀</span>
          <h4 className="text-xs font-semibold">Fluid Nodes</h4>
        </div>
        <p className="text-[10px] text-slate-500 mt-2">Vector paths tracing.</p>
      </div>
    </div>
  )
}
```

---

## Layout #6: Animata Educational Bento Grid
*A dashboard grid optimized for educational features containing tickers, typing simulators, animated counters, custom badges, avatar rows, report structures, and responsive layouts.*

### HTML
```html
<div class="bento-grid-6">
  <div class="grid w-full grid-cols-1 sm:grid-cols-4 gap-3">
    <!-- FeatureOne: Highly Rated -->
    <div class="bento-card flex flex-col bg-yellow-300 p-4 rounded-2xl justify-between h-36">
      <div class="font-bold text-yellow-800 text-xs">Highly rated</div>
      <div class="mt-auto flex justify-end items-baseline gap-0.5">
        <div class="text-5xl font-black text-black/75 leading-none bento-ticker" data-target="4.8">0.0</div>
        <span class="text-xl text-yellow-800 font-bold">★</span>
      </div>
    </div>

    <!-- FeatureTwo: Students Counter + AvatarList -->
    <div class="bento-card flex flex-col bg-violet-500 p-4 rounded-2xl justify-between h-36 text-white col-span-2">
      <strong class="text-2xl font-bold leading-none bento-counter" data-target="179">0k+ students</strong>
      <div class="flex -space-x-1.5 overflow-hidden mt-auto">
        <div class="inline-block h-7 w-7 rounded-full ring-2 ring-violet-500 bg-rose-400 text-white flex items-center justify-center font-bold text-[10px]">SV</div>
        <div class="inline-block h-7 w-7 rounded-full ring-2 ring-violet-500 bg-indigo-400 text-white flex items-center justify-center font-bold text-[10px]">JD</div>
        <div class="inline-block h-7 w-7 rounded-full ring-2 ring-violet-500 bg-emerald-400 text-white flex items-center justify-center font-bold text-[10px]">AM</div>
        <div class="inline-block h-7 w-7 rounded-full ring-2 ring-violet-500 bg-amber-400 text-white flex items-center justify-center font-bold text-[10px]">+9k</div>
      </div>
    </div>

    <!-- FeatureThree: Integrated AI -->
    <div class="bento-card flex flex-col bg-orange-300 p-4 rounded-2xl justify-between h-36">
      <svg class="h-8 w-8 text-black" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M12 8V4H8"></path>
        <rect width="16" height="12" x="4" y="8" rx="2"></rect>
        <path d="M2 14h2"></path>
        <path d="M20 14h2"></path>
        <path d="M15 13v2"></path>
        <path d="M9 13v2"></path>
      </svg>
      <strong class="mt-1 block text-xs font-bold text-orange-950">Integrated AI</strong>
      <div class="mt-auto">
        <div class="text-[10px] text-orange-950/80 font-medium">What is 4 times 4?</div>
        <div class="font-bold text-xs min-h-[16px] bento-typing" data-text="4 times 4 is 16"></div>
      </div>
    </div>

    <!-- FeatureFour: Progress Report -->
    <div class="bento-card flex items-center gap-4 bg-lime-300 p-4 rounded-2xl justify-between h-36 col-span-2">
      <div class="text-lg font-black text-lime-900 leading-snug">Generate progress report</div>
      <div class="w-32 bg-white rounded-xl p-3 border border-lime-400/30 shadow-sm shrink-0 overflow-hidden flex flex-col gap-1.5">
        <div class="h-2.5 bg-slate-200 rounded w-3/4 animate-pulse"></div>
        <div class="h-2 bg-slate-100 rounded w-5/6 animate-pulse"></div>
        <div class="h-2 bg-slate-100 rounded w-1/2 animate-pulse"></div>
        <div class="flex items-center gap-1 mt-1">
          <div class="h-3.5 w-3.5 rounded-full bg-lime-400 shrink-0"></div>
          <div class="h-1.5 bg-slate-100 rounded w-10"></div>
        </div>
      </div>
    </div>

    <!-- FeatureFive: EDU Copy -->
    <div class="bento-card flex flex-col items-center justify-center bg-zinc-300 p-4 rounded-2xl h-36 col-span-2 group/bento relative overflow-hidden cursor-pointer">
      <div class="text-7xl font-black uppercase text-zinc-400/25 transition-all duration-300 group-hover/bento:opacity-50 select-none">
        EDU
      </div>
      <div class="text-2xl absolute font-black uppercase text-zinc-800 transition-all duration-300 group-hover/bento:text-6xl select-none">
        EDU
      </div>
    </div>

    <!-- FeatureSix: Weekly Review / BarChart -->
    <div class="bento-card bg-green-200 p-4 rounded-2xl flex flex-col justify-between h-36">
      <div class="flex items-end justify-between gap-1 h-16 px-1">
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 20px;"></div>
          <span class="text-[8px] font-bold text-green-800">Jan</span>
        </div>
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 48px;"></div>
          <span class="text-[8px] font-bold text-green-800">S</span>
        </div>
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 40px;"></div>
          <span class="text-[8px] font-bold text-green-800">M</span>
        </div>
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 60px;"></div>
          <span class="text-[8px] font-bold text-green-800">T</span>
        </div>
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 8px;"></div>
          <span class="text-[8px] font-bold text-green-800">W</span>
        </div>
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 15px;"></div>
          <span class="text-[8px] font-bold text-green-800">Th</span>
        </div>
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 20px;"></div>
          <span class="text-[8px] font-bold text-green-800">F</span>
        </div>
        <div class="flex flex-col items-center flex-1 gap-1">
          <div class="w-full bg-green-400 rounded-t-sm transition-all duration-500 hover:bg-green-500" style="height: 60px;"></div>
          <span class="text-[8px] font-bold text-green-800">Sa</span>
        </div>
      </div>
      <div class="mt-1 text-center font-bold text-[10px] text-green-800">Weekly review</div>
    </div>

    <!-- FeatureSeven: Skills -->
    <div class="bento-card bg-rose-300 p-4 rounded-2xl flex flex-col justify-center gap-1.5 h-36">
      <div class="w-full -rotate-1 rounded-full bg-rose-500 hover:scale-105 transition py-1 text-center text-[10px] font-bold text-white shadow-xs">
        Javascript
      </div>
      <div class="w-full rotate-1 rounded-full bg-rose-500 hover:scale-105 transition py-1 text-center text-[10px] font-bold text-white shadow-xs">
        ReactJS
      </div>
      <div class="w-full rounded-full bg-rose-500 hover:scale-105 transition py-1 text-center text-[10px] font-bold text-white shadow-xs">
        NextJS
      </div>
    </div>

    <!-- FeatureEight: Daily Reminders -->
    <div class="bento-card bg-blue-200 p-4 rounded-2xl flex flex-col justify-between h-36 col-span-2 relative overflow-hidden">
      <div class="w-full bg-white rounded-xl p-2.5 border border-blue-300 shadow-xs flex items-center gap-2">
        <div class="h-7 w-7 rounded bg-blue-400 flex items-center justify-center text-sm shrink-0">⏰</div>
        <div class="flex-1 flex flex-col gap-1">
          <div class="h-2.5 bg-slate-200 rounded w-1/3"></div>
          <div class="h-1.5 bg-slate-100 rounded w-2/3"></div>
        </div>
      </div>
      <div class="mt-2">
        <div class="text-xs font-bold text-blue-900 leading-none">Daily reminders</div>
        <p class="text-[10px] text-blue-800 mt-0.5 leading-tight">Our daily reminder helps you keep focused on your goals.</p>
      </div>
    </div>
  </div>
</div>
```

### CSS
```css
/* Core bento card hover & animation resets */
.bento-card {
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
.bento-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
}
```

### JavaScript
```javascript
// Initializer for Bento Grid 6 animations
const bento6Container = document.getElementById('card-6');
if (bento6Container) {
    // Ticker Animation
    const tickers = bento6Container.querySelectorAll('.bento-ticker');
    tickers.forEach(ticker => {
        const target = parseFloat(ticker.getAttribute('data-target'));
        let current = 0.0;
        const duration = 1200; 
        const stepTime = 30;
        const steps = duration / stepTime;
        const increment = target / steps;
        const timer = setInterval(() => {
            current += increment;
            if (current >= target) {
                ticker.textContent = target.toFixed(1);
                clearInterval(timer);
            } else {
                ticker.textContent = current.toFixed(1);
            }
        }, stepTime);
    });

    // Counter Animation
    const counters = bento6Container.querySelectorAll('.bento-counter');
    counters.forEach(counter => {
        const target = parseInt(counter.getAttribute('data-target'));
        let current = 0;
        const duration = 1500;
        const stepTime = 30;
        const steps = duration / stepTime;
        const increment = Math.ceil(target / steps);
        const timer = setInterval(() => {
            current += increment;
            if (current >= target) {
                counter.textContent = `${target}k+ students`;
                clearInterval(timer);
            } else {
                counter.textContent = `${current}k+ students`;
            }
        }, stepTime);
    });

    // Typing Animation
    const typings = bento6Container.querySelectorAll('.bento-typing');
    typings.forEach(el => {
        const text = el.getAttribute('data-text');
        let index = 0;
        el.textContent = '';
        function type() {
            if (index < text.length) {
                el.textContent += text.charAt(index);
                index++;
                setTimeout(type, 100);
            } else {
                setTimeout(() => {
                    index = 0;
                    el.textContent = '';
                    setTimeout(type, 1000);
                }, 2000);
            }
        }
        type();
    });
}
```

### React
```tsx
import { Bot } from "lucide-react";

import BarChart from "@/animata/graphs/bar-chart";
import AvatarList from "@/animata/list/avatar-list";
import Report from "@/animata/skeleton/report";
import WideCard from "@/animata/skeleton/wide-card";
import Counter from "@/animata/text/counter";
import Ticker from "@/animata/text/ticker";
import TypingText from "@/animata/text/typing-text";
import { cn } from "@/lib/utils";

// #region placeholder
function BoldCopy({
  text = "animata",
  className,
  textClassName,
  backgroundTextClassName,
}: {
  text: string;
  className?: string;
  textClassName?: string;
  backgroundTextClassName?: string;
}) {
  if (!text?.length) {
    return null;
  }

  return (
    <div
      className={cn(
        "group/bento relative flex items-center justify-center bg-background px-2 py-2 md:px-6 md:py-4",
        className,
      )}
    >
      <div
        className={cn(
          "text-4xl font-black uppercase text-foreground/15 transition-all group-hover/bento:opacity-50 md:text-8xl",
          backgroundTextClassName,
        )}
      >
        {text}
      </div>
      <div
        className={cn(
          "text-md absolute font-black uppercase text-foreground transition-all group-hover/bento:text-4xl md:text-3xl group-hover/bento:md:text-8xl",
          textClassName,
        )}
      >
        {text}
      </div>
    </div>
  );
}

function BentoCard({ children, className }: { children: React.ReactNode; className?: string }) {
  return (
    <div className={cn("relative h-full w-full overflow-hidden rounded-2xl p-4", className)}>
      {children}
    </div>
  );
}

function FeatureOne() {
  return (
    <BentoCard className="flex flex-col bg-yellow-300">
      <div className="font-bold text-yellow-700">Highly rated</div>
      <div className="mt-auto flex justify-end">
        <div className="text-4xl font-black text-black/60 md:text-7xl">
          <Ticker value="4.8" />
        </div>{" "}
        <sup className="text-xl text-yellow-700">★</sup>
      </div>
    </BentoCard>
  );
}

function FeatureTwo() {
  return (
    <BentoCard className="relative flex flex-col overflow-visible bg-violet-500 sm:col-span-2">
      <strong className="text-2xl font-semibold text-white">
        <Counter targetValue={179} format={(v) => `${+Math.ceil(v)}k+ students`} />
      </strong>
      <div className="ml-4 mt-auto">
        <AvatarList size="sm" className="py-0" />
      </div>
    </BentoCard>
  );
}

function FeatureThree() {
  return (
    <BentoCard className="flex flex-col bg-orange-300">
      <Bot className="size-8 md:size-12" />
      <strong className="mt-1 inline-block text-sm">Integrated AI</strong>

      <div className="mt-auto">
        <div className="text-sm font-medium">What is 4 times 4?</div>
        <div className="font-semibold">
          <TypingText text="4 times 4 is 16" waitTime={2000} alwaysVisibleCount={0} />
        </div>
      </div>
    </BentoCard>
  );
}

function FeatureFour() {
  return (
    <BentoCard className="flex items-center gap-4 bg-lime-300 sm:col-span-2 md:flex-row-reverse">
      <div className="text-2xl font-black text-lime-800">Generate progress report</div>
      <div className="relative max-h-32 shrink-0 overflow-hidden">
        <Report className="w-40 overflow-hidden border-none shadow-none hover:shadow-none" />
      </div>
    </BentoCard>
  );
}

function FeatureFive() {
  return (
    <BentoCard className="flex flex-col items-center justify-center bg-zinc-300 sm:col-span-2">
      <BoldCopy text="EDU" className="bg-transparent" textClassName="text-zinc-800" />
    </BentoCard>
  );
}

function FeatureSix() {
  return (
    <BentoCard className="bg-green-200">
      <BarChart
        items={[
          {
            progress: 30,
            label: "Jan",
            className: "rounded-xl bg-green-400",
          },
          { progress: 70, label: "S", className: "rounded-xl bg-green-400" },
          { progress: 60, label: "M", className: "rounded-xl bg-green-400" },
          { progress: 90, label: "T", className: "rounded-xl bg-green-400" },
          { progress: 10, label: "W", className: "rounded-xl bg-green-400" },
          { progress: 20, label: "Th", className: "rounded-xl bg-green-400" },
          { progress: 30, label: "F", className: "rounded-xl bg-green-400" },
          { progress: 90, label: "Sa", className: "rounded-xl bg-green-400" },
        ]}
        height={100}
      />
      <div className="mt-2 text-center font-bold">Weekly review</div>
    </BentoCard>
  );
}

function FeatureSeven() {
  return (
    <BentoCard className="flex flex-col gap-2 bg-rose-300">
      <div className="w-full -rotate-1 rounded-full border-rose-400 bg-rose-400 py-2 text-center font-semibold text-white md:-rotate-3">
        Javascript
      </div>
      <div className="w-full rotate-1 rounded-full border-rose-400 bg-rose-400 py-2 text-center font-semibold text-white md:rotate-3">
        ReactJS
      </div>
      <div className="w-full rounded-full border-rose-400 bg-rose-400 py-2 text-center font-semibold text-white">
        NextJS
      </div>
    </BentoCard>
  );
}

function FeatureEight() {
  return (
    <BentoCard className="relative flex flex-col bg-blue-200 sm:col-span-2">
      <WideCard />
      <div className="mt-4">
        <div className="text-lg font-black text-blue-800">Daily reminders</div>
        <p className="text-sm">Our daily reminder helps you keep focused on your goals.</p>
      </div>
    </BentoCard>
  );
}

// #endregion

export default function Eight() {
  return (
    <div className="full-content w-full min-w-0">
      <div className="grid w-full min-w-0 grid-cols-1 gap-3 sm:grid-cols-4 sm:grid-rows-3">
        <FeatureOne />
        <FeatureTwo />
        <FeatureThree />
        <FeatureFour />
        <FeatureFive />
        <FeatureSix />
        <FeatureSeven />
        <FeatureEight />
      </div>
    </div>
  );
}
```
