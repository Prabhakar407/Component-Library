# Premium Custom Button Code Database

This file contains the complete, self-contained HTML and CSS code snippets for all **11 Premium Buttons** featured in the interactive showcase. Each button is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Button #1: Neon Glowing Border](#button-1-neon-glowing-border)
2. [Button #2: Glassmorphism Reflector](#button-2-glassmorphism-reflector)
3. [Button #3: Perimeter Border Tracer](#button-3-perimeter-border-tracer)
4. [Button #4: Liquid Blob Waves](#button-4-liquid-blob-waves)
5. [Button #5: Dynamic Gradient Mesh](#button-5-dynamic-gradient-mesh)
6. [Button #6: Magnetic Aura Expander](#button-6-magnetic-aura-expander)
7. [Button #7: Corner Bracket Draw](#button-7-corner-bracket-draw)
8. [Button #8: Shimmer Rotating Border](#button-8-shimmer-rotating-border)
9. [Button #9: Cosmic Portal Launch](#button-9-cosmic-portal-launch)
10. [Button #10: Slide Arrow Button](#button-10-slide-arrow-button)
11. [Button #11: Shimmer Button](#button-11-shimmer-button)

---

## Button #1: Neon Glowing Border
*Dark mode neon glow animation with an expansion hover effect.*

### HTML
```html
<button class="btn-1">Button 1</button>
```

### CSS
```css
.btn-1 {
    background: #111;
    color: #00f0ff;
    border: 2px solid #00f0ff;
    padding: 12px 28px;
    font-size: 16px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 2px;
    cursor: pointer;
    border-radius: 6px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
    box-shadow: 0 0 0 0 rgba(0, 240, 255, 0.7);
}

.btn-1:hover {
    background: #00f0ff;
    color: #111;
    box-shadow: 0 0 20px 5px rgba(0, 240, 255, 0.7);
    text-shadow: 0 0 5px rgba(255, 255, 255, 0.5);
}
```

---

## Button #2: Glassmorphism Reflector
*Glassmorphic backdrop-blur card styling with a shiny diagonal reflection sweep.*

### HTML
```html
<button class="btn-2">Button 2</button>
```

### CSS
```css
.btn-2 {
    background: rgba(255, 255, 255, 0.05);
    color: #fff;
    border: 1px solid rgba(255, 255, 255, 0.15);
    padding: 12px 28px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    border-radius: 12px;
    position: relative;
    overflow: hidden;
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    transition: background 0.3s, border-color 0.3s;
}

.btn-2::before {
    content: '';
    position: absolute;
    top: 0;
    left: -150%;
    width: 50%;
    height: 100%;
    background: linear-gradient(
        90deg,
        transparent,
        rgba(255, 255, 255, 0.4),
        transparent
    );
    transform: skewX(-25deg);
    transition: 0.75s;
}

.btn-2:hover::before {
    left: 150%;
}

.btn-2:hover {
    background: rgba(255, 255, 255, 0.15);
    border-color: rgba(255, 255, 255, 0.3);
}
```

---

## Button #3: Perimeter Border Tracer
*Smoothly draws borders along the top-left and bottom-right edges on hover.*

### HTML
```html
<button class="btn-3">Button 3</button>
```

### CSS
```css
.btn-3 {
    background: transparent;
    color: #ff3366;
    border: 1px solid rgba(255, 51, 102, 0.2);
    padding: 12px 28px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    position: relative;
    transition: color 0.3s, border-color 0.3s;
}

.btn-3::before,
.btn-3::after {
    content: '';
    position: absolute;
    width: 0;
    height: 0;
    box-sizing: border-box;
    transition: width 0.2s ease, height 0.2s ease 0.2s;
}

.btn-3::before {
    top: 0;
    left: 0;
    border-top: 2px solid #ff3366;
    border-left: 2px solid #ff3366;
}

.btn-3::after {
    bottom: 0;
    right: 0;
    border-bottom: 2px solid #ff3366;
    border-right: 2px solid #ff3366;
}

.btn-3:hover::before,
.btn-3:hover::after {
    width: 100%;
    height: 100%;
}

.btn-3:hover {
    color: #ff3366;
    border-color: transparent;
}
```

---

## Button #4: Liquid Blob Waves
*Rotational filling liquid wave structure that pushes up from the bottom.*

### HTML
```html
<button class="btn-4"><span>Button 4</span></button>
```

### CSS
```css
.btn-4 {
    background: transparent;
    color: #00e676;
    border: 2px solid #00e676;
    padding: 12px 28px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    position: relative;
    overflow: hidden;
    border-radius: 30px;
    z-index: 1;
    transition: color 0.4s;
}

.btn-4::before {
    content: '';
    position: absolute;
    top: 100%;
    left: 50%;
    width: 150%;
    height: 300%;
    background: #00e676;
    border-radius: 40%;
    transform: translate(-50%, 0) rotate(0deg);
    transition: transform 0.8s ease, top 0.8s ease;
    z-index: -1;
}

.btn-4:hover::before {
    top: -60%;
    transform: translate(-50%, 0) rotate(360deg);
}

.btn-4:hover {
    color: #111;
}

.btn-4 span {
    position: relative;
    z-index: 2;
}
```

---

## Button #5: Dynamic Gradient Mesh
*Flowing multi-color linear gradient shifting constantly inside a capsule pill wrapper.*

### HTML
```html
<button class="btn-5">Button 5</button>
```

### CSS
```css
.btn-5 {
    background: linear-gradient(45deg, #ff007f, #7f00ff, #00f0ff, #ff007f);
    background-size: 400% 400%;
    color: #fff;
    border: none;
    padding: 12px 28px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    border-radius: 50px;
    box-shadow: 0 4px 15px 0 rgba(127, 0, 255, 0.45);
    transition: all 0.3s ease;
    animation: gradient-shift 12s ease infinite;
}

.btn-5:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 20px 0 rgba(127, 0, 255, 0.6);
}

.btn-5:active {
    transform: translateY(-1px);
}

@keyframes gradient-shift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}
```

---

## Button #6: Magnetic Aura Expander
*Spawns a massive scale-blured pulsing backdrop shadow aura around the button edges.*

### HTML
```html
<button class="btn-6">Button 6</button>
```

### CSS
```css
.btn-6 {
    background: #6200ea;
    color: #fff;
    border: none;
    padding: 12px 28px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    border-radius: 8px;
    position: relative;
    z-index: 1;
}

.btn-6::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    border-radius: 8px;
    background: #6200ea;
    z-index: -1;
    transition: transform 0.3s, opacity 0.3s;
}

.btn-6:hover::before {
    transform: scale(1.25, 1.45);
    opacity: 0;
}
```

---

## Button #7: Corner Bracket Draw
*Corner bracket accents expand symmetrically to wrap around the button margins.*

### HTML
```html
<button class="btn-7">Button 7</button>
```

### CSS
```css
.btn-7 {
    background: transparent;
    color: #e040fb;
    border: none;
    padding: 12px 28px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    position: relative;
    transition: color 0.3s;
}

.btn-7::before,
.btn-7::after {
    content: '';
    position: absolute;
    width: 12px;
    height: 12px;
    border: 2px solid #e040fb;
    transition: all 0.35s ease;
}

.btn-7::before {
    top: 0;
    left: 0;
    border-right: none;
    border-bottom: none;
}

.btn-7::after {
    bottom: 0;
    right: 0;
    border-left: none;
    border-top: none;
}

.btn-7:hover::before,
.btn-7:hover::after {
    width: 100%;
    height: 100%;
    border-radius: 4px;
}

.btn-7:hover {
    color: #f3e5f5;
    text-shadow: 0 0 4px rgba(224, 64, 251, 0.4);
}
```

---

## Button #8: Shimmer Rotating Border
*A modern high-end React/CSS component where a rotating conic-gradient forms a glowing shimmer beam running around the border perimeter.*

### HTML
```html
<button class="btn-8">
    <span class="btn-8-shim"></span>
    <span class="btn-8-content">Button 8</span>
</button>
```

### CSS
```css
.btn-8 {
    position: relative;
    overflow: hidden;
    padding: 2px;
    border-radius: 8px;
    background: transparent;
    border: none;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    justify-content: center;
}

.btn-8-shim {
    position: absolute;
    top: -150%;
    left: -150%;
    width: 400%;
    height: 400%;
    background: conic-gradient(
        from 90deg at 50% 50%,
        #e2cbff 0%,
        #393bb2 50%,
        #e2cbff 100%
    );
    animation: spin-shimmer 3s linear infinite;
    z-index: 1;
}

.btn-8-content {
    position: relative;
    z-index: 2;
    background: #0b0f19;
    color: #fff;
    padding: 10px 26px;
    border-radius: 6px;
    font-size: 16px;
    font-weight: 600;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    transition: background 0.3s;
}

.btn-8:hover .btn-8-content {
    background: rgba(11, 15, 25, 0.8);
}

@keyframes spin-shimmer {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}
```

---

## Button #9: Cosmic Portal Launch
*A premium WebGL-powered launch button featuring a cosmic event horizon animation inside the button core, responsive physics-based warping on hover, and an interactive flash-expansion ignition transition upon click.*

### HTML
```html
<div class="launch-portal-wrap">
    <div id="launch-container" class="launch-portal-container">
        <button id="ignition-btn" type="button" class="launch-portal-btn">
            <span class="launch-portal-inner">
                <canvas id="portal-canvas" class="launch-portal-canvas" aria-hidden="true"></canvas>
                <span class="launch-portal-text">LAUNCH</span>
            </span>
        </button>
    </div>
</div>
```

### CSS
```css
.launch-portal-wrap {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 3rem;
    padding-bottom: 3rem;
    width: 100%;
    height: 100%;
}

.launch-portal-container {
    opacity: 0;
    transform: scale(0.6);
    filter: blur(10px);
}

.launch-portal-btn {
    position: relative;
    display: block;
    width: 264px;
    height: 78px;
    border: 0;
    padding: 7px;
    border-radius: 24px;
    cursor: pointer;
    outline: none;
    transition: all 0.3s cubic-bezier(0.34, 1.4, 0.5, 1);
    background: linear-gradient(180deg, #3c3f46 0%, #15171b 55%, #2a2d33 100%);
    box-shadow: 
        0 26px 52px rgba(15, 12, 10, 0.35),
        0 3px 10px rgba(0, 0, 0, 0.35),
        inset 0 1px 0 rgba(255, 255, 255, 0.14);
}

.launch-portal-btn:hover {
    transform: translateY(-2px);
    box-shadow: 
        0 32px 64px rgba(160, 60, 12, 0.3),
        0 4px 12px rgba(0, 0, 0, 0.4),
        inset 0 1px 0 rgba(255, 255, 255, 0.16);
}

.launch-portal-btn:active {
    transform: translateY(1px) scale(0.985);
}

.launch-portal-btn:focus-visible {
    outline: 2px solid #d43d17;
    outline-offset: 5px;
}

.launch-portal-inner {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    border-radius: 17px;
    overflow: hidden;
    background-color: #06050a;
    box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.9);
}

.launch-portal-canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: block;
}

.launch-portal-text {
    position: relative;
    z-index: 10;
    pointer-events: none;
    font-weight: 500;
    font-size: 0.875rem;
    letter-spacing: 0.34em;
    text-indent: 0.34em;
    color: #fdf6ee;
    text-transform: uppercase;
    font-family: 'Inter', sans-serif;
    text-shadow: 
        0 0 14px rgba(255, 170, 100, 0.55),
        0 1px 6px rgba(0, 0, 0, 0.9);
}
```

### JavaScript
```javascript
// Note: Requires GSAP loaded from CDN:
// <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>

(function() {
    const container = document.getElementById('launch-container');
    const btn = document.getElementById('ignition-btn');
    const canvas = document.getElementById('portal-canvas');
    if (!container || !btn || !canvas) return;
    
    const gl = canvas.getContext('webgl');

    // Initial Animation
    gsap.to(container, {
        scale: 1,
        opacity: 1,
        duration: 1.2,
        ease: "back.out(1.7)",
        onUpdate: function() {
            let progress = this.progress();
            let blurAmount = Math.max(0, 10 * (1 - progress * 1.2));
            container.style.filter = `blur(${blurAmount}px)`;
        }
    });

    // Mouse Parallax
    document.addEventListener("mousemove", (e) => {
        const x = (e.clientX / window.innerWidth - 0.5) * 15;
        const y = (e.clientY / window.innerHeight - 0.5) * 15;
        gsap.to(container, { x, y, duration: 2, ease: "power2.out" });
    });

    if (!gl) return;

    const VS = 'attribute vec2 p;void main(){gl_Position=vec4(p,0.,1.);}';
    const FS = `
    precision highp float;
    uniform vec2 u_res;
    uniform float u_time;
    uniform float u_warp;
    uniform float u_flash;
    float hash(vec2 p){return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453123);}
    float noise(vec2 p){
    vec2 i=floor(p), f=fract(p);
    vec2 u=f*f*(3.0-2.0*f);
    return mix(mix(hash(i),hash(i+vec2(1.,0.)),u.x),mix(hash(i+vec2(0.,1.)),hash(i+vec2(1.,1.)),u.x),u.y);
    }
    float fbm(vec2 p){
    float v=0.0; float a=0.5;
    for(int i=0;i<4;i++){ v+=a*noise(p); p=p*2.07+vec2(13.1,5.7); a*=0.5; }
    return v;
    }
    void main(){
    vec2 sc = gl_FragCoord.xy / u_res;
    vec2 uv = (gl_FragCoord.xy - 0.5 * u_res) / u_res.y;
    float r = length(uv), rr = max(r, 0.08), a = atan(uv.y, uv.x), t = u_time;
    vec3 col = vec3(0.012, 0.011, 0.014);
    float hz = fbm(uv * 2.6 + vec2(t * 0.35, 1.7));
    col += vec3(0.13, 0.06, 0.032) * hz * (0.7 + 0.6 * u_warp);
    for (int i = 0; i < 3; i++) {
    float fi = float(i), ringN = 26.0 + fi * 9.0;
    vec2 sp = vec2((a / 6.28318 + 0.5) * ringN, (0.3 + fi * 0.22) / rr + t * (2.0 + fi * 1.2));
    vec2 cell = floor(sp), f = fract(sp);
    float h = hash(cell + vec2(fi * 17.31)), on = step(0.68, h);
    vec2 c = vec2(0.2 + 0.6 * hash(cell + vec2(4.7)), 0.5), dlt = f - c;
    float sy = mix(130.0, 8.0, u_warp), star = on * exp(-(dlt.x * dlt.x * 150.0 + dlt.y * dlt.y * sy));
    float tw = (0.7 + 0.3 * sin(h * 81.0 + t * 9.0));
    vec3 sCol = mix(vec3(1.0, 0.94, 0.85), vec3(1.0, 0.6, 0.33), step(0.9, h));
    col += sCol * star * mix(tw, 1.0, u_warp) * smoothstep(0.02, 0.25, r) * (1.1 + 0.7 * u_warp);
    }
    col += vec3(1.0, 0.8, 0.58) * u_warp * 0.32 * exp(-r * 4.0);
    col = mix(col, vec3(1.0, 0.97, 0.92), clamp(u_flash, 0.0, 1.0));
    gl_FragColor = vec4(col, 1.0);
    }`;

    function compile(type, src) {
        const s = gl.createShader(type);
        gl.shaderSource(s, src);
        gl.compileShader(s);
        return s;
    }
    const prog = gl.createProgram();
    gl.attachShader(prog, compile(gl.VERTEX_SHADER, VS));
    gl.attachShader(prog, compile(gl.FRAGMENT_SHADER, FS));
    gl.linkProgram(prog);
    gl.useProgram(prog);

    const buf = gl.createBuffer();
    gl.bindBuffer(gl.ARRAY_BUFFER, buf);
    gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([-1,-1,3,-1,-1,3]), gl.STATIC_DRAW);
    const locP = gl.getAttribLocation(prog, 'p');
    gl.enableVertexAttribArray(locP);
    gl.vertexAttribPointer(locP, 2, gl.FLOAT, false, 0, 0);

    const uRes = gl.getUniformLocation(prog, 'u_res'), uTime = gl.getUniformLocation(prog, 'u_time'),
    uWarp = gl.getUniformLocation(prog, 'u_warp'), uFlash = gl.getUniformLocation(prog, 'u_flash');

    let warp = 0, warpTarget = 0, flash = 0, z = 0, last = performance.now();
    btn.addEventListener('mouseenter', () => warpTarget = 1);
    btn.addEventListener('mouseleave', () => warpTarget = 0);
    btn.addEventListener('click', () => { flash = 1; warp = 0; z = 0; });

    function frame(now) {
        const dt = Math.min(0.05, (now - last) / 1000);
        last = now;
        warp += (warpTarget - warp) * Math.min(1, dt * 2.6);
        flash *= Math.exp(-4.5 * dt);
        z += dt * (0.05 + warp * 1.35);
        const dpr = Math.min(window.devicePixelRatio || 1, 2);
        const w = canvas.clientWidth * dpr, h = canvas.clientHeight * dpr;
        if (canvas.width !== w || canvas.height !== h) { canvas.width = w; canvas.height = h; gl.viewport(0, 0, w, h); }
        gl.uniform2f(uRes, canvas.width, canvas.height);
        gl.uniform1f(uTime, z);
        gl.uniform1f(uWarp, warp);
        gl.uniform1f(uFlash, flash);
        gl.drawArrays(gl.TRIANGLES, 0, 3);
        requestAnimationFrame(frame);
    }
    requestAnimationFrame(frame);
})();
```

---

## Button #10: Slide Arrow Button
*A pill-shaped button outline where hovering shifts the arrow container to fill the background and changes text color.*

### HTML
```html
<button class="btn-10">
    <div class="slide-bg"></div>
    <span class="arrow-icon">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <line x1="5" y1="12" x2="19" y2="12"></line>
            <polyline points="12 5 19 12 12 19"></polyline>
        </svg>
    </span>
    <span class="btn-text">Get Started</span>
</button>
```

### CSS
```css
.btn-10 {
    position: relative;
    width: 160px;
    height: 52px;
    background: #fff;
    border: 1px solid #fff;
    border-radius: 9999px;
    display: flex;
    align-items: center;
    cursor: pointer;
    overflow: hidden;
    transition: all 0.2s ease-in-out;
    padding: 0;
    font-family: inherit;
}
.btn-10 .slide-bg {
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    width: 44px;
    border-radius: 9999px;
    background-color: #6f3cff;
    transition: all 0.2s ease-in-out;
    z-index: 1;
}
.btn-10:hover .slide-bg {
    width: 100%;
}
.btn-10 .arrow-icon {
    position: absolute;
    left: 12px;
    z-index: 2;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.2s ease-in-out;
}
.btn-10:hover .arrow-icon {
    left: calc(100% - 32px);
}
.btn-10 .btn-text {
    position: relative;
    left: 48px;
    z-index: 3;
    font-weight: 600;
    color: #000;
    transition: all 0.2s ease-in-out;
    font-size: 0.9rem;
}
.btn-10:hover .btn-text {
    left: 20px;
    color: #fff;
}
```

---

## Button #11: Shimmer Button
*A premium button with a shimmering light effect traveling around the perimeter.*

### HTML
```html
<button class="btn-11">
    <div class="spark-container">
        <div class="spark-slide">
            <div class="spark-rotate"></div>
        </div>
    </div>
    <span class="btn-text">Shimmer Button</span>
    <div class="highlight"></div>
    <div class="backdrop"></div>
</button>
```

### CSS
```css
.btn-11 {
    --spread: 90deg;
    --shimmer-color: #ffffff;
    --radius: 100px;
    --speed: 3s;
    --cut: 0.05em;
    --bg: rgba(0, 0, 0, 1);
    
    position: relative;
    z-index: 0;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    border-radius: var(--radius);
    border: 1px solid rgba(255, 255, 255, 0.1);
    padding: 12px 24px;
    white-space: nowrap;
    color: #fff;
    background: var(--bg);
    cursor: pointer;
    transition: transform 0.3s ease-in-out;
    font-family: inherit;
    font-size: 16px;
    font-weight: 500;
}

.btn-11:active {
    transform: translateY(1px);
}

.btn-11 .spark-container {
    position: absolute;
    inset: 0;
    overflow: visible;
    z-index: -30;
    filter: blur(2px);
    container-type: size;
}

.btn-11 .spark-slide {
    position: absolute;
    inset: 0;
    aspect-ratio: 1 / 1;
    height: 100cqh;
    border-radius: 0;
    mask: none;
    -webkit-mask: none;
    animation: shimmer-slide var(--speed) ease-in-out infinite alternate;
}

.btn-11 .spark-rotate {
    position: absolute;
    inset: -100%;
    width: auto;
    transform: translate(0, 0) rotate(0deg);
    background: conic-gradient(
        from calc(270deg - (var(--spread) * 0.5)),
        transparent 0%,
        var(--shimmer-color) var(--spread),
        transparent var(--spread)
    );
    animation: spin-around calc(var(--speed) * 2) infinite linear;
}

.btn-11 .highlight {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    border-radius: inherit;
    box-shadow: inset 0 -8px 10px rgba(255, 255, 255, 0.12);
    transition: all 0.3s ease-in-out;
    pointer-events: none;
}

.btn-11:hover .highlight {
    box-shadow: inset 0 -6px 10px rgba(255, 255, 255, 0.25);
}

.btn-11:active .highlight {
    box-shadow: inset 0 -10px 10px rgba(255, 255, 255, 0.25);
}

.btn-11 .backdrop {
    position: absolute;
    inset: var(--cut);
    z-index: -20;
    border-radius: var(--radius);
    background: var(--bg);
}

@keyframes shimmer-slide {
    to {
        transform: translate(calc(100cqw - 100%), 0);
    }
}

@keyframes spin-around {
    0% {
        transform: translateZ(0) rotate(0deg);
    }
    15%, 35% {
        transform: translateZ(0) rotate(90deg);
    }
    65%, 85% {
        transform: translateZ(0) rotate(270deg);
    }
    100% {
        transform: translateZ(0) rotate(360deg);
    }
}
```




