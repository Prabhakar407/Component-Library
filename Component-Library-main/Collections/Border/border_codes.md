# Premium Custom Border Code Database

This file contains the complete, self-contained HTML, CSS, and React code snippets for all **20 Premium Borders** featured in the interactive showcase. Each border is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Effect #1: Neon Pulse Border](#effect-1-neon-pulse-border)
2. [Effect #2: Animated Snake Border](#effect-2-animated-snake-border)
3. [Effect #3: Marching Dots Border](#effect-3-marching-dots-border)
4. [Effect #4: Corner Bracket Focus Frame](#effect-4-corner-bracket-focus-frame)
5. [Effect #5: Conic Shimmer Glow](#effect-5-conic-shimmer-glow)
6. [Effect #6: Double Slide Border](#effect-6-double-slide-border)
7. [Effect #7: Cyberpunk Glitch Border](#effect-7-cyberpunk-glitch-border)
8. [Effect #8: Gradient Draw Lines](#effect-8-gradient-draw-lines)
9. [Effect #9: Cosmic Aurora Pulse](#effect-9-cosmic-aurora-pulse)
10. [Effect #10: Glassmorphism Frost Highlight](#effect-10-glassmorphism-frost-highlight)
11. [Effect #11: Pulse Wave Echo](#effect-11-pulse-wave-echo)
12. [Effect #12: Electric Plasma Flow](#effect-12-electric-plasma-flow)
13. [Effect #13: Neon Ripple Flow](#effect-13-neon-ripple-flow)
14. [Effect #14: Shimmering Starlight](#effect-14-shimmering-starlight)
15. [Effect #15: Retro Wave Grid Sweep](#effect-15-retro-wave-grid-sweep)
16. [Effect #16: Volumetric Shadow Eclipse](#effect-16-volumetric-shadow-eclipse)
17. [Effect #17: Mouse Spotlight Glow](#effect-17-mouse-spotlight-glow)
18. [Effect #18: Interactive Glow Card (React)](#effect-18-interactive-glow-card-react)
19. [Effect #19: Sparkles Core (React)](#effect-19-sparkles-core-react)
20. [Effect #20: CTA Section Glow (React)](#effect-20-cta-section-glow-react)
21. [Effect #21: CTA Section Glow v2 (React)](#effect-21-cta-section-glow-v2-react)
22. [Effect #22: Shine Border (React)](#effect-22-shine-border-react)

---

## Effect #1: Neon Pulse Border
*A pulsing glowing outline border that flares up smoothly on hover to create a beautiful neon depth projection.*

### HTML
```html
<div class="border-box border-effect-1">
    <span class="border-text">Neon Pulse</span>
</div>
```

### CSS
```css
.border-effect-1 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    box-shadow: 0 0 0 2px rgba(99, 102, 241, 0.2);
    transition: all 0.3s ease;
}
.border-effect-1:hover {
    box-shadow: 0 0 0 3px #6366f1, 0 0 20px rgba(99, 102, 241, 0.6);
    background: #111524;
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #2: Animated Snake Border
*A flowing border animation where a vibrant multi-color gradient traces along the perimeter path.*

### HTML
```html
<div class="border-box border-effect-2">
    <div class="snake-border"></div>
    <span class="border-text">Snake Line</span>
</div>
```

### CSS
```css
.border-effect-2 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    overflow: hidden;
}
.border-effect-2 .snake-border {
    position: absolute;
    inset: 0;
    border-radius: 8px;
    padding: 2px;
    background: linear-gradient(90deg, #6366f1, #ec4899, #00f0ff, #6366f1);
    background-size: 300% 300%;
    -webkit-mask: 
       linear-gradient(#fff 0 0) content-box, 
       linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
            mask-composite: exclude;
    pointer-events: none;
}
.border-effect-2:hover .snake-border {
    animation: snake-flow 2s linear infinite;
}
@keyframes snake-flow {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #3: Marching Dots Border
*An SVG-driven custom dashed border that animates marching ants offset cycles during hover states.*

### HTML
```html
<div class="border-box border-effect-3">
    <svg class="svg-border" width="100%" height="100%">
        <rect x="0" y="0" width="100%" height="100%" rx="8" ry="8" />
    </svg>
    <span class="border-text">Marching Dots</span>
</div>
```

### CSS
```css
.border-effect-3 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}
.border-effect-3 .svg-border {
    position: absolute;
    inset: 0;
    fill: none;
    stroke: rgba(255, 255, 255, 0.15);
    stroke-width: 2;
    stroke-dasharray: 6 4;
    border-radius: 8px;
    pointer-events: none;
}
.border-effect-3:hover .svg-border {
    stroke: #00f0ff;
    animation: march 0.4s linear infinite;
}
@keyframes march {
    to { stroke-dashoffset: -10; }
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #4: Corner Bracket Focus Frame
*A minimal focus frame outline composed of four corners that compress tightly on hover, utilizing elastic transitions.*

### HTML
```html
<div class="border-box border-effect-4">
    <div class="bracket top-left"></div>
    <div class="bracket top-right"></div>
    <div class="bracket bottom-left"></div>
    <div class="bracket bottom-right"></div>
    <span class="border-text">Focus Frame</span>
</div>
```

### CSS
```css
.border-effect-4 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 1px solid rgba(255, 255, 255, 0.05);
}
.border-effect-4 .bracket {
    position: absolute;
    width: 12px;
    height: 12px;
    border: 2px solid transparent;
    transition: all 0.3s cubic-bezier(0.25, 1, 0.5, 1);
}
.border-effect-4 .top-left {
    top: 6px;
    left: 6px;
    border-top-color: rgba(255,255,255,0.2);
    border-left-color: rgba(255,255,255,0.2);
}
.border-effect-4 .top-right {
    top: 6px;
    right: 6px;
    border-top-color: rgba(255,255,255,0.2);
    border-right-color: rgba(255,255,255,0.2);
}
.border-effect-4 .bottom-left {
    bottom: 6px;
    left: 6px;
    border-bottom-color: rgba(255,255,255,0.2);
    border-left-color: rgba(255,255,255,0.2);
}
.border-effect-4 .bottom-right {
    bottom: 6px;
    right: 6px;
    border-bottom-color: rgba(255,255,255,0.2);
    border-right-color: rgba(255,255,255,0.2);
}
.border-effect-4:hover .bracket {
    width: 20px;
    height: 20px;
    border-color: #ec4899;
}
.border-effect-4:hover .top-left { top: -2px; left: -2px; }
.border-effect-4:hover .top-right { top: -2px; right: -2px; }
.border-effect-4:hover .bottom-left { bottom: -2px; left: -2px; }
.border-effect-4:hover .bottom-right { bottom: -2px; right: -2px; }
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #5: Conic Shimmer Glow
*A premium border styling where a sweeping conic-gradient rotating backplate bleeds vibrant neon shimmer outlines.*

### HTML
```html
<div class="border-box border-effect-5">
    <div class="conic-glow"></div>
    <div class="conic-inner">
        <span class="border-text">Conic Shimmer</span>
    </div>
</div>
```

### CSS
```css
.border-effect-5 {
    position: relative;
    width: 140px;
    height: 80px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    overflow: hidden;
    background: transparent;
    padding: 2px;
}
.border-effect-5 .conic-glow {
    position: absolute;
    width: 200%;
    height: 200%;
    background: conic-gradient(from 90deg, #ec4899 0%, #6366f1 50%, #00f0ff 100%);
    animation: rotate-conic 4s linear infinite;
    z-index: 1;
}
.border-effect-5 .conic-inner {
    position: relative;
    width: 100%;
    height: 100%;
    background: #0b0f19;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2;
    transition: background 0.3s;
}
.border-effect-5:hover .conic-inner {
    background: #111524;
}
@keyframes rotate-conic {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #6: Double Slide Border
*An interactive minimal design using two opposing corner border outlines that sweep in on hover to frame the component.*

### HTML
```html
<div class="border-box border-effect-6">
    <span class="border-text">Double Slide</span>
</div>
```

### CSS
```css
.border-effect-6 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: background 0.3s;
}
.border-effect-6::before,
.border-effect-6::after {
    content: '';
    position: absolute;
    width: 0;
    height: 0;
    border: 2px solid transparent;
    border-radius: 8px;
    transition: all 0.35s ease;
}
.border-effect-6::before {
    top: 0;
    left: 0;
}
.border-effect-6::after {
    bottom: 0;
    right: 0;
}
.border-effect-6:hover::before {
    width: 100%;
    height: 100%;
    border-top-color: #6366f1;
    border-right-color: #6366f1;
}
.border-effect-6:hover::after {
    width: 100%;
    height: 100%;
    border-bottom-color: #6366f1;
    border-left-color: #6366f1;
}
.border-effect-6:hover {
    background: #111524;
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #7: Cyberpunk Glitch Border
*A glowing cyberpunk-themed border that dynamic-glitches through neon color cycles and offset drop shadows on hover.*

### HTML
```html
<div class="border-box border-effect-7">
    <span class="border-text">Cyber Glitch</span>
</div>
```

### CSS
```css
.border-effect-7 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 2px solid #00f0ff;
    box-shadow: 0 0 10px rgba(0, 240, 255, 0.2);
    transition: all 0.2s ease;
}
.border-effect-7:hover {
    animation: glitch-border 0.8s infinite;
    background: #0d1222;
}
.border-effect-7:hover .border-text {
    color: #fff;
    text-shadow: 0 0 2px rgba(255, 255, 255, 0.5);
}
@keyframes glitch-border {
    0% {
        border-color: #00f0ff;
        box-shadow: -2px -2px 10px #ff007f, 2px 2px 10px #00f0ff;
    }
    20% {
        border-color: #ff007f;
        box-shadow: 2px -2px 12px #00f0ff, -2px 2px 12px #ff007f;
    }
    40% {
        border-color: #00f0ff;
        box-shadow: -1px 2px 8px #ff007f, 2px -1px 8px #00f0ff;
    }
    60% {
        border-color: #9d4edd;
        box-shadow: 2px 2px 14px #9d4edd, -2px -2px 14px #00f0ff;
    }
    80% {
        border-color: #ff007f;
        box-shadow: -2px 1px 10px #00f0ff, 2px -2px 10px #ff007f;
    }
    100% {
        border-color: #00f0ff;
        box-shadow: -2px -2px 10px #ff007f, 2px 2px 10px #00f0ff;
    }
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #8: Gradient Draw Lines
*An interactive line drawing border where progressive neon strokes animate sequentially around the perimeter edges on hover.*

### HTML
```html
<div class="border-box border-effect-8">
    <span class="line-1"></span>
    <span class="line-2"></span>
    <span class="line-3"></span>
    <span class="line-4"></span>
    <span class="border-text">Line Draw</span>
</div>
```

### CSS
```css
.border-effect-8 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.05);
}
.border-effect-8 span[class^="line-"] {
    position: absolute;
    background: linear-gradient(90deg, #6366f1, #00f0ff);
    transition: all 0.25s ease;
}
.border-effect-8 .line-1 {
    top: 0; left: 0;
    width: 0; height: 2px;
}
.border-effect-8 .line-2 {
    top: 0; right: 0;
    width: 2px; height: 0;
    background: linear-gradient(180deg, #6366f1, #00f0ff);
}
.border-effect-8 .line-3 {
    bottom: 0; right: 0;
    width: 0; height: 2px;
    background: linear-gradient(270deg, #6366f1, #00f0ff);
}
.border-effect-8 .line-4 {
    bottom: 0; left: 0;
    width: 2px; height: 0;
    background: linear-gradient(360deg, #6366f1, #00f0ff);
}
.border-effect-8:hover .line-1 {
    width: 100%;
}
.border-effect-8:hover .line-2 {
    height: 100%;
    transition-delay: 0.08s;
}
.border-effect-8:hover .line-3 {
    width: 100%;
    transition-delay: 0.16s;
}
.border-effect-8:hover .line-4 {
    height: 100%;
    transition-delay: 0.24s;
}
.border-effect-8:hover .border-text {
    color: #fff;
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #9: Cosmic Aurora Pulse
*A volumetric layered aura that pulses softly behind the element container to resemble a colorful deep space nebula.*

### HTML
```html
<div class="border-box border-effect-9">
    <div class="aurora-glow"></div>
    <span class="border-text">Cosmic Aura</span>
</div>
```

### CSS
```css
.border-effect-9 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0a0e17;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 1px solid rgba(255, 255, 255, 0.1);
    transition: all 0.3s ease;
}
.border-effect-9 .aurora-glow {
    position: absolute;
    inset: -2px;
    border-radius: 10px;
    background: linear-gradient(45deg, #ff007f, #7f00ff, #00f0ff, #ff007f);
    background-size: 400% 400%;
    z-index: -1;
    opacity: 0;
    filter: blur(12px);
    transition: opacity 0.4s ease;
}
.border-effect-9:hover {
    border-color: transparent;
    transform: translateY(-2px);
}
.border-effect-9:hover .aurora-glow {
    opacity: 0.85;
    animation: aurora-move 8s ease infinite;
}
.border-effect-9:hover .border-text {
    color: #fff;
}
@keyframes aurora-move {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
.border-text {
    font-size: 0.9rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 0.5px;
}
```

---

## Effect #10: Glassmorphism Frost Highlight
*A premium glassmorphic border with a sliding gloss highlight reflection that sweeps across the surface on hover.*

### HTML
```html
<div class="border-box border-effect-10">
    <div class="glass-reflection"></div>
    <span class="border-text">Glass Frost</span>
</div>
```

### CSS
```css
.border-effect-10 {
    position: relative;
    width: 140px;
    height: 80px;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    backdrop-filter: blur(12px);
    overflow: hidden;
    transition: all 0.3s ease;
}
.border-effect-10 .glass-reflection {
    position: absolute;
    top: 0;
    left: -150%;
    width: 50%;
    height: 100%;
    background: linear-gradient(
        90deg,
        transparent,
        rgba(255, 255, 255, 0.25),
        transparent
    );
    transform: skewX(-25deg);
    transition: 0.75s;
}
.border-effect-10:hover {
    border-color: rgba(255, 255, 255, 0.25);
    background: rgba(255, 255, 255, 0.06);
    box-shadow: 0 8px 32px rgba(255, 255, 255, 0.05);
}
.border-effect-10:hover .glass-reflection {
    left: 150%;
}
.border-effect-10:hover .border-text {
    color: #fff;
}
```

---

## Effect #11: Pulse Wave Echo
*A pulsing neon outline that generates expanding soundwave-like rings around the card boundaries on hover.*

### HTML
```html
<div class="border-box border-effect-11">
    <div class="pulse-ring ring-1"></div>
    <div class="pulse-ring ring-2"></div>
    <span class="border-text">Pulse Wave</span>
</div>
```

### CSS
```css
.border-effect-11 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 1px solid #10b981;
    transition: all 0.3s ease;
}
.border-effect-11 .pulse-ring {
    position: absolute;
    inset: -1px;
    border: 1px solid #10b981;
    border-radius: 8px;
    opacity: 0;
    pointer-events: none;
}
.border-effect-11:hover {
    box-shadow: 0 0 10px rgba(16, 185, 129, 0.4);
}
.border-effect-11:hover .ring-1 {
    animation: ring-pulse-wave 1.5s cubic-bezier(0.24, 0, 0.38, 1) infinite;
}
.border-effect-11:hover .ring-2 {
    animation: ring-pulse-wave 1.5s cubic-bezier(0.24, 0, 0.38, 1) infinite;
    animation-delay: 0.75s;
}
.border-effect-11:hover .border-text {
    color: #fff;
}
@keyframes ring-pulse-wave {
    0% {
        transform: scale(1);
        opacity: 0.8;
    }
    100% {
        transform: scale(1.2, 1.35);
        opacity: 0;
    }
}
```



---

## Effect #12: Electric Plasma Flow
*An overlay of opposing multi-colored gradients which rotate in reverse to form a fluid plasma outline.*

### HTML
```html
<div class="border-box border-effect-12">
    <div class="plasma-layer layer-1"></div>
    <div class="plasma-layer layer-2"></div>
    <span class="border-text">Plasma Flow</span>
</div>
```

### CSS
```css
.border-effect-12 {
    position: relative;
    width: 140px;
    height: 80px;
    background: transparent;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    overflow: hidden;
}
.border-effect-12 .plasma-layer {
    position: absolute;
    inset: 0;
    mix-blend-mode: screen;
    opacity: 0.15;
    transition: opacity 0.3s;
}
.border-effect-12 .layer-1 {
    background: radial-gradient(circle at 0% 0%, #ff007f, transparent 70%),
                radial-gradient(circle at 100% 100%, #7f00ff, transparent 70%);
}
.border-effect-12 .layer-2 {
    background: radial-gradient(circle at 100% 0%, #00f0ff, transparent 70%),
                radial-gradient(circle at 0% 100%, #ffaa00, transparent 70%);
}
.border-effect-12::after {
    content: '';
    position: absolute;
    inset: 1px;
    background: #0b0f19;
    border-radius: 7px;
    z-index: 1;
    transition: background 0.3s ease;
}
.border-effect-12:hover .plasma-layer {
    opacity: 0.8;
}
.border-effect-12:hover .layer-1 {
    animation: spin-plasma-1 4s linear infinite;
}
.border-effect-12:hover .layer-2 {
    animation: spin-plasma-2 4s linear infinite;
}
.border-effect-12:hover::after {
    background: #111524;
}
.border-effect-12:hover .border-text {
    color: #fff;
}
@keyframes spin-plasma-1 {
    0% { transform: rotate(0deg) scale(1); }
    50% { transform: rotate(180deg) scale(1.2); }
    100% { transform: rotate(360deg) scale(1); }
}
@keyframes spin-plasma-2 {
    0% { transform: rotate(360deg) scale(1.2); }
    50% { transform: rotate(180deg) scale(1); }
    100% { transform: rotate(0deg) scale(1.2); }
}
```


```

---

## Effect #13: Neon Ripple Flow
*Glowing neon indicators that slide and ripple across top/bottom and left/right border walls alternatively on hover.*

### HTML
```html
<div class="border-box border-effect-13">
    <span class="pulse-bar top"></span>
    <span class="pulse-bar right"></span>
    <span class="pulse-bar bottom"></span>
    <span class="pulse-bar left"></span>
    <span class="border-text">Ripple Flow</span>
</div>
```

### CSS
```css
.border-effect-13 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 1px solid rgba(255, 255, 255, 0.05);
}
.border-effect-13 .pulse-bar {
    position: absolute;
    background: #6366f1;
    opacity: 0;
    transition: all 0.3s ease;
}
.border-effect-13 .pulse-bar.top {
    top: -1px; left: 0; width: 100%; height: 2px;
    transform: scaleX(0);
}
.border-effect-13 .pulse-bar.right {
    top: 0; right: -1px; width: 2px; height: 100%;
    transform: scaleY(0);
}
.border-effect-13 .pulse-bar.bottom {
    bottom: -1px; left: 0; width: 100%; height: 2px;
    transform: scaleX(0);
}
.border-effect-13 .pulse-bar.left {
    top: 0; left: -1px; width: 2px; height: 100%;
    transform: scaleY(0);
}
.border-effect-13:hover {
    border-color: rgba(255, 255, 255, 0.1);
}
.border-effect-13:hover .pulse-bar {
    opacity: 1;
}
.border-effect-13:hover .pulse-bar.top,
.border-effect-13:hover .pulse-bar.bottom {
    transform: scaleX(1);
    animation: chroma-flash 1.2s infinite;
}
.border-effect-13:hover .pulse-bar.right,
.border-effect-13:hover .pulse-bar.left {
    transform: scaleY(1);
    animation: chroma-flash 1.2s infinite 0.6s;
}
.border-effect-13:hover .border-text {
    color: #fff;
}
@keyframes chroma-flash {
    0%, 100% { background: #6366f1; box-shadow: 0 0 4px #6366f1; }
    50% { background: #ec4899; box-shadow: 0 0 10px #ec4899; }
}
```



---

## Effect #14: Shimmering Starlight
*A gold-bordered showcase where high-frequency starlight pulses flicker shimmer highlights dynamically on hover.*

### HTML
```html
<div class="border-box border-effect-14">
    <div class="star-sparkle"></div>
    <span class="border-text">Starlight</span>
</div>
```

### CSS
```css
.border-effect-14 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0b0f19;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 1px solid rgba(255, 255, 255, 0.08);
}
.border-effect-14 .star-sparkle {
    position: absolute;
    inset: -1px;
    border-radius: 8px;
    background: transparent;
    pointer-events: none;
    box-shadow: inset 0 0 0 1px transparent;
    transition: all 0.3s;
}
.border-effect-14:hover {
    border-color: #ffd700;
    box-shadow: 0 0 10px rgba(255, 215, 0, 0.2);
}
.border-effect-14:hover .star-sparkle {
    animation: sparkle-flicker 1s infinite alternate;
}
.border-effect-14:hover .border-text {
    color: #ffd700;
    text-shadow: 0 0 8px rgba(255, 215, 0, 0.6);
}
@keyframes sparkle-flicker {
    0% {
        box-shadow: inset 0 0 5px #ffd700, 0 0 4px #ffd700;
        opacity: 0.5;
    }
    100% {
        box-shadow: inset 0 0 15px #ffd700, 0 0 12px #ffd700;
        opacity: 1;
    }
}
```



---

## Effect #15: Retro Wave Grid Sweep
*An outrun grid perspective mesh sweeping downwards to resemble retro synthwave aesthetics.*

### HTML
```html
<div class="border-box border-effect-15">
    <div class="retrowave-grid"></div>
    <span class="border-text">Retro Wave</span>
</div>
```

### CSS
```css
.border-effect-15 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #11001c;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 2px solid #ff007f;
    box-shadow: 0 0 10px rgba(255, 0, 127, 0.3);
    overflow: hidden;
}
.border-effect-15 .retrowave-grid {
    position: absolute;
    inset: 0;
    background: 
        linear-gradient(rgba(255,0,127,0.15) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,0,127,0.15) 1px, transparent 1px);
    background-size: 10px 10px;
    background-position: center;
    transform: perspective(60px) rotateX(25deg);
    transform-origin: bottom center;
    transition: all 0.3s ease;
}
.border-effect-15:hover .retrowave-grid {
    animation: grid-slide-down 1.5s linear infinite;
    background-image: 
        linear-gradient(rgba(0,240,255,0.3) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,240,255,0.3) 1px, transparent 1px);
}
.border-effect-15:hover {
    border-color: #00f0ff;
    box-shadow: 0 0 18px rgba(0, 240, 255, 0.6);
}
.border-effect-15 .border-text {
    color: #ff007f;
    text-shadow: 0 0 4px #ff007f;
}
.border-effect-15:hover .border-text {
    color: #00f0ff;
    text-shadow: 0 0 6px #00f0ff;
}
@keyframes grid-slide-down {
    0% { background-position-y: 0px; }
    100% { background-position-y: 20px; }
}
```



---

## Effect #16: Volumetric Shadow Eclipse
*An internal volumetric shadow coupled with an outer white coronal eclipse flare on hover.*

### HTML
```html
<div class="border-box border-effect-16">
    <span class="border-text">Eclipse Flare</span>
</div>
```

### CSS
```css
.border-effect-16 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #000;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    border: 1px solid rgba(255, 255, 255, 0.2);
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.9);
    transition: all 0.4s ease;
}
.border-effect-16:hover {
    border-color: #fff;
    box-shadow: inset 0 0 15px rgba(0, 0, 0, 1), 0 0 20px #fff;
    background: #020202;
}
.border-effect-16:hover .border-text {
    color: #fff;
    text-shadow: 0 0 4px rgba(255, 255, 255, 0.6);
}
```

---

## Effect #17: Mouse Spotlight Glow
*An interactive card layout featuring dynamic radial glow borders and subtle inner spotlight gradients tracking mouse movements.*

### HTML
```html
<div class="border-box border-effect-17" id="spotlight-card-17">
    <div class="glow-inner-17"></div>
    <span class="border-text">Spotlight Glow</span>
</div>
```

### CSS
```css
.border-effect-17 {
    position: relative;
    width: 140px;
    height: 80px;
    background: #0c101b;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.08);
}

.border-effect-17::before {
    content: '';
    position: absolute;
    inset: -1px;
    border-radius: inherit;
    padding: 1px;
    background: radial-gradient(
        75px circle at var(--x, 0px) var(--y, 0px),
        rgba(99, 102, 241, 1),
        transparent 100%
    );
    -webkit-mask: 
       linear-gradient(#fff 0 0) content-box, 
       linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
    pointer-events: none;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.border-effect-17:hover::before {
    opacity: 1;
}

.border-effect-17 .glow-inner-17 {
    position: absolute;
    inset: 0;
    background: radial-gradient(
        100px circle at var(--x, 0px) var(--y, 0px),
        rgba(99, 102, 241, 0.15),
        transparent 100%
    );
    opacity: 0;
    transition: opacity 0.3s ease;
    pointer-events: none;
}

.border-effect-17:hover .glow-inner-17 {
    opacity: 1;
}

.border-effect-17 .border-text {
    font-size: 0.85rem;
    font-weight: 600;
    color: #cbd5e1;
    letter-spacing: 0.5px;
    z-index: 10;
}

.border-effect-17:hover .border-text {
    color: #fff;
}
```

### JavaScript
```javascript
const card = document.getElementById('spotlight-card-17');
if (card) {
    card.addEventListener('mousemove', (e) => {
        const rect = card.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        card.style.setProperty('--x', `${x}px`);
        card.style.setProperty('--y', `${y}px`);
    });
}
```

---

## Effect #18: Interactive Glow Card (React)
*Interactive spotlight border and ambient glowing card React implementation that responds to document-wide pointer movements.*

### React Component
```tsx
import React, { useEffect, useRef, ReactNode } from 'react';

interface GlowCardProps {
  children: ReactNode;
  className?: string;
  glowColor?: 'blue' | 'purple' | 'green' | 'red' | 'orange';
  size?: 'sm' | 'md' | 'lg';
  width?: string | number;
  height?: string | number;
  customSize?: boolean; // When true, ignores size prop and uses width/height or className
}

const glowColorMap = {
  blue: { base: 220, spread: 200 },
  purple: { base: 280, spread: 300 },
  green: { base: 120, spread: 200 },
  red: { base: 0, spread: 200 },
  orange: { base: 30, spread: 200 }
};

const sizeMap = {
  sm: 'w-48 h-64',
  md: 'w-64 h-80',
  lg: 'w-80 h-96'
};

const GlowCard: React.FC<GlowCardProps> = ({ 
  children, 
  className = '', 
  glowColor = 'blue',
  size = 'md',
  width,
  height,
  customSize = false
}) => {
  const cardRef = useRef<HTMLDivElement>(null);
  const innerRef = useRef<HTMLDivElement>(null);

  useEffect(() => {
    const syncPointer = (e: PointerEvent) => {
      const { clientX: x, clientY: y } = e;
      
      if (cardRef.current) {
        cardRef.current.style.setProperty('--x', x.toFixed(2));
        cardRef.current.style.setProperty('--xp', (x / window.innerWidth).toFixed(2));
        cardRef.current.style.setProperty('--y', y.toFixed(2));
        cardRef.current.style.setProperty('--yp', (y / window.innerHeight).toFixed(2));
      }
    };

    document.addEventListener('pointermove', syncPointer);
    return () => document.removeEventListener('pointermove', syncPointer);
  }, []);

  const { base, spread } = glowColorMap[glowColor];

  // Determine sizing
  const getSizeClasses = () => {
    if (customSize) {
      return ''; // Let className or inline styles handle sizing
    }
    return sizeMap[size];
  };

  const getInlineStyles = () => {
    const baseStyles = {
      '--base': base,
      '--spread': spread,
      '--radius': '14',
      '--border': '3',
      '--backdrop': 'hsl(0 0% 60% / 0.12)',
      '--backup-border': 'var(--backdrop)',
      '--size': '200',
      '--outer': '1',
      '--border-size': 'calc(var(--border, 2) * 1px)',
      '--spotlight-size': 'calc(var(--size, 150) * 1px)',
      '--hue': 'calc(var(--base) + (var(--xp, 0) * var(--spread, 0)))',
      backgroundImage: `radial-gradient(
        var(--spotlight-size) var(--spotlight-size) at
        calc(var(--x, 0) * 1px)
        calc(var(--y, 0) * 1px),
        hsl(var(--hue, 210) calc(var(--saturation, 100) * 1%) calc(var(--lightness, 70) * 1%) / var(--bg-spot-opacity, 0.1)), transparent
      )`,
      backgroundColor: 'var(--backdrop, transparent)',
      backgroundSize: 'calc(100% + (2 * var(--border-size))) calc(100% + (2 * var(--border-size)))',
      backgroundPosition: '50% 50%',
      backgroundAttachment: 'fixed',
      border: 'var(--border-size) solid var(--backup-border)',
      position: 'relative' as const,
      touchAction: 'none' as const,
    };

    // Add width and height if provided
    if (width !== undefined) {
      baseStyles.width = typeof width === 'number' ? `${width}px` : width;
    }
    if (height !== undefined) {
      baseStyles.height = typeof height === 'number' ? `${height}px` : height;
    }

    return baseStyles;
  };

  const beforeAfterStyles = `
    [data-glow]::before,
    [data-glow]::after {
      pointer-events: none;
      content: "";
      position: absolute;
      inset: calc(var(--border-size) * -1);
      border: var(--border-size) solid transparent;
      border-radius: calc(var(--radius) * 1px);
      background-attachment: fixed;
      background-size: calc(100% + (2 * var(--border-size))) calc(100% + (2 * var(--border-size)));
      background-repeat: no-repeat;
      background-position: 50% 50%;
      mask: linear-gradient(transparent, transparent), linear-gradient(white, white);
      mask-clip: padding-box, border-box;
      mask-composite: intersect;
    }
    
    [data-glow]::before {
      background-image: radial-gradient(
        calc(var(--spotlight-size) * 0.75) calc(var(--spotlight-size) * 0.75) at
        calc(var(--x, 0) * 1px)
        calc(var(--y, 0) * 1px),
        hsl(var(--hue, 210) calc(var(--saturation, 100) * 1%) calc(var(--lightness, 50) * 1%) / var(--border-spot-opacity, 1)), transparent 100%
      );
      filter: brightness(2);
    }
    
    [data-glow]::after {
      background-image: radial-gradient(
        calc(var(--spotlight-size) * 0.5) calc(var(--spotlight-size) * 0.5) at
        calc(var(--x, 0) * 1px)
        calc(var(--y, 0) * 1px),
        hsl(0 100% 100% / var(--border-light-opacity, 1)), transparent 100%
      );
    }
    
    [data-glow] [data-glow] {
      position: absolute;
      inset: 0;
      will-change: filter;
      opacity: var(--outer, 1);
      border-radius: calc(var(--radius) * 1px);
      border-width: calc(var(--border-size) * 20);
      filter: blur(calc(var(--border-size) * 10));
      background: none;
      pointer-events: none;
      border: none;
    }
    
    [data-glow] > [data-glow]::before {
      inset: -10px;
      border-width: 10px;
    }
  `;

  return (
    <>
      <style dangerouslySetInnerHTML={{ __html: beforeAfterStyles }} />
      <div
        ref={cardRef}
        data-glow
        style={getInlineStyles()}
        className={`
          \${getSizeClasses()}
          \${!customSize ? 'aspect-[3/4]' : ''}
          rounded-2xl 
          relative 
          grid 
          grid-rows-[1fr_auto] 
          shadow-[0_1rem_2rem_-1rem_black] 
          p-4 
          gap-4 
          backdrop-blur-[5px]
          \${className}
        `}
      >
        <div ref={innerRef} data-glow></div>
        {children}
      </div>
    </>
  );
};

export { GlowCard }
```

### CSS Styles
```css
[data-glow] {
  --border-size: calc(var(--border, 2) * 1px);
  --spotlight-size: calc(var(--size, 150) * 1px);
  --hue: calc(var(--base) + (var(--xp, 0) * var(--spread, 0)));
  --backdrop: hsl(0 0% 60% / 0.12);
  --backup-border: var(--backdrop);
  
  background-image: radial-gradient(
    var(--spotlight-size) var(--spotlight-size) at
    calc(var(--x, 0) * 1px)
    calc(var(--y, 0) * 1px),
    hsl(var(--hue, 210) calc(var(--saturation, 100) * 1%) calc(var(--lightness, 70) * 1%) / var(--bg-spot-opacity, 0.1)), transparent
  );
  background-color: var(--backdrop);
  background-size: calc(100% + (2 * var(--border-size))) calc(100% + (2 * var(--border-size)));
  background-position: 50% 50%;
  background-attachment: fixed;
  border: var(--border-size) solid var(--backup-border);
  position: relative;
  touch-action: none;
}

[data-glow]::before,
[data-glow]::after {
  pointer-events: none;
  content: "";
  position: absolute;
  inset: calc(var(--border-size) * -1);
  border: var(--border-size) solid transparent;
  border-radius: calc(var(--radius, 14) * 1px);
  background-attachment: fixed;
  background-size: calc(100% + (2 * var(--border-size))) calc(100% + (2 * var(--border-size)));
  background-repeat: no-repeat;
  background-position: 50% 50%;
  mask: linear-gradient(transparent, transparent), linear-gradient(white, white);
  mask-clip: padding-box, border-box;
  mask-composite: intersect;
  /* Vendor prefixed equivalents for optimal compatibility */
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
}

[data-glow]::before {
  background-image: radial-gradient(
    calc(var(--spotlight-size) * 0.75) calc(var(--spotlight-size) * 0.75) at
    calc(var(--x, 0) * 1px)
    calc(var(--y, 0) * 1px),
    hsl(var(--hue, 210) calc(var(--saturation, 100) * 1%) calc(var(--lightness, 50) * 1%) / var(--border-spot-opacity, 1)), transparent 100%
  );
  filter: brightness(2);
}

[data-glow]::after {
  background-image: radial-gradient(
    calc(var(--spotlight-size) * 0.5) calc(var(--spotlight-size) * 0.5) at
    calc(var(--x, 0) * 1px)
    calc(var(--y, 0) * 1px),
    hsl(0 100% 100% / var(--border-light-opacity, 1)), transparent 100%
  );
}

[data-glow] [data-glow] {
  position: absolute;
  inset: 0;
  will-change: filter;
  opacity: var(--outer, 1);
  border-radius: calc(var(--radius, 14) * 1px);
  border-width: calc(var(--border-size) * 20);
  filter: blur(calc(var(--border-size) * 10));
  background: none;
  pointer-events: none;
  border: none;
}

[data-glow] > [data-glow]::before {
  inset: -10px;
  border-width: 10px;
}
```

### JavaScript
```javascript
// Pointer sync for Glow Cards
const syncPointer = ({ x, y }) => {
  document.documentElement.style.setProperty('--x', x.toFixed(2));
  document.documentElement.style.setProperty('--xp', (x / window.innerWidth).toFixed(2));
  document.documentElement.style.setProperty('--y', y.toFixed(2));
  document.documentElement.style.setProperty('--yp', (y / window.innerHeight).toFixed(2));
};
document.body.addEventListener('pointermove', syncPointer);
```

---

## Effect #19: Sparkles Core (React)
*Animated particles background border component powered by tsparticles and Framer Motion React implementation.*

### React Component
```tsx
"use client";
import React, { useId, useMemo } from "react";
import { useEffect, useState } from "react";
import Particles, { initParticlesEngine } from "@tsparticles/react";
import type { Container, SingleOrMultiple } from "@tsparticles/engine";
import { loadSlim } from "@tsparticles/slim";
import { cn } from "@/lib/utils";
import { motion, useAnimation } from "framer-motion";

type ParticlesProps = {
  id?: string;
  className?: string;
  background?: string;
  particleSize?: number;
  minSize?: number;
  maxSize?: number;
  speed?: number;
  particleColor?: string;
  particleDensity?: number;
};
export const SparklesCore = (props: ParticlesProps) => {
  const {
    id,
    className,
    background,
    minSize,
    maxSize,
    speed,
    particleColor,
    particleDensity,
  } = props;
  const [init, setInit] = useState(false);
  useEffect(() => {
    initParticlesEngine(async (engine) => {
      await loadSlim(engine);
    }).then(() => {
      setInit(true);
    });
  }, []);
  const controls = useAnimation();

  const particlesLoaded = async (container?: Container) => {
    if (container) {
      controls.start({
        opacity: 1,
        transition: {
          duration: 1,
        },
      });
    }
  };

  const generatedId = useId();
  return (
    <motion.div animate={controls} className={cn("opacity-0", className)}>
      {init && (
        <Particles
          id={id || generatedId}
          className={cn("h-full w-full")}
          particlesLoaded={particlesLoaded}
          options={{
            background: {
              color: {
                value: background || "#0d47a1",
              },
            },
            fullScreen: {
              enable: false,
              zIndex: 1,
            },

            fpsLimit: 120,
            interactivity: {
              events: {
                onClick: {
                  enable: true,
                  mode: "push",
                },
                onHover: {
                  enable: false,
                  mode: "repulse",
                },
                resize: true as any,
              },
              modes: {
                push: {
                  quantity: 4,
                },
                repulse: {
                  distance: 200,
                  duration: 0.4,
                },
              },
            },
            particles: {
              bounce: {
                horizontal: {
                  value: 1,
                },
                vertical: {
                  value: 1,
                },
              },
              collisions: {
                absorb: {
                  speed: 2,
                },
                bounce: {
                  horizontal: {
                    value: 1,
                  },
                  vertical: {
                    value: 1,
                  },
                },
                enable: false,
                maxSpeed: 50,
                mode: "bounce",
                overlap: {
                  enable: true,
                  retries: 0,
                },
              },
              color: {
                value: particleColor || "#ffffff",
                animation: {
                  h: {
                    count: 0,
                    enable: false,
                    speed: 1,
                    decay: 0,
                    delay: 0,
                    sync: true,
                    offset: 0,
                  },
                  s: {
                    count: 0,
                    enable: false,
                    speed: 1,
                    decay: 0,
                    delay: 0,
                    sync: true,
                    offset: 0,
                  },
                  l: {
                    count: 0,
                    enable: false,
                    speed: 1,
                    decay: 0,
                    delay: 0,
                    sync: true,
                    offset: 0,
                  },
                },
              },
              effect: {
                close: true,
                fill: true,
                options: {},
                type: {} as SingleOrMultiple<string> | undefined,
              },
              groups: {},
              move: {
                angle: {
                  offset: 0,
                  value: 90,
                },
                attract: {
                  distance: 200,
                  enable: false,
                  rotate: {
                    x: 3000,
                    y: 3000,
                  },
                },
                center: {
                  x: 50,
                  y: 50,
                  mode: "percent",
                  radius: 0,
                },
                decay: 0,
                distance: {},
                direction: "none",
                drift: 0,
                enable: true,
                gravity: {
                  acceleration: 9.81,
                  enable: false,
                  inverse: false,
                  maxSpeed: 50,
                },
                path: {
                  clamp: true,
                  delay: {
                    value: 0,
                  },
                  enable: false,
                  options: {},
                },
                outModes: {
                  default: "out",
                },
                random: false,
                size: false,
                speed: {
                  min: 0.1,
                  max: 1,
                },
                spin: {
                  acceleration: 0,
                  enable: false,
                },
                straight: false,
                trail: {
                  enable: false,
                  length: 10,
                  fill: {},
                },
                vibrate: false,
                warp: false,
              },
              number: {
                density: {
                  enable: true,
                  width: 400,
                  height: 400,
                },
                limit: {
                  mode: "delete",
                  value: 0,
                },
                value: particleDensity || 120,
              },
              opacity: {
                value: {
                  min: 0.1,
                  max: 1,
                },
                animation: {
                  count: 0,
                  enable: true,
                  speed: speed || 4,
                  decay: 0,
                  delay: 0,
                  sync: false,
                  mode: "auto",
                  startValue: "random",
                  destroy: "none",
                },
              },
              reduceDuplicates: false,
              shadow: {
                blur: 0,
                color: {
                  value: "#000",
                },
                enable: false,
                offset: {
                  x: 0,
                  y: 0,
                },
              },
              shape: {
                close: true,
                fill: true,
                options: {},
                type: "circle",
              },
              size: {
                value: {
                  min: minSize || 1,
                  max: maxSize || 3,
                },
                animation: {
                  count: 0,
                  enable: false,
                  speed: 5,
                  decay: 0,
                  delay: 0,
                  sync: false,
                  mode: "auto",
                  startValue: "random",
                  destroy: "none",
                },
              },
              stroke: {
                width: 0,
              },
              zIndex: {
                value: 0,
                opacityRate: 1,
                sizeRate: 1,
                velocityRate: 1,
              },
              destroy: {
                bounds: {},
                mode: "none",
                split: {
                  count: 1,
                  factor: {
                    value: 3,
                  },
                  rate: {
                    value: {
                      min: 4,
                      max: 9,
                    },
                  },
                  sizeOffset: true,
                },
              },
              roll: {
                darken: {
                  enable: false,
                  value: 0,
                },
                enable: false,
                enlighten: {
                  enable: false,
                  value: 0,
                },
                mode: "vertical",
                speed: 25,
              },
              tilt: {
                value: 0,
                animation: {
                  enable: false,
                  speed: 0,
                  decay: 0,
                  sync: false,
                },
                direction: "clockwise",
                enable: false,
              },
              twinkle: {
                lines: {
                  enable: false,
                  frequency: 0.05,
                  opacity: 1,
                },
                particles: {
                  enable: false,
                  frequency: 0.05,
                  opacity: 1,
                },
              },
              wobble: {
                distance: 5,
                enable: false,
                speed: {
                  angle: 50,
                  move: 10,
                },
              },
              life: {
                count: 0,
                delay: {
                  value: 0,
                  sync: false,
                },
                duration: {
                  value: 0,
                  sync: false,
                },
              },
              rotate: {
                value: 0,
                animation: {
                  enable: false,
                  speed: 0,
                  decay: 0,
                  sync: false,
                },
                direction: "clockwise",
                path: false,
              },
              orbit: {
                animation: {
                  count: 0,
                  enable: false,
                  speed: 1,
                  decay: 0,
                  delay: 0,
                  sync: false,
                },
                enable: false,
                opacity: 1,
                rotation: {
                  value: 45,
                },
                width: 1,
              },
              links: {
                blink: false,
                color: {
                  value: "#fff",
                },
                consent: false,
                distance: 100,
                enable: false,
                frequency: 1,
                opacity: 1,
                shadow: {
                  blur: 5,
                  color: {
                    value: "#000",
                  },
                  enable: false,
                },
                triangles: {
                  enable: false,
                  frequency: 1,
                },
                width: 1,
                warp: false,
              },
              repulse: {
                value: 0,
                enabled: false,
                distance: 1,
                duration: 1,
                factor: 1,
                speed: 1,
              },
            },
            detectRetina: true,
          }}
        />
      )}
    </motion.div>
  );
};
```

.border-effect-19 {
    position: relative;
    width: 240px;
    height: 120px;
    background: #03000a;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.05);
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.4);
}

.border-effect-19 canvas {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 1;
    -webkit-mask-image: radial-gradient(circle, white 40%, transparent 80%);
    mask-image: radial-gradient(circle, white 40%, transparent 80%);
}

.border-effect-19 .sparkles-content-19 {
    z-index: 2;
    text-align: center;
    pointer-events: none;
}

.border-effect-19 .sparkles-title-19 {
    font-size: 1.1rem;
    font-weight: 800;
    color: #fff;
    letter-spacing: 4px;
    margin: 0;
    text-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
}

.border-effect-19 .sparkles-divider-19 {
    width: 80px;
    height: 1px;
    background: linear-gradient(90deg, transparent, #818cf8, transparent);
    margin: 6px auto 0;
    box-shadow: 0 0 8px #818cf8;
}
```

---

## Effect #20: CTA Section Glow (React)
*Ambient border glow component for CTA sections with fade-in scale animations.*

### React Component
```tsx
"use client"

import { Button } from "@/components/ui/button"
import { Badge } from "@/components/ui/badge"
import { cn } from "@/lib/utils"

interface CTAProps {
  badge?: {
    text: string
  }
  title: string
  description?: string
  action: {
    text: string
    href: string
    variant?: "default" | "glow"
  }
  withGlow?: boolean
  className?: string
}

export function CTASection({
  badge,
  title,
  description,
  action,
  withGlow = true,
  className,
}: CTAProps) {
  return (
    <section className={cn("overflow-hidden pt-0 md:pt-0", className)}>
      <div className="relative mx-auto flex max-w-container flex-col items-center gap-6 px-8 py-12 text-center sm:gap-8 md:py-24">
        {/* Badge */}
        {badge && (
          <Badge
            variant="outline"
            className="opacity-0 animate-fade-in-up delay-100"
          >
            <span className="text-muted-foreground">{badge.text}</span>
          </Badge>
        )}

        {/* Title */}
        <h2 className="text-3xl font-semibold sm:text-5xl opacity-0 animate-fade-in-up delay-200">
          {title}
        </h2>

        {/* Description */}
        {description && (
          <p className="text-muted-foreground opacity-0 animate-fade-in-up delay-300">
            {description}
          </p>
        )}

        {/* Action Button */}
        <Button
          variant={action.variant || "default"}
          size="lg"
          className="opacity-0 animate-fade-in-up delay-500"
          asChild
        >
          <a href={action.href}>{action.text}</a>
        </Button>

        {/* Glow Effect */}
        {withGlow && (
          <div className="fade-top-lg pointer-events-none absolute inset-0 rounded-2xl shadow-glow opacity-0 animate-scale-in delay-700" />
        )}
      </div>
    </section>
  )
}
```

### CSS Styles
```css
.border-effect-20 {
    position: relative;
    width: 240px;
    height: 140px;
    background: #09090b;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.08);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
    padding: 12px;
}

.border-effect-20 .cta-glow-20 {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translate(-50%, -40%);
    width: 160px;
    height: 80px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.25) 0%, transparent 70%);
    pointer-events: none;
    filter: blur(10px);
    z-index: 1;
    transition: transform 0.5s ease;
}

.border-effect-20:hover .cta-glow-20 {
    transform: translate(-50%, -20%) scale(1.2);
    background: radial-gradient(circle, rgba(99, 102, 241, 0.4) 0%, transparent 70%);
}

.border-effect-20 .cta-content-20 {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
    text-align: center;
    z-index: 2;
    pointer-events: none;
}

.border-effect-20 .cta-badge-20 {
    font-size: 0.55rem;
    color: #818cf8;
    background: rgba(129, 140, 248, 0.1);
    border: 1px solid rgba(129, 140, 248, 0.2);
    padding: 1px 6px;
    border-radius: 100px;
    font-weight: 500;
}

.border-effect-20 .cta-title-20 {
    font-size: 0.85rem;
    font-weight: 600;
    color: #fff;
    margin: 0;
}

.border-effect-20 .cta-desc-20 {
    font-size: 0.65rem;
    color: #a1a1aa;
    margin: 0 0 2px;
    max-width: 180px;
    line-height: 1.2;
}

.border-effect-20 .cta-button-20 {
    font-size: 0.65rem;
    color: #000;
    background: #fff;
    border: none;
    padding: 4px 10px;
    border-radius: 6px;
    font-weight: 600;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Extra Tailwind configuration for CTA Glow animation */
@keyframes scale-in {
  0% { transform: scale(0.95); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}
.animate-scale-in {
  animation: scale-in 0.5s ease-out forwards;
}
.shadow-glow {
  box-shadow: 0 0 50px 10px rgba(99, 102, 241, 0.15);
}
```

---

## Effect #21: CTA Section Glow v2 (React)
*A call-to-action (CTA) component featuring customizable badges, headers, and buttons, styled with a volumetric top glow backdrop.*

### React Component

#### `cta-section.tsx`
```tsx
"use client";

import { Button } from "@/components/ui/button"
import { Badge } from "@/components/ui/badge"
import { cn } from "@/lib/utils"

interface CTAProps {
  badge?: {
    text: string
  }
  title: string
  description?: string
  action: {
    text: string
    href: string
    variant?: "default" | "glow"
  }
  withGlow?: boolean
  className?: string
}

export function CTASection({
  badge,
  title,
  description,
  action,
  withGlow = true,
  className,
}: CTAProps) {
  return (
    <section className={cn("overflow-hidden pt-0 md:pt-0", className)}>
      <div className="relative mx-auto flex max-w-container flex-col items-center gap-6 px-8 py-12 text-center sm:gap-8 md:py-24">
        {/* Badge */}
        {badge && (
          <Badge
            variant="outline"
            className="opacity-0 animate-fade-in-up delay-100"
          >
            <span className="text-muted-foreground">{badge.text}</span>
          </Badge>
        )}

        {/* Title */}
        <h2 className="text-3xl font-semibold sm:text-5xl opacity-0 animate-fade-in-up delay-200">
          {title}
        </h2>

        {/* Description */}
        {description && (
          <p className="text-muted-foreground opacity-0 animate-fade-in-up delay-300">
            {description}
          </p>
        )}

        {/* Action Button */}
        <Button
          variant={action.variant || "default"}
          size="lg"
          className="opacity-0 animate-fade-in-up delay-500"
          asChild
        >
          <a href={action.href}>{action.text}</a>
        </Button>

        {/* Glow Effect */}
        {withGlow && (
          <div className="fade-top-lg pointer-events-none absolute inset-0 rounded-2xl shadow-glow opacity-0 animate-scale-in delay-700" />
        )}
      </div>
    </section>
  )
}
```

---

## Effect #22: Shine Border (React)
*An animated background border glow effect that cycles beautiful multi-color gradients around the container.*

### React Components

#### `shine-border-demo.tsx`
```tsx
"use client"

import { Button } from "@/components/ui/button"
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card"
import { Input } from "@/components/ui/input"
import { Label } from "@/components/ui/label"
import { ShineBorder } from "./shine-border"

export function ShineBorderDemo() {
  return (
    <Card className="relative w-full max-w-[350px] overflow-hidden">
      <ShineBorder shineColor={["#A07CFE", "#FE8FB5", "#FFBE7B"]} />
      <CardHeader>
        <CardTitle>Login</CardTitle>
        <CardDescription>
          Enter your credentials to access your account
        </CardDescription>
      </CardHeader>
      <CardContent>
        <form>
          <div className="grid gap-4">
            <div className="grid gap-2">
              <Label htmlFor="email">Email</Label>
              <Input id="email" type="email" placeholder="name@example.com" />
            </div>
            <div className="grid gap-2">
              <Label htmlFor="password">Password</Label>
              <Input id="password" type="password" />
            </div>
          </div>
        </form>
      </CardContent>
      <CardFooter>
        <Button className="w-full">Sign In</Button>
      </CardFooter>
    </Card>
  )
}
```

#### `shine-border.tsx`
```tsx
"use client"

import * as React from "react"
import { cn } from "@/lib/utils"

interface ShineBorderProps extends React.HTMLAttributes<HTMLDivElement> {
  /**
   * Width of the border in pixels
   * @default 1
   */
  borderWidth?: number
  /**
   * Duration of the animation in seconds
   * @default 14
   */
  duration?: number
  /**
   * Color of the border, can be a single color or an array of colors
   * @default "#000000"
   */
  shineColor?: string | string[]
}

/**
 * Shine Border
 *
 * An animated background border effect component with configurable properties.
 */
export function ShineBorder({
  borderWidth = 1,
  duration = 14,
  shineColor = "#000000",
  className,
  style,
  ...props
}: ShineBorderProps) {
  return (
    <div
      style={
        {
          "--border-width": `${borderWidth}px`,
          "--duration": `${duration}s`,
          backgroundImage: `radial-gradient(transparent,transparent, ${
            Array.isArray(shineColor) ? shineColor.join(",") : shineColor
          },transparent,transparent)`,
          backgroundSize: "300% 300%",
          mask: `linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0)`,
          WebkitMask: `linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0)`,
          WebkitMaskComposite: "xor",
          maskComposite: "exclude",
          padding: "var(--border-width)",
          ...style,
        } as React.CSSProperties
      }
      className={cn(
        "motion-safe:animate-shine pointer-events-none absolute inset-0 size-full rounded-[inherit] will-change-[background-position]",
        className
      )}
      {...props}
    />
  )
}
```






