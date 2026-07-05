# Premium Custom Spinners & Loaders Code Database

This file contains the complete, self-contained HTML, CSS, and React code snippets for all **14 Premium Loader Components** featured in the interactive showcase. Each component is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Loader #1: Orbital Gooey Liquid Loader](#loader-1-orbital-gooey-liquid-loader)
2. [Loader #2: Infinity Loop Dash Trail](#loader-2-infinity-loop-dash-trail)
3. [Loader #3: Cyberpunk Tech Radar Scan](#loader-3-cyberpunk-tech-radar-scan)
4. [Loader #4: Isometric Wireframe Cube](#loader-4-isometric-wireframe-cube)
5. [Loader #5: Double Helix DNA Wave](#loader-5-double-helix-dna-wave)
6. [Loader #6: Fading Particle Orbit Ring](#loader-6-fading-particle-orbit-ring)
7. [Loader #7: Neumorphic Glowing Track](#loader-7-neumorphic-glowing-track)
8. [Loader #8: Shimmering Skeleton Image Card](#loader-8-shimmering-skeleton-image-card)
9. [Loader #9: Blur-Up Progressive Image](#loader-9-blur-up-progressive-image)
10. [Loader #10: Avatar Circular Halo Loader](#loader-10-avatar-circular-halo-loader)
11. [Loader #11: Progressive Image Swipe Loader](#loader-11-progressive-image-swipe-loader)
12. [Loader #12: Corner Glow Border Frame](#loader-12-corner-glow-border-frame)
13. [Loader #13: Circular Media Loading Ring](#loader-13-circular-media-loading-ring)
14. [Loader #14: Magic UI Spinning Text](#loader-14-magic-ui-spinning-text)

---

## Loader #1: Orbital Gooey Liquid Loader
*A liquid-like loader where orbiting spheres seamlessly merge and separate using advanced SVG blur and contrast color matrix filters.*

### HTML
```html
<div class="loader-container-gooey">
    <svg class="gooey-svg" width="0" height="0">
        <defs>
            <filter id="goo">
                <feGaussianBlur in="SourceGraphic" stdDeviation="6" result="blur" />
                <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 18 -7" result="goo" />
                <feBlend in="SourceGraphic" in2="goo" />
            </filter>
        </defs>
    </svg>
    <div class="gooey-dots">
        <div class="gooey-dot center-dot"></div>
        <div class="gooey-dot orbiting-dot orbit-1"></div>
        <div class="gooey-dot orbiting-dot orbit-2"></div>
        <div class="gooey-dot orbiting-dot orbit-3"></div>
    </div>
</div>
```

### CSS
```css
.loader-container-gooey {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #060913;
    border-radius: 12px;
}
.gooey-dots {
    position: relative;
    width: 120px;
    height: 120px;
    filter: url('#goo');
}
.gooey-dot {
    position: absolute;
    background: linear-gradient(135deg, #6366f1 0%, #a855f7 100%);
    border-radius: 50%;
}
.center-dot {
    top: 45px;
    left: 45px;
    width: 30px;
    height: 30px;
    animation: pulse-center 2s ease-in-out infinite alternate;
}
.orbiting-dot {
    width: 20px;
    height: 20px;
    top: 50px;
    left: 50px;
}
.orbit-1 {
    animation: rotate-orbit-1 2.4s cubic-bezier(0.445, 0.05, 0.55, 0.95) infinite;
}
.orbit-2 {
    animation: rotate-orbit-2 2.4s cubic-bezier(0.445, 0.05, 0.55, 0.95) infinite;
    animation-delay: 0.3s;
    background: linear-gradient(135deg, #3b82f6 0%, #06b6d4 100%);
}
.orbit-3 {
    animation: rotate-orbit-3 2.4s cubic-bezier(0.445, 0.05, 0.55, 0.95) infinite;
    animation-delay: 0.6s;
    background: linear-gradient(135deg, #ec4899 0%, #f43f5e 100%);
}
@keyframes pulse-center {
    0% { transform: scale(0.85); }
    100% { transform: scale(1.15); }
}
@keyframes rotate-orbit-1 {
    0% { transform: rotate(0deg) translate(-45px) scale(0.8); }
    50% { transform: rotate(180deg) translate(-45px) scale(1.2); }
    100% { transform: rotate(360deg) translate(-45px) scale(0.8); }
}
@keyframes rotate-orbit-2 {
    0% { transform: rotate(120deg) translate(-45px) scale(0.8); }
    50% { transform: rotate(300deg) translate(-45px) scale(1.2); }
    100% { transform: rotate(480deg) translate(-45px) scale(0.8); }
}
@keyframes rotate-orbit-3 {
    0% { transform: rotate(240deg) translate(-45px) scale(0.8); }
    50% { transform: rotate(420deg) translate(-45px) scale(1.2); }
    100% { transform: rotate(600deg) translate(-45px) scale(0.8); }
}
```

### React
```tsx
"use client";

import React from "react";

export function GooeyLiquidLoader() {
  return (
    <div className="relative flex items-center justify-center w-full h-[240px] bg-[#060913] rounded-xl overflow-hidden">
      <svg className="absolute w-0 h-0" width="0" height="0">
        <defs>
          <filter id="react-goo">
            <feGaussianBlur in="SourceGraphic" stdDeviation="6" result="blur" />
            <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 18 -7" result="goo" />
            <feBlend in="SourceGraphic" in2="goo" />
          </filter>
        </defs>
      </svg>
      <div className="relative w-[120px] h-[120px]" style={{ filter: "url(#react-goo)" }}>
        <div className="absolute top-[45px] left-[45px] w-[30px] h-[30px] rounded-full bg-gradient-to-br from-indigo-500 to-purple-500 animate-[pulse-center_2s_ease-in-out_infinite_alternate]" />
        <div className="absolute top-[50px] left-[50px] w-[20px] h-[20px] rounded-full bg-gradient-to-br from-indigo-500 to-purple-500 animate-[rotate-orbit-1_2.4s_cubic-bezier(0.445,0.05,0.55,0.95)_infinite]" />
        <div className="absolute top-[50px] left-[50px] w-[20px] h-[20px] rounded-full bg-gradient-to-br from-blue-500 to-cyan-500 delay-[0.3s] animate-[rotate-orbit-2_2.4s_cubic-bezier(0.445,0.05,0.55,0.95)_infinite]" style={{ animationDelay: "0.3s" }} />
        <div className="absolute top-[50px] left-[50px] w-[20px] h-[20px] rounded-full bg-gradient-to-br from-pink-500 to-rose-500 delay-[0.6s] animate-[rotate-orbit-3_2.4s_cubic-bezier(0.445,0.05,0.55,0.95)_infinite]" style={{ animationDelay: "0.6s" }} />
      </div>
    </div>
  );
}
```

---

## Loader #2: Infinity Loop Dash Trail
*A glowing, dual-colored infinity path where a bright neon dash flows continuously along the curve with trailing blurs.*

### HTML
```html
<div class="loader-container-infinity">
    <svg class="infinity-svg" viewBox="0 0 100 40">
        <defs>
            <linearGradient id="inf-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
                <stop offset="0%" stop-color="#06b6d4" />
                <stop offset="50%" stop-color="#3b82f6" />
                <stop offset="100%" stop-color="#6366f1" />
            </linearGradient>
            <filter id="glow" x="-20%" y="-20%" width="140%" height="140%">
                <feGaussianBlur stdDeviation="2.5" result="blur" />
                <feMerge>
                    <feMergeNode in="blur" />
                    <feMergeNode in="SourceGraphic" />
                </feMerge>
            </filter>
        </defs>
        <path class="infinity-bg-path" d="M30,20 C10,5 5,35 30,20 C55,5 90,5 70,20 C50,35 45,5 70,20 C95,35 90,5 70,20 C50,35 15,35 30,20 Z" />
        <path class="infinity-path" d="M30,20 C10,5 5,35 30,20 C55,5 90,5 70,20 C50,35 45,5 70,20 C95,35 90,5 70,20 C50,35 15,35 30,20 Z" />
    </svg>
</div>
```

### CSS
```css
.loader-container-infinity {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #080a10;
    border-radius: 12px;
}
.infinity-svg {
    width: 150px;
    height: auto;
}
.infinity-bg-path {
    fill: none;
    stroke: rgba(255, 255, 255, 0.03);
    stroke-width: 4px;
}
.infinity-path {
    fill: none;
    stroke: url(#inf-gradient);
    stroke-width: 4.5px;
    stroke-linecap: round;
    stroke-dasharray: 60 180;
    stroke-dashoffset: 0;
    animation: dash-loop 1.8s linear infinite;
    filter: url(#glow);
}
@keyframes dash-loop {
    0% { stroke-dashoffset: 0; }
    100% { stroke-dashoffset: -240; }
}
```

### React
```tsx
"use client";

import React from "react";

export function InfinityLoopLoader() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#080a10] rounded-xl overflow-hidden">
      <svg className="w-[150px] h-auto" viewBox="0 0 100 40">
        <defs>
          <linearGradient id="react-inf-gradient" x1="0%" y1="0%" x2="100%" y2="100%">
            <stop offset="0%" stopColor="#06b6d4" />
            <stop offset="50%" stopColor="#3b82f6" />
            <stop offset="100%" stopColor="#6366f1" />
          </linearGradient>
          <filter id="react-inf-glow" x="-20%" y="-20%" width="140%" height="140%">
            <feGaussianBlur stdDeviation="2.5" result="blur" />
            <feMerge>
              <feMergeNode in="blur" />
              <feMergeNode in="SourceGraphic" />
            </feMerge>
          </filter>
        </defs>
        <path
          className="fill-none stroke-white/5 stroke-[4]"
          d="M30,20 C10,5 5,35 30,20 C55,5 90,5 70,20 C50,35 45,5 70,20 C95,35 90,5 70,20 C50,35 15,35 30,20 Z"
        />
        <path
          className="fill-none stroke-[url(#react-inf-gradient)] stroke-[4.5] stroke-linecap-round animate-[dash-loop_1.8s_linear_infinite]"
          style={{
            strokeDasharray: "60 180",
            strokeDashoffset: 0,
            filter: "url(#react-inf-glow)"
          }}
          d="M30,20 C10,5 5,35 30,20 C55,5 90,5 70,20 C50,35 45,5 70,20 C95,35 90,5 70,20 C50,35 15,35 30,20 Z"
        />
      </svg>
    </div>
  );
}
```

---

## Loader #3: Cyberpunk Tech Radar Scan
*A telemetry system simulation featuring scanning lines, coordinate labels, and target-rich tracking dots that fade in and out.*

### HTML
```html
<div class="loader-container-radar">
    <div class="radar-box">
        <div class="radar-grid"></div>
        <div class="radar-scanline"></div>
        <div class="radar-inner-ring"></div>
        <div class="radar-outer-ring"></div>
        <div class="radar-dots">
            <span class="radar-dot d1"></span>
            <span class="radar-dot d2"></span>
        </div>
        <div class="radar-coords">SYS.LOAD // 82%</div>
    </div>
</div>
```

### CSS
```css
.loader-container-radar {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #03060a;
    border-radius: 12px;
}
.radar-box {
    position: relative;
    width: 130px;
    height: 130px;
    border: 1px solid rgba(16, 185, 129, 0.15);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}
.radar-grid {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-image: 
        radial-gradient(circle, transparent 30%, rgba(16, 185, 129, 0.05) 31%, rgba(16, 185, 129, 0.05) 32%, transparent 33%),
        radial-gradient(circle, transparent 60%, rgba(16, 185, 129, 0.05) 61%, rgba(16, 185, 129, 0.05) 62%, transparent 63%);
}
.radar-grid::before {
    content: '';
    position: absolute;
    top: 0;
    left: 50%;
    width: 1px;
    height: 100%;
    background: rgba(16, 185, 129, 0.1);
}
.radar-grid::after {
    content: '';
    position: absolute;
    top: 50%;
    left: 0;
    height: 1px;
    width: 100%;
    background: rgba(16, 185, 129, 0.1);
}
.radar-scanline {
    position: absolute;
    width: 50%;
    height: 50%;
    top: 0;
    left: 50%;
    background: linear-gradient(45deg, rgba(16, 185, 129, 0.3) 0%, transparent 60%);
    transform-origin: bottom left;
    border-radius: 0 100% 0 0;
    animation: radar-sweep 2.5s linear infinite;
}
.radar-inner-ring {
    position: absolute;
    width: 80px;
    height: 80px;
    border: 1px dashed rgba(16, 185, 129, 0.3);
    border-radius: 50%;
    animation: rotate-anti 8s linear infinite;
}
.radar-outer-ring {
    position: absolute;
    width: 110px;
    height: 110px;
    border: 1px solid rgba(16, 185, 129, 0.4);
    border-left-color: transparent;
    border-right-color: transparent;
    border-radius: 50%;
    animation: rotate-clockwise 3s linear infinite;
}
.radar-dot {
    position: absolute;
    width: 4px;
    height: 4px;
    background: #10b981;
    border-radius: 50%;
    box-shadow: 0 0 8px #10b981;
}
.radar-dot.d1 {
    top: 35px;
    left: 85px;
    animation: blink-dot 1.2s ease-in-out infinite alternate;
}
.radar-dot.d2 {
    bottom: 40px;
    left: 30px;
    animation: blink-dot 1.5s ease-in-out infinite alternate-reverse;
}
.radar-coords {
    position: absolute;
    bottom: -22px;
    font-family: monospace;
    font-size: 0.65rem;
    color: #10b981;
    letter-spacing: 1px;
    opacity: 0.8;
}
@keyframes radar-sweep {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}
@keyframes rotate-clockwise {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}
@keyframes rotate-anti {
    from { transform: rotate(360deg); }
    to { transform: rotate(0deg); }
}
@keyframes blink-dot {
    0% { opacity: 0.1; }
    100% { opacity: 1; }
}
```

### React
```tsx
"use client";

import React from "react";

export function CyberpunkRadarLoader() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#03060a] rounded-xl overflow-hidden font-mono text-[10px] text-emerald-500">
      <div className="relative w-[130px] h-[130px] border border-emerald-500/20 rounded-full flex items-center justify-center">
        <div className="absolute inset-0 rounded-full bg-[radial-gradient(circle,transparent_30%,rgba(16,185,129,0.05)_31%,rgba(16,185,129,0.05)_32%,transparent_33%)]" />
        <div className="absolute inset-0 rounded-full bg-[radial-gradient(circle,transparent_60%,rgba(16,185,129,0.05)_61%,rgba(16,185,129,0.05)_62%,transparent_63%)]" />
        <div className="absolute top-0 left-1/2 w-[1px] h-full bg-emerald-500/10" />
        <div className="absolute top-1/2 left-0 h-[1px] w-full bg-emerald-500/10" />
        <div className="absolute top-0 left-1/2 w-1/2 h-1/2 bg-gradient-to-tr from-emerald-500/30 to-transparent origin-bottom-left rounded-tr-full animate-[radar-sweep_2.5s_linear_infinite]" />
        <div className="absolute w-[80px] h-[80px] border border-dashed border-emerald-500/30 rounded-full animate-[rotate-anti_8s_linear_infinite]" />
        <div className="absolute w-[110px] h-[110px] border-y border-x-transparent border-emerald-500/40 rounded-full animate-[rotate-clockwise_3s_linear_infinite]" />
        <div className="absolute top-[35px] left-[85px] w-1 h-1 bg-emerald-500 rounded-full shadow-[0_0_8px_#10b981] animate-[blink-dot_1.2s_ease-in-out_infinite_alternate]" />
        <div className="absolute bottom-[40px] left-[30px] w-1 h-1 bg-emerald-500 rounded-full shadow-[0_0_8px_#10b981] animate-[blink-dot_1.5s_ease-in-out_infinite_alternate-reverse]" />
        <div className="absolute -bottom-[22px] tracking-widest opacity-80 text-[10px]">SYS.LOAD // 82%</div>
      </div>
    </div>
  );
}
```

---

## Loader #4: Isometric Wireframe Cube
*A 3D perspective wireframe cube rotating on dual-axes with glowing colored corners.*

### HTML
```html
<div class="loader-container-cube">
    <div class="cube-scene">
        <div class="isometric-cube">
            <div class="cube-face front"></div>
            <div class="cube-face back"></div>
            <div class="cube-face left"></div>
            <div class="cube-face right"></div>
            <div class="cube-face top"></div>
            <div class="cube-face bottom"></div>
        </div>
    </div>
</div>
```

### CSS
```css
.loader-container-cube {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #090a0f;
    border-radius: 12px;
}
.cube-scene {
    width: 60px;
    height: 60px;
    perspective: 300px;
}
.isometric-cube {
    width: 100%;
    height: 100%;
    position: relative;
    transform-style: preserve-3d;
    transform: rotateX(-35deg) rotateY(45deg);
    animation: rotate-cube 4s infinite ease-in-out;
}
.cube-face {
    position: absolute;
    width: 60px;
    height: 60px;
    border: 2px solid #ec4899;
    background: rgba(236, 72, 153, 0.03);
    box-shadow: 0 0 10px rgba(236, 72, 153, 0.15);
    box-sizing: border-box;
}
.front  { transform: rotateY(0deg) translateZ(30px); border-color: #3b82f6; box-shadow: 0 0 10px rgba(59, 130, 246, 0.15); }
.back   { transform: rotateY(180deg) translateZ(30px); border-color: #6366f1; box-shadow: 0 0 10px rgba(99, 102, 241, 0.15); }
.left   { transform: rotateY(-90deg) translateZ(30px); border-color: #a855f7; box-shadow: 0 0 10px rgba(168, 85, 247, 0.15); }
.right  { transform: rotateY(90deg) translateZ(30px); border-color: #ec4899; box-shadow: 0 0 10px rgba(236, 72, 153, 0.15); }
.top    { transform: rotateX(90deg) translateZ(30px); border-color: #06b6d4; box-shadow: 0 0 10px rgba(6, 182, 212, 0.15); }
.bottom { transform: rotateX(-90deg) translateZ(30px); border-color: #10b981; box-shadow: 0 0 10px rgba(16, 185, 129, 0.15); }

@keyframes rotate-cube {
    0% { transform: rotateX(-35deg) rotateY(45deg) scale(1); }
    25% { transform: rotateX(145deg) rotateY(45deg) scale(0.85); }
    50% { transform: rotateX(145deg) rotateY(225deg) scale(1); }
    75% { transform: rotateX(-35deg) rotateY(225deg) scale(0.85); }
    100% { transform: rotateX(-35deg) rotateY(405deg) scale(1); }
}
```

### React
```tsx
"use client";

import React from "react";

export function IsometricCubeLoader() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#090a0f] rounded-xl overflow-hidden">
      <div className="w-[60px] h-[60px] [perspective:300px]">
        <div className="relative w-full h-full [transform-style:preserve-3d] [transform:rotateX(-35deg)_rotateY(45deg)] animate-[rotate-cube_4s_infinite_ease-in-out]">
          <div className="absolute w-[60px] h-[60px] border-2 bg-blue-500/5 shadow-[0_0_10px_rgba(59,130,246,0.15)] [transform:rotateY(0deg)_translateZ(30px)] border-blue-500" />
          <div className="absolute w-[60px] h-[60px] border-2 bg-indigo-500/5 shadow-[0_0_10px_rgba(99,102,241,0.15)] [transform:rotateY(180deg)_translateZ(30px)] border-indigo-500" />
          <div className="absolute w-[60px] h-[60px] border-2 bg-purple-500/5 shadow-[0_0_10px_rgba(168,85,247,0.15)] [transform:rotateY(-90deg)_translateZ(30px)] border-purple-500" />
          <div className="absolute w-[60px] h-[60px] border-2 bg-pink-500/5 shadow-[0_0_10px_rgba(236,72,153,0.15)] [transform:rotateY(90deg)_translateZ(30px)] border-pink-500" />
          <div className="absolute w-[60px] h-[60px] border-2 bg-cyan-500/5 shadow-[0_0_10px_rgba(6,182,212,0.15)] [transform:rotateX(90deg)_translateZ(30px)] border-cyan-500" />
          <div className="absolute w-[60px] h-[60px] border-2 bg-emerald-500/5 shadow-[0_0_10px_rgba(16,185,129,0.15)] [transform:rotateX(-90deg)_translateZ(30px)] border-emerald-500" />
        </div>
      </div>
    </div>
  );
}
```

---

## Loader #5: Double Helix DNA Wave
*An interactive double helix strand simulation showing a smooth sinusoidal bounce with dual color-ways.*

### HTML
```html
<div class="loader-container-dna">
    <div class="dna-helix">
        <div class="dna-strand" style="--i: 1"></div>
        <div class="dna-strand" style="--i: 2"></div>
        <div class="dna-strand" style="--i: 3"></div>
        <div class="dna-strand" style="--i: 4"></div>
        <div class="dna-strand" style="--i: 5"></div>
        <div class="dna-strand" style="--i: 6"></div>
        <div class="dna-strand" style="--i: 7"></div>
        <div class="dna-strand" style="--i: 8"></div>
        <div class="dna-strand" style="--i: 9"></div>
        <div class="dna-strand" style="--i: 10"></div>
        <div class="dna-strand" style="--i: 11"></div>
        <div class="dna-strand" style="--i: 12"></div>
    </div>
</div>
```

### CSS
```css
.loader-container-dna {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #05060b;
    border-radius: 12px;
}
.dna-helix {
    display: flex;
    gap: 7px;
}
.dna-strand {
    position: relative;
    width: 4px;
    height: 60px;
    background: rgba(255, 255, 255, 0.04);
    border-radius: 2px;
}
.dna-strand::before, .dna-strand::after {
    content: '';
    position: absolute;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    left: -2px;
    animation: dna-bounce 2s ease-in-out infinite;
    animation-delay: calc(var(--i) * 0.12s);
}
.dna-strand::before {
    background: #6366f1;
    box-shadow: 0 0 8px rgba(99, 102, 241, 0.6);
    top: 0;
}
.dna-strand::after {
    background: #ec4899;
    box-shadow: 0 0 8px rgba(236, 72, 153, 0.6);
    bottom: 0;
    animation-name: dna-bounce-reverse;
}
@keyframes dna-bounce {
    0%, 100% {
        transform: translateY(0) scale(1);
        opacity: 1;
    }
    50% {
        transform: translateY(52px) scale(0.6);
        opacity: 0.4;
        background: #a855f7;
    }
}
@keyframes dna-bounce-reverse {
    0%, 100% {
        transform: translateY(0) scale(1);
        opacity: 1;
    }
    50% {
        transform: translateY(-52px) scale(0.6);
        opacity: 0.4;
        background: #3b82f6;
    }
}
```

### React
```tsx
"use client";

import React from "react";

export function DnaHelixLoader() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#05060b] rounded-xl overflow-hidden">
      <div className="flex gap-[7px]">
        {Array.from({ length: 12 }).map((_, i) => (
          <div
            key={i}
            className="relative w-1 h-[60px] bg-white/5 rounded-[2px] before:content-[''] before:absolute before:w-2 before:h-2 before:rounded-full before:-left-[2px] before:top-0 before:bg-indigo-500 before:shadow-[0_0_8px_rgba(99,102,241,0.6)] before:animate-[dna-bounce_2s_ease-in-out_infinite] after:content-[''] after:absolute after:w-2 after:h-2 after:rounded-full after:-left-[2px] after:bottom-0 after:bg-pink-500 after:shadow-[0_0_8px_rgba(236,72,153,0.6)] after:animate-[dna-bounce-reverse_2s_ease-in-out_infinite]"
            style={{
              // @ts-ignore
              "--i": i + 1,
              beforeDelay: `${(i + 1) * 0.12}s`,
              afterDelay: `${(i + 1) * 0.12}s`,
            }}
          />
        ))}
      </div>
    </div>
  );
}
```

---

## Loader #6: Fading Particle Orbit Ring
*A circular trail of glowing light points spinning synchronously to indicate progressive activities.*

### HTML
```html
<div class="loader-container-particles">
    <div class="particle-spinner">
        <span style="--r: 1; --d: 0s"></span>
        <span style="--r: 2; --d: 0.12s"></span>
        <span style="--r: 3; --d: 0.24s"></span>
        <span style="--r: 4; --d: 0.36s"></span>
        <span style="--r: 5; --d: 0.48s"></span>
        <span style="--r: 6; --d: 0.6s"></span>
        <span style="--r: 7; --d: 0.72s"></span>
        <span style="--r: 8; --d: 0.84s"></span>
    </div>
</div>
```

### CSS
```css
.loader-container-particles {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #080913;
    border-radius: 12px;
}
.particle-spinner {
    position: relative;
    width: 75px;
    height: 75px;
}
.particle-spinner span {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transform: rotate(calc(var(--r) * 45deg));
}
.particle-spinner span::before {
    content: '';
    position: absolute;
    top: 0;
    left: calc(50% - 4px);
    width: 8px;
    height: 8px;
    background: linear-gradient(135deg, #06b6d4 0%, #3b82f6 100%);
    border-radius: 50%;
    box-shadow: 0 0 10px #06b6d4, 0 0 20px #3b82f6;
    animation: particle-fade 0.96s linear infinite;
    animation-delay: var(--d);
}
@keyframes particle-fade {
    0% {
        transform: scale(1.2);
        opacity: 1;
    }
    100% {
        transform: scale(0.2);
        opacity: 0.1;
    }
}
```

### React
```tsx
"use client";

import React from "react";

export function ParticleOrbitLoader() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#080913] rounded-xl overflow-hidden">
      <div className="relative w-[75px] h-[75px]">
        {Array.from({ length: 8 }).map((_, idx) => (
          <span
            key={idx}
            className="absolute top-0 left-0 w-full h-full before:content-[''] before:absolute before:top-0 before:left-[calc(50%-4px)] before:w-2 before:h-2 before:bg-gradient-to-br before:from-cyan-500 before:to-blue-500 before:rounded-full before:shadow-[0_0_10px_#06b6d4,0_0_20px_#3b82f6] before:animate-[particle-fade_0.96s_linear_infinite]"
            style={{
              // @ts-ignore
              "--r": idx + 1,
              "--d": `${idx * 0.12}s`,
              transform: `rotate(${(idx + 1) * 45}deg)`
            }}
          />
        ))}
      </div>
    </div>
  );
}
```

---

## Loader #7: Neumorphic Glowing Track
*A neumorphic design spinner with inset track channels and a neon blue handle tracking the loop.*

### HTML
```html
<div class="loader-container-neumorphic">
    <div class="neu-spinner-track">
        <div class="neu-spinner-handle"></div>
    </div>
</div>
```

### CSS
```css
.loader-container-neumorphic {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #0b0f19;
    border-radius: 12px;
}
.neu-spinner-track {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: #0b0f19;
    box-shadow: 
        inset 4px 4px 10px rgba(0, 0, 0, 0.4),
        inset -4px -4px 10px rgba(255, 255, 255, 0.03);
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
}
.neu-spinner-handle {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 3px solid transparent;
    border-top-color: #6366f1;
    animation: neu-rotate 1.2s cubic-bezier(0.5, 0.1, 0.4, 0.9) infinite;
    box-sizing: border-box;
    filter: drop-shadow(0 0 6px rgba(99, 102, 241, 0.6));
}
.neu-spinner-track::after {
    content: '';
    position: absolute;
    width: 64px;
    height: 64px;
    border-radius: 50%;
    background: #0b0f19;
    box-shadow: 
        4px 4px 10px rgba(0, 0, 0, 0.4),
        -4px -4px 10px rgba(255, 255, 255, 0.03);
}
@keyframes neu-rotate {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}
```

### React
```tsx
"use client";

import React from "react";

export function NeumorphicLoader() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#0b0f19] rounded-xl overflow-hidden">
      <div className="relative w-20 h-20 rounded-full bg-[#0b0f19] shadow-[inset_4px_4px_10px_rgba(0,0,0,0.4),inset_-4px_-4px_10px_rgba(255,255,255,0.03)] flex items-center justify-center">
        <div className="absolute w-full h-full rounded-full border-3 border-transparent border-t-indigo-500 animate-[neu-rotate_1.2s_cubic-bezier(0.5,0.1,0.4,0.9)_infinite] [filter:drop-shadow(0_0_6px_rgba(99,102,241,0.6))]" />
        <div className="w-16 h-16 rounded-full bg-[#0b0f19] shadow-[4px_4px_10px_rgba(0,0,0,0.4),-4px_-4px_10px_rgba(255,255,255,0.03)]" />
      </div>
    </div>
  );
}
```

---

## Loader #8: Shimmering Skeleton Image Card
*A shimmer layout simulator overlaying profile, header, and description placeholders with animated diagonal highlight bars.*

### HTML
```html
<div class="skeleton-card">
    <div class="skeleton-media shimmer"></div>
    <div class="skeleton-info">
        <div class="skeleton-title shimmer"></div>
        <div class="skeleton-text shimmer"></div>
        <div class="skeleton-text shimmer short"></div>
    </div>
</div>
```

### CSS
```css
.skeleton-card {
    width: 280px;
    background: #111625;
    border: 1px solid rgba(255,255,255,0.05);
    border-radius: 12px;
    padding: 12px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.3);
}
.skeleton-media {
    width: 100%;
    height: 140px;
    background: rgba(255,255,255,0.03);
    border-radius: 8px;
}
.skeleton-info {
    margin-top: 15px;
}
.skeleton-title {
    width: 60%;
    height: 16px;
    background: rgba(255,255,255,0.04);
    border-radius: 4px;
    margin-bottom: 10px;
}
.skeleton-text {
    width: 100%;
    height: 10px;
    background: rgba(255,255,255,0.02);
    border-radius: 4px;
    margin-bottom: 8px;
}
.skeleton-text.short {
    width: 40%;
}
.shimmer {
    position: relative;
    overflow: hidden;
}
.shimmer::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(
        90deg,
        transparent,
        rgba(255, 255, 255, 0.05),
        transparent
    );
    transform: translateX(-100%);
    animation: shimmer-swipe 1.6s infinite;
}
@keyframes shimmer-swipe {
    100% {
        transform: translateX(100%);
    }
}
```

### React
```tsx
"use client";

import React from "react";

export function ShimmeringSkeletonCard() {
  return (
    <div className="w-[280px] bg-[#111625] border border-white/5 rounded-xl p-3 shadow-lg">
      <div className="relative overflow-hidden w-full h-[140px] bg-white/5 rounded-lg before:content-[''] before:absolute before:inset-0 before:bg-gradient-to-r before:from-transparent before:via-white/5 before:to-transparent before:-translate-x-full before:animate-[shimmer-swipe_1.6s_infinite]" />
      <div className="mt-4">
        <div className="relative overflow-hidden w-3/5 h-4 bg-white/10 rounded mb-2.5 before:content-[''] before:absolute before:inset-0 before:bg-gradient-to-r before:from-transparent before:via-white/5 before:to-transparent before:-translate-x-full before:animate-[shimmer-swipe_1.6s_infinite]" />
        <div className="relative overflow-hidden w-full h-2.5 bg-white/5 rounded mb-2 before:content-[''] before:absolute before:inset-0 before:bg-gradient-to-r before:from-transparent before:via-white/5 before:to-transparent before:-translate-x-full before:animate-[shimmer-swipe_1.6s_infinite]" />
        <div className="relative overflow-hidden w-2/5 h-2.5 bg-white/5 rounded before:content-[''] before:absolute before:inset-0 before:bg-gradient-to-r before:from-transparent before:via-white/5 before:to-transparent before:-translate-x-full before:animate-[shimmer-swipe_1.6s_infinite]" />
      </div>
    </div>
  );
}
```

---

## Loader #9: Blur-Up Progressive Image
*A progressive loader that smooths a low-res image blur to high-res sharpness once fully downloaded.*

### HTML
```html
<div class="blur-up-card">
    <div class="blur-up-wrapper">
        <img class="blur-img placeholder" src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=20&q=10" alt="lowres" />
        <img class="blur-img target-img" src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=300&q=80" onload="imageLoaded(this)" alt="highres" />
        <div class="blur-spinner"></div>
    </div>
</div>
```

### CSS
```css
.blur-up-card {
    width: 280px;
    height: 180px;
    border-radius: 12px;
    overflow: hidden;
    position: relative;
    border: 1px solid rgba(255,255,255,0.05);
}
.blur-up-wrapper {
    width: 100%;
    height: 100%;
    position: relative;
}
.blur-img {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: filter 1.2s ease, opacity 1s ease;
}
.blur-img.placeholder {
    filter: blur(10px);
    z-index: 1;
}
.blur-img.target-img {
    opacity: 0;
    z-index: 2;
}
.blur-img.target-img.loaded {
    opacity: 1;
}
.blur-img.target-img.loaded ~ .placeholder {
    opacity: 0;
}
.blur-img.target-img.loaded ~ .blur-spinner {
    opacity: 0;
    pointer-events: none;
}
.blur-spinner {
    position: absolute;
    top: calc(50% - 20px);
    left: calc(50% - 20px);
    width: 40px;
    height: 40px;
    border: 3px solid rgba(255,255,255,0.1);
    border-top-color: #6366f1;
    border-radius: 50%;
    z-index: 3;
    animation: spin-blur-loader 0.8s linear infinite;
    transition: opacity 0.5s;
}
@keyframes spin-blur-loader {
    100% { transform: rotate(360deg); }
}
```

### React
```tsx
"use client";

import React, { useState } from "react";

export function BlurUpImageLoader() {
  const [loaded, setLoaded] = useState(false);

  return (
    <div className="relative w-[280px] h-[180px] rounded-xl overflow-hidden border border-white/5">
      <img
        src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=20&q=10"
        className={`absolute inset-0 w-full h-full object-cover blur-md transition-opacity duration-1000 ${loaded ? "opacity-0" : "opacity-100"}`}
        alt="placeholder"
      />
      <img
        src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=300&q=80"
        className={`absolute inset-0 w-full h-full object-cover transition-opacity duration-1000 ${loaded ? "opacity-100" : "opacity-0"}`}
        onLoad={() => setLoaded(true)}
        alt="target"
      />
      {!loaded && (
        <div className="absolute inset-0 flex items-center justify-center bg-black/20">
          <div className="w-10 h-10 border-3 border-white/10 border-t-indigo-500 rounded-full animate-spin" />
        </div>
      )}
    </div>
  );
}
```

---

## Loader #10: Avatar Circular Halo Loader
*An avatar card featuring a circular conic gradient halo spinner orbiting around the border profile photo.*

### HTML
```html
<div class="avatar-loader-card">
    <div class="avatar-ring-container">
        <div class="avatar-ring-spinner"></div>
        <img class="avatar-img" src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=100&q=80" alt="avatar" />
    </div>
    <div class="avatar-details">
        <h4>Jane Doe</h4>
        <p>Product Designer</p>
    </div>
</div>
```

### CSS
```css
.avatar-loader-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    background: #101524;
    border: 1px solid rgba(255,255,255,0.05);
    border-radius: 12px;
    padding: 20px;
    width: 220px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.3);
}
.avatar-ring-container {
    position: relative;
    width: 90px;
    height: 90px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.avatar-ring-spinner {
    position: absolute;
    inset: 0;
    border-radius: 50%;
    background: conic-gradient(from 0deg, #6366f1 0%, #ec4899 50%, transparent 80%);
    animation: spin-avatar 1.5s linear infinite;
    mask: radial-gradient(circle, transparent 40px, black 41px);
    -webkit-mask: radial-gradient(circle, transparent 40px, black 41px);
}
.avatar-img {
    width: 76px;
    height: 76px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid #101524;
    z-index: 2;
}
.avatar-details {
    margin-top: 15px;
    text-align: center;
}
.avatar-details h4 {
    color: #fff;
    font-size: 0.95rem;
    font-weight: 600;
}
.avatar-details p {
    color: #94a3b8;
    font-size: 0.72rem;
    margin-top: 2px;
}
@keyframes spin-avatar {
    100% { transform: rotate(360deg); }
}
```

### React
```tsx
"use client";

import React from "react";

export function AvatarHaloLoader() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#0d131f] rounded-xl overflow-hidden">
      <div className="flex flex-col items-center bg-[#101524] border border-white/5 rounded-xl p-5 w-[220px] shadow-lg">
        <div className="relative w-[90px] h-[90px] flex items-center justify-center">
          <div
            className="absolute inset-0 rounded-full bg-[conic-gradient(from_0deg,#6366f1_0%,#ec4899_50%,transparent_80%)] animate-spin"
            style={{
              mask: "radial-gradient(circle, transparent 40px, black 41px)",
              WebkitMask: "radial-gradient(circle, transparent 40px, black 41px)"
            }}
          />
          <img
            src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=100&q=80"
            className="w-[76px] h-[76px] rounded-full object-cover border-2 border-[#101524] z-10"
            alt="user"
          />
        </div>
        <div className="mt-4 text-center">
          <h4 className="text-white text-sm font-semibold">Jane Doe</h4>
          <p className="text-slate-400 text-xs mt-0.5">Product Designer</p>
        </div>
      </div>
    </div>
  );
}
```

---

## Loader #11: Progressive Image Swipe Loader
*An image container featuring a neon scanning sweep bar that slides left and right with fading opacity overlay pulses.*

### HTML
```html
<div class="swipe-loader-card">
    <div class="swipe-image-wrapper">
        <img class="swipe-img" src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=300&q=80" alt="product" />
        <div class="swipe-bar"></div>
        <div class="swipe-overlay"></div>
    </div>
</div>
```

### CSS
```css
.swipe-loader-card {
    width: 280px;
    height: 180px;
    border-radius: 12px;
    overflow: hidden;
    position: relative;
    border: 1px solid rgba(255,255,255,0.05);
}
.swipe-image-wrapper {
    width: 100%;
    height: 100%;
    position: relative;
    background: #0f131f;
}
.swipe-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0.9;
}
.swipe-bar {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 3px;
    background: linear-gradient(to bottom, #06b6d4, #6366f1);
    box-shadow: 0 0 10px #06b6d4, 0 0 20px #6366f1;
    left: 0;
    animation: swipe-scan 2.2s ease-in-out infinite;
    z-index: 3;
}
.swipe-overlay {
    position: absolute;
    inset: 0;
    background: rgba(10, 14, 23, 0.4);
    z-index: 2;
    animation: swipe-overlay-pulse 2.2s ease-in-out infinite;
}
@keyframes swipe-scan {
    0% { left: 0%; }
    50% { left: 100%; }
    100% { left: 0%; }
}
@keyframes swipe-overlay-pulse {
    0%, 100% { opacity: 0.6; }
    50% { opacity: 0.1; }
}
```

### React
```tsx
"use client";

import React from "react";

export function ProgressiveImageSwipeLoader() {
  return (
    <div className="relative w-[280px] h-[180px] rounded-xl overflow-hidden border border-white/5 bg-[#0f131f]">
      <img
        src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=300&q=80"
        className="w-full h-full object-cover opacity-90"
        alt="product"
      />
      <div className="absolute inset-y-0 w-[3px] bg-gradient-to-b from-cyan-500 to-indigo-500 shadow-[0_0_10px_#06b6d4,0_0_20px_#6366f1] animate-[swipe-scan_2.2s_ease-in-out_infinite]" />
      <div className="absolute inset-0 bg-black/40 z-10 animate-[swipe-overlay-pulse_2.2s_ease-in-out_infinite]" />
    </div>
  );
}
```

---

## Loader #12: Corner Glow Border Frame
*An image display frame where the surrounding border border-line spins to illuminate each corner sequentially.*

### HTML
```html
<div class="frame-loader-card">
    <div class="frame-border-spinner"></div>
    <div class="frame-content">
        <img src="https://images.unsplash.com/photo-1502082553048-f009c37129b9?w=300&q=80" alt="nature" />
    </div>
</div>
```

### CSS
```css
.frame-loader-card {
    position: relative;
    width: 250px;
    height: 180px;
    border-radius: 12px;
    overflow: hidden;
    padding: 3px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #0d1220;
}
.frame-border-spinner {
    position: absolute;
    width: 150%;
    height: 150%;
    background: conic-gradient(from 0deg, #ec4899 0%, #3b82f6 30%, transparent 60%);
    animation: frame-spin 3s linear infinite;
    z-index: 1;
}
.frame-content {
    position: relative;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    overflow: hidden;
    z-index: 2;
    background: #0d1220;
}
.frame-content img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
@keyframes frame-spin {
    100% { transform: rotate(360deg); }
}
```

### React
```tsx
"use client";

import React from "react";

export function CornerGlowBorderLoader() {
  return (
    <div className="relative w-[250px] h-[180px] rounded-xl overflow-hidden p-[3px] flex items-center justify-center bg-[#0d1220] shadow-lg">
      <div className="absolute w-[150%] h-[150%] bg-[conic-gradient(from_0deg,#ec4899_0%,#3b82f6_30%,transparent_60%)] animate-spin z-0" />
      <div className="relative w-full h-full rounded-[10px] overflow-hidden z-10 bg-[#0d1220]">
        <img
          src="https://images.unsplash.com/photo-1502082553048-f009c37129b9?w=300&q=80"
          className="w-full h-full object-cover"
          alt="nature"
        />
      </div>
    </div>
  );
}
```

---

## Loader #13: Circular Media Loading Ring
*An audio/video player loading ring circling around the track art album thumbnail with progress bar indicator loops.*

### HTML
```html
<div class="media-loader-card">
    <div class="media-art-wrap">
        <svg class="media-ring-svg" viewBox="0 0 100 100">
            <circle class="media-ring-bg" cx="50" cy="50" r="44" />
            <circle class="media-ring-val" cx="50" cy="50" r="44" />
        </svg>
        <img class="media-art-img" src="https://images.unsplash.com/photo-1514525253161-7a46d19cd819?w=100&q=80" alt="art" />
    </div>
    <div class="media-meta">
        <h5>Synthesized Dreams</h5>
        <p>Loading audio stream...</p>
    </div>
</div>
```

### CSS
```css
.media-loader-card {
    display: flex;
    align-items: center;
    background: #111625;
    border: 1px solid rgba(255,255,255,0.05);
    border-radius: 12px;
    padding: 12px 18px;
    width: 280px;
    gap: 15px;
}
.media-art-wrap {
    position: relative;
    width: 60px;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.media-ring-svg {
    position: absolute;
    inset: 0;
    transform: rotate(-90deg);
}
.media-ring-bg {
    fill: none;
    stroke: rgba(255,255,255,0.03);
    stroke-width: 5px;
}
.media-ring-val {
    fill: none;
    stroke: #06b6d4;
    stroke-width: 5px;
    stroke-linecap: round;
    stroke-dasharray: 276.46;
    stroke-dashoffset: 276.46;
    animation: media-progress-anim 2.5s ease-in-out infinite;
}
.media-art-img {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    object-fit: cover;
    z-index: 2;
}
.media-meta {
    flex: 1;
}
.media-meta h5 {
    color: #fff;
    font-size: 0.85rem;
    font-weight: 600;
}
.media-meta p {
    color: #06b6d4;
    font-size: 0.7rem;
    margin-top: 2px;
    animation: pulse-loading-text 1.5s ease-in-out infinite;
}
@keyframes media-progress-anim {
    0% { stroke-dashoffset: 276.46; }
    50% { stroke-dashoffset: 70; }
    100% { stroke-dashoffset: 0; }
}
@keyframes pulse-loading-text {
    0%, 100% { opacity: 0.6; }
    50% { opacity: 1; }
}
```

### React
```tsx
"use client";

import React from "react";

export function MediaLoadingRing() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#0d131f] rounded-xl overflow-hidden">
      <div className="flex items-center bg-[#111625] border border-white/5 rounded-xl p-3 px-4.5 w-[280px] gap-3.5">
        <div className="relative w-[60px] h-[60px] flex items-center justify-center">
          <svg className="absolute inset-0 -rotate-90" viewBox="0 0 100 100">
            <circle className="fill-none stroke-white/5 stroke-[5]" cx="50" cy="50" r="44" />
            <circle
              className="fill-none stroke-cyan-500 stroke-[5] stroke-linecap-round animate-[media-progress-anim_2.5s_ease-in-out_infinite]"
              cx="50"
              cy="50"
              r="44"
              style={{
                strokeDasharray: 276.46,
                strokeDashoffset: 276.46
              }}
            />
          </svg>
          <img
            src="https://images.unsplash.com/photo-1514525253161-7a46d19cd819?w=100&q=80"
            className="w-12 h-12 rounded-full object-cover z-10"
            alt="art"
          />
        </div>
        <div className="flex-1">
          <h5 className="text-white text-xs font-semibold">Synthesized Dreams</h5>
          <p className="text-cyan-500 text-[10px] mt-0.5 animate-pulse">Loading audio stream...</p>
        </div>
      </div>
    </div>
  );
}

---

## Loader #14: Magic UI Spinning Text
*A circular rotating text loader layout based on Magic UI components using relative letter offsets and rotate transformations.*

### HTML
```html
<div class="loader-container-spinning-text">
    <div class="spinning-text" style="--total: 35; --radius: 5.25;">
        <span style="--index: 0">l</span>
        <span style="--index: 1">e</span>
        <span style="--index: 2">a</span>
        <span style="--index: 3">r</span>
        <span style="--index: 4">n</span>
        <span style="--index: 5"> </span>
        <span style="--index: 6">m</span>
        <span style="--index: 7">o</span>
        <span style="--index: 8">r</span>
        <span style="--index: 9">e</span>
        <span style="--index: 10"> </span>
        <span style="--index: 11">•</span>
        <span style="--index: 12"> </span>
        <span style="--index: 13">e</span>
        <span style="--index: 14">a</span>
        <span style="--index: 15">r</span>
        <span style="--index: 16">n</span>
        <span style="--index: 17"> </span>
        <span style="--index: 18">m</span>
        <span style="--index: 19">o</span>
        <span style="--index: 20">r</span>
        <span style="--index: 21">e</span>
        <span style="--index: 22"> </span>
        <span style="--index: 23">•</span>
        <span style="--index: 24"> </span>
        <span style="--index: 25">g</span>
        <span style="--index: 26">r</span>
        <span style="--index: 27">o</span>
        <span style="--index: 28">w</span>
        <span style="--index: 29"> </span>
        <span style="--index: 30">m</span>
        <span style="--index: 31">o</span>
        <span style="--index: 32">r</span>
        <span style="--index: 33">e</span>
        <span style="--index: 34"> </span>
    </div>
</div>
```

### CSS
```css
.loader-container-spinning-text {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    background: #090e1a;
    border-radius: 12px;
    position: relative;
    overflow: hidden;
}
.spinning-text {
    position: relative;
    width: 140px;
    height: 140px;
    display: flex;
    align-items: center;
    justify-content: center;
    animation: spinning-text-rotate 10s linear infinite;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
    font-size: 0.85rem;
    color: #6366f1;
    text-transform: uppercase;
    letter-spacing: 0.1em;
}
.spinning-text span {
    position: absolute;
    top: 50%;
    left: 50%;
    display: inline-block;
    transform: translate(-50%, -50%) rotate(calc(360deg / var(--total) * var(--index))) translateY(calc(var(--radius, 5) * -1ch));
    transform-origin: center;
}
@keyframes spinning-text-rotate {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}
```

### React
```tsx
"use client";

import React from "react";
import { SpinningText } from "@/components/ui/spinning-text";

export function SpinningTextDemo() {
  return (
    <div className="flex w-full h-[240px] items-center justify-center bg-[#090e1a] rounded-xl overflow-hidden">
      <SpinningText
        radius={5.25}
        duration={10}
        className="font-mono text-[0.85rem] font-semibold uppercase text-indigo-500 tracking-wider"
      >
        learn more • earn more • grow more •
      </SpinningText>
    </div>
  );
}
```
```

