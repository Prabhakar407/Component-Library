# Premium Custom Border Code Database

This file contains the complete, self-contained HTML and CSS code snippets for all **17 Premium Borders** featured in the interactive showcase. Each border is numbered to match the UI labels in the application.

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
