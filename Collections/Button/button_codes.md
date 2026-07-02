# Premium Custom Button Code Database

This file contains the complete, self-contained HTML and CSS code snippets for all **14 Premium Buttons** featured in the interactive showcase. Each button is numbered to match the UI labels in the application.

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
12. [Button #12: Diagonal Slide Fill](#button-12-diagonal-slide-fill)
13. [Button #13: Valence Core WebGL](#button-13-valence-core-webgl)
14. [Button #14: Shining Button](#button-14-shining-button)

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

---

## Button #12: Diagonal Slide Fill
*A minimalist outline button with a diagonal purple sliding background block that slides in from the bottom-left on hover, cleanly changing the text color from black to white.*

### HTML
```html
<a href="#" class="btn-12">
    <span class="btn-12-slide"></span>
    <span class="btn-12-text">Animation Button</span>
</a>
```

### CSS
```css
.btn-12 {
    position: relative;
    display: inline-flex;
    align-items: center;
    justify-content: flex-start;
    padding: 8px 24px;
    overflow: hidden;
    font-weight: 500;
    font-size: 16px;
    text-decoration: none;
    transition: all 0.3s ease;
    background-color: #ffffff;
    border-radius: 4px;
    outline: 1px solid #000000;
    cursor: pointer;
}

.btn-12-slide {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 192px;  /* 12rem / w-48 */
    height: 192px; /* 12rem / h-48 */
    background-color: #9333ea; /* bg-purple-600 */
    border-radius: 4px;
    transform: rotate(-40deg) translate(-100%, 100%);
    margin-bottom: 36px; /* mb-9 */
    margin-left: 36px;  /* ml-9 */
    transition: all 0.5s ease-out;
    z-index: 1;
}

.btn-12-text {
    position: relative;
    width: 100%;
    text-align: left;
    color: #000000;
    transition: color 0.3s ease-in-out;
    z-index: 2;
}

.btn-12:hover .btn-12-slide {
    margin-left: 0;
    margin-bottom: 128px; /* mb-32 */
    transform: rotate(-40deg) translate(0, 0);
}

.btn-12:hover .btn-12-text {
    color: #ffffff;
}
```

### React/Next.js (Source Component)
```tsx
"use client"
import React from "react"
import { cn } from "@/lib/utils"

interface DiagonalButtonProps {
  label?: string
  href?: string
  className?: string
  onClick?: (e: React.MouseEvent<HTMLAnchorElement>) => void
}

/**
 * A custom transition button with a diagonal purple slide fill on hover.
 */
export const DiagonalButton = ({
  label = "Animation Button",
  href = "#",
  className = "",
  onClick,
}: DiagonalButtonProps) => {
  return (
    <div className={cn("flex flex-col items-center gap-4 p-4 rounded-lg", className)}>
      <a
        href={href}
        onClick={onClick}
        className="relative inline-flex items-center justify-start px-6 py-2 overflow-hidden font-medium transition-all bg-white rounded hover:bg-white group outline outline-1"
      >
        <span className="w-48 h-48 rounded rotate-[-40deg] bg-purple-600 absolute bottom-0 left-0 -translate-x-full ease-out duration-500 transition-all translate-y-full mb-9 ml-9 group-hover:ml-0 group-hover:mb-32 group-hover:translate-x-0" />
        <span className="relative w-full text-left text-black transition-colors duration-300 ease-in-out group-hover:text-white">
          {label}
        </span>
      </a>
    </div>
  )
}

export default DiagonalButton;
```

---

## Button #13: Valence Core WebGL
*A futuristic, WebGL-powered interactive button. Features dynamic shader-drawn pulsing energy arcs that wrap the button outline, scaling neon core glow, custom mouse state translations, and a GSAP/Web Animations API sequence on load. Cleanly optimized for React client runtimes and Next.js SSR.*

### HTML
```html
<div class="valence-core-container" id="valence-core-container-13">
  <button
    id="btn-valence-13"
    type="button"
    class="btn-valence"
  >
    <canvas 
      id="btn-gl-canvas-13" 
      class="btn-gl-canvas"
    ></canvas>
    <span class="btn-valence-text">VALENCE CORE</span>
  </button>
</div>
```

### CSS
```css
.valence-core-container {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    min-height: 200px;
}

.btn-valence {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 280px;
    height: 96px;
    background: transparent;
    border: none;
    cursor: pointer;
    border-radius: 18px;
    transition: transform .22s cubic-bezier(.34, 1.4, .5, 1);
    opacity: 0;
    transform: scale(0.92);
}

.btn-valence:focus-visible {
    outline: none;
    box-shadow: 0 0 0 2px #06b6d4, 0 0 0 4px #0a0e17;
}

.btn-gl-canvas {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    display: block;
    border-radius: 18px;
    filter: drop-shadow(0 0 15px rgba(6, 182, 212, 0.2));
    pointer-events: none;
}

.btn-valence-text {
    position: relative;
    z-index: 10;
    pointer-events: none;
    font-weight: 500;
    font-size: 14px;
    letter-spacing: 0.3em;
    padding-left: 0.3em;
    color: #e0f7f8;
    text-shadow: 0 0 12px rgba(0, 210, 255, .6), 0 1px 4px rgba(0, 0, 0, .8);
}
```

### JavaScript
```javascript
(function() {
    const container = document.getElementById('valence-core-container-13');
    if (!container) return;
    const btn = container.querySelector('#btn-valence-13');
    const canvas = container.querySelector('#btn-gl-canvas-13');
    if (!btn || !canvas) return;
    const reduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

    // --- Entrance Animation ---
    if (typeof gsap !== 'undefined') {
        gsap.to(btn, {
            keyframes: {
                "0%":   { opacity: 0, scale: 0.92 },
                "9%":   { opacity: 0.85 },
                "15%":  { opacity: 0.12 },
                "24%":  { opacity: 0.92 },
                "31%":  { opacity: 0.35 },
                "44%":  { opacity: 1, scale: 1.015 },
                "100%": { opacity: 1, scale: 1 }
            },
            duration: 1.15,
            ease: "none"
        });
    } else {
        btn.style.opacity = '1';
        btn.style.transform = 'scale(1)';
    }

    // --- Interactive States ---
    btn.addEventListener('mouseover', () => btn.style.transform = 'translateY(-2px)');
    btn.addEventListener('mouseout', () => btn.style.transform = 'translateY(0)');
    btn.addEventListener('mousedown', () => btn.style.transform = 'translateY(1px) scale(.99)');
    btn.addEventListener('mouseup', () => btn.style.transform = 'translateY(-2px)');

    // --- WebGL Core ---
    const gl = canvas.getContext('webgl', { alpha: false, antialias: true });
    if (!gl) {
        btn.style.background = '#062630';
        return;
    }

    const vsSource = 'attribute vec2 p;void main(){gl_Position=vec4(p,0.,1.);}';
    const fsSource = `
        precision highp float;
        uniform vec2 u_res;
        uniform float u_time;
        uniform float u_arcs;
        uniform float u_flash;
        float hash(vec2 p){return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453123);}
        float noise(vec2 p){
            vec2 i=floor(p), f=fract(p);
            vec2 u=f*f*(3.0-2.0*f);
            return mix(mix(hash(i),hash(i+vec2(1.,0.)),u.x),mix(hash(i+vec2(0.,1.)),hash(i+vec2(1.,1.)),u.x),u.y);
        }
        float fbm(vec2 p){
            float v=0.0; float a=0.5;
            for(int i=0;i<4;i++){ v+=a*noise(p); p=p*2.05+vec2(9.7,3.1); a*=0.5; }
            return v;
        }
        float sdRBox(vec2 p, vec2 b, float r){
            vec2 q = abs(p) - b + r;
            return length(max(q, 0.0)) + min(max(q.x, q.y), 0.0) - r;
        }
        void main(){
            vec2 p = (gl_FragCoord.xy - 0.5 * u_res) / u_res.y;
            float ar = u_res.x / u_res.y;
            vec2 hs = vec2(ar * 0.5 - 0.2, 0.5 - 0.2);
            float d = sdRBox(p, hs, 0.14);
            float t = u_time;
            float hover = clamp(u_arcs / 6.0, 0.0, 1.0);
            vec3 col = vec3(0.039, 0.039, 0.039);
            float plate = 1.0 - smoothstep(-0.004, 0.004, d);
            vec3 plateCol = vec3(0.04, 0.05, 0.055) + vec3(0.014, 0.022, 0.035) * fbm(p * 9.0);
            plateCol += vec3(0.0, 0.25, 0.3) * exp(d * 9.0) * (0.25 + hover * 0.6);
            col = mix(col, plateCol, plate);
            col *= 1.0 + 0.5 * exp(-max(d, 0.0) * 16.0) * (1.0 - plate);
            float a = atan(p.y, p.x);
            vec3 arcCol = vec3(0.0);
            for (int i = 0; i < 6; i++) {
                float fi = float(i);
                float w = clamp(u_arcs - fi, 0.0, 1.0);
                float n1 = fbm(vec2(a * 2.4 + fi * 11.3, t * (1.6 + fi * 0.27) + fi * 53.1));
                float off = (n1 - 0.5) * (0.11 + u_flash * 0.1);
                float seg = 0.3 + 0.7 * smoothstep(0.35, 0.75, noise(vec2(a * 1.8 + fi * 7.7, t * (0.9 + fi * 0.13) + fi * 19.0)));
                float g = 0.0042 / (abs(d + off) + 0.006);
                arcCol += (vec3(0.0, 0.75, 0.9) * g + vec3(0.6, 1.0, 0.95) * g * g * 0.55) * w * seg;
            }
            float outerMask = 1.0 - smoothstep(0.04, 0.15, d);
            col += arcCol * (0.6 + 0.4 * hover) * outerMask;
            float ring = 0.006 / (abs(d) + 0.006);
            col += vec3(0.8, 0.98, 1.0) * ring * u_flash * 1.5 * outerMask;
            col += vec3(0.7, 0.95, 1.0) * u_flash * 0.16 * outerMask;
            gl_FragColor = vec4(col, 1.0);
        }
    `;

    function createShader(gl, type, source) {
        const s = gl.createShader(type);
        gl.shaderSource(s, source);
        gl.compileShader(s);
        return s;
    }

    const program = gl.createProgram();
    gl.attachShader(program, createShader(gl, gl.VERTEX_SHADER, vsSource));
    gl.attachShader(program, createShader(gl, gl.FRAGMENT_SHADER, fsSource));
    gl.linkProgram(program);
    gl.useProgram(program);

    const buffer = gl.createBuffer();
    gl.bindBuffer(gl.ARRAY_BUFFER, buffer);
    gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([-1, -1, 3, -1, -1, 3]), gl.STATIC_DRAW);
    const locP = gl.getAttribLocation(program, 'p');
    gl.enableVertexAttribArray(locP);
    gl.vertexAttribPointer(locP, 2, gl.FLOAT, false, 0, 0);

    const uRes = gl.getUniformLocation(program, 'u_res');
    const uTime = gl.getUniformLocation(program, 'u_time');
    const uArcs = gl.getUniformLocation(program, 'u_arcs');
    const uFlash = gl.getUniformLocation(program, 'u_flash');

    let arcs = 2.4, arcsTarget = 2.4, flash = 0, crawl = 0, last = performance.now();

    function resize() {
        const dpr = Math.min(window.devicePixelRatio || 1, 2);
        const w = Math.round(btn.clientWidth * dpr);
        const h = Math.round(btn.clientHeight * dpr);
        if (canvas.width !== w || canvas.height !== h) {
            canvas.width = w; canvas.height = h;
            gl.viewport(0, 0, w, h);
        }
    }

    const handleMouseEnter = () => arcsTarget = 5.8;
    const handleMouseLeave = () => arcsTarget = 2.4;
    const handleBtnClick = () => flash = 1;

    btn.addEventListener('mouseenter', handleMouseEnter);
    btn.addEventListener('mouseleave', handleMouseLeave);
    btn.addEventListener('click', handleBtnClick);
    window.addEventListener('resize', resize);
    resize();

    let frameId;
    function render(now) {
        const dt = Math.min(0.05, (now - last) / 1000);
        last = now;
        arcs += (arcsTarget - arcs) * Math.min(1, dt * 5);
        flash *= Math.exp(-3.6 * dt);
        crawl += dt * (0.6 + (arcs / 6) * 1.1 + flash * 2.0);
        
        gl.uniform2f(uRes, canvas.width, canvas.height);
        gl.uniform1f(uTime, reduced ? 3.0 : crawl);
        gl.uniform1f(uArcs, arcs);
        gl.uniform1f(uFlash, flash);
        gl.drawArrays(gl.TRIANGLES, 0, 3);
        frameId = requestAnimationFrame(render);
    }
    frameId = requestAnimationFrame(render);

    container._btn13Cleanup = () => {
        cancelAnimationFrame(frameId);
        btn.removeEventListener('mouseenter', handleMouseEnter);
        btn.removeEventListener('mouseleave', handleMouseLeave);
        btn.removeEventListener('click', handleBtnClick);
        window.removeEventListener('resize', resize);
    };
})();
```

### React/Next.js (Source Component)
```tsx
"use client"
import React, { useEffect, useRef } from "react"
import { cn } from "@/lib/utils"

interface ValenceButtonProps {
  className?: string
  label?: string
  onClick?: () => void
}

export const ValenceButton = ({
  className,
  label = "VALENCE CORE",
  onClick,
}: ValenceButtonProps) => {
  const containerRef = useRef<HTMLDivElement>(null)
  const btnRef = useRef<HTMLButtonElement>(null)
  const canvasRef = useRef<HTMLCanvasElement>(null)

  useEffect(() => {
    const btn = btnRef.current
    const canvas = canvasRef.current
    if (!btn || !canvas) return

    const reduced = window.matchMedia("(prefers-reduced-motion: reduce)").matches

    // --- Entrance Animation (Safe Web Animations API instead of external script load) ---
    btn.style.opacity = "0"
    btn.style.transform = "scale(0.92)"
    
    const keyframes = [
      { opacity: 0, transform: "scale(0.92)", offset: 0 },
      { opacity: 0.85, offset: 0.09 },
      { opacity: 0.12, offset: 0.15 },
      { opacity: 0.92, offset: 0.24 },
      { opacity: 0.35, offset: 0.31 },
      { opacity: 1, transform: "scale(1.015)", offset: 0.44 },
      { opacity: 1, transform: "scale(1)", offset: 1 }
    ]
    
    const anim = btn.animate(keyframes, {
      duration: 1150,
      easing: "linear",
      fill: "forwards"
    })

    // --- Interactive States ---
    const handleMouseOver = () => {
      btn.style.transform = "translateY(-2px)"
    }
    const handleMouseOut = () => {
      btn.style.transform = "translateY(0)"
    }
    const handleMouseDown = () => {
      btn.style.transform = "translateY(1px) scale(.99)"
    }
    const handleMouseUp = () => {
      btn.style.transform = "translateY(-2px)"
    }

    btn.addEventListener("mouseover", handleMouseOver)
    btn.addEventListener("mouseout", handleMouseOut)
    btn.addEventListener("mousedown", handleMouseDown)
    btn.addEventListener("mouseup", handleMouseUp)

    // --- WebGL Core ---
    const gl = canvas.getContext("webgl", { alpha: false, antialias: true })
    if (!gl) {
      btn.style.background = "#062630"
      return
    }

    const vsSource = "attribute vec2 p;void main(){gl_Position=vec4(p,0.,1.);}"
    const fsSource = `
      precision highp float;
      uniform vec2 u_res;
      uniform float u_time;
      uniform float u_arcs;
      uniform float u_flash;
      float hash(vec2 p){return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453123);}
      float noise(vec2 p){
        vec2 i=floor(p), f=fract(p);
        vec2 u=f*f*(3.0-2.0*f);
        return mix(mix(hash(i),hash(i+vec2(1.,0.)),u.x),mix(hash(i+vec2(0.,1.)),hash(i+vec2(1.,1.)),u.x),u.y);
      }
      float fbm(vec2 p){
        float v=0.0; float a=0.5;
        for(int i=0;i<4;i++){ v+=a*noise(p); p=p*2.05+vec2(9.7,3.1); a*=0.5; }
        return v;
      }
      float sdRBox(vec2 p, vec2 b, float r){
        vec2 q = abs(p) - b + r;
        return length(max(q, 0.0)) + min(max(q.x, q.y), 0.0) - r;
      }
      void main(){
        vec2 p = (gl_FragCoord.xy - 0.5 * u_res) / u_res.y;
        float ar = u_res.x / u_res.y;
        vec2 hs = vec2(ar * 0.5 - 0.2, 0.5 - 0.2);
        float d = sdRBox(p, hs, 0.14);
        float t = u_time;
        float hover = clamp(u_arcs / 6.0, 0.0, 1.0);
        vec3 col = vec3(0.039, 0.039, 0.039);
        float plate = 1.0 - smoothstep(-0.004, 0.004, d);
        vec3 plateCol = vec3(0.04, 0.05, 0.055) + vec3(0.014, 0.022, 0.035) * fbm(p * 9.0);
        plateCol += vec3(0.0, 0.25, 0.3) * exp(d * 9.0) * (0.25 + hover * 0.6);
        col = mix(col, plateCol, plate);
        col *= 1.0 + 0.5 * exp(-max(d, 0.0) * 16.0) * (1.0 - plate);
        float a = atan(p.y, p.x);
        vec3 arcCol = vec3(0.0);
        for (int i = 0; i < 6; i++) {
          float fi = float(i);
          float w = clamp(u_arcs - fi, 0.0, 1.0);
          float n1 = fbm(vec2(a * 2.4 + fi * 11.3, t * (1.6 + fi * 0.27) + fi * 53.1));
          float off = (n1 - 0.5) * (0.11 + u_flash * 0.1);
          float seg = 0.3 + 0.7 * smoothstep(0.35, 0.75, noise(vec2(a * 1.8 + fi * 7.7, t * (0.9 + fi * 0.13) + fi * 19.0)));
          float g = 0.0042 / (abs(d + off) + 0.006);
          arcCol += (vec3(0.0, 0.75, 0.9) * g + vec3(0.6, 1.0, 0.95) * g * g * 0.55) * w * seg;
        }
        float outerMask = 1.0 - smoothstep(0.04, 0.15, d);
        col += arcCol * (0.6 + 0.4 * hover) * outerMask;
        float ring = 0.006 / (abs(d) + 0.006);
        col += vec3(0.8, 0.98, 1.0) * ring * u_flash * 1.5 * outerMask;
        col += vec3(0.7, 0.95, 1.0) * u_flash * 0.16 * outerMask;
        gl_FragColor = vec4(col, 1.0);
      }
    `

    function createShader(glContext: WebGLRenderingContext, type: number, source: string) {
      const s = glContext.createShader(type)
      if (!s) return null
      glContext.shaderSource(s, source)
      glContext.compileShader(s)
      return s
    }

    const vs = createShader(gl, gl.VERTEX_SHADER, vsSource)
    const fs = createShader(gl, gl.FRAGMENT_SHADER, fsSource)
    if (!vs || !fs) return

    const program = gl.createProgram()
    if (!program) return
    gl.attachShader(program, vs)
    gl.attachShader(program, fs)
    gl.linkProgram(program)
    gl.useProgram(program)

    const buffer = gl.createBuffer()
    gl.bindBuffer(gl.ARRAY_BUFFER, buffer)
    gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([-1, -1, 3, -1, -1, 3]), gl.STATIC_DRAW)
    const locP = gl.getAttribLocation(program, "p")
    gl.enableVertexAttribArray(locP)
    gl.vertexAttribPointer(locP, 2, gl.FLOAT, false, 0, 0)

    const uRes = gl.getUniformLocation(program, "u_res")
    const uTime = gl.getUniformLocation(program, "u_time")
    const uArcs = gl.getUniformLocation(program, "u_arcs")
    const uFlash = gl.getUniformLocation(program, "u_flash")

    let arcs = 2.4, arcsTarget = 2.4, flash = 0, crawl = 0, last = performance.now()

    function resize() {
      if (!btn || !canvas || !gl) return
      const dpr = Math.min(window.devicePixelRatio || 1, 2)
      const w = Math.round(btn.clientWidth * dpr)
      const h = Math.round(btn.clientHeight * dpr)
      if (canvas.width !== w || canvas.height !== h) {
        canvas.width = w
        canvas.height = h
        gl.viewport(0, 0, w, h)
      }
    }

    const handleMouseEnter = () => {
      arcsTarget = 5.8
    }
    const handleMouseLeave = () => {
      arcsTarget = 2.4
    }
    const handleBtnClick = () => {
      flash = 1
      onClick?.()
    }

    btn.addEventListener("mouseenter", handleMouseEnter)
    btn.addEventListener("mouseleave", handleMouseLeave)
    btn.addEventListener("click", handleBtnClick)
    window.addEventListener("resize", resize)
    
    resize()

    let frameId: number
    function render(now: number) {
      if (!gl || !canvas) return
      const dt = Math.min(0.05, (now - last) / 1000)
      last = now
      arcs += (arcsTarget - arcs) * Math.min(1, dt * 5)
      flash *= Math.exp(-3.6 * dt)
      crawl += dt * (0.6 + (arcs / 6) * 1.1 + flash * 2.0)
      
      gl.uniform2f(uRes, canvas.width, canvas.height)
      gl.uniform1f(uTime, reduced ? 3.0 : crawl)
      gl.uniform1f(uArcs, arcs)
      gl.uniform1f(uFlash, flash)
      gl.drawArrays(gl.TRIANGLES, 0, 3)
      frameId = requestAnimationFrame(render)
    }
    frameId = requestAnimationFrame(render)

    return () => {
      cancelAnimationFrame(frameId)
      anim.cancel()
      btn.removeEventListener("mouseover", handleMouseOver)
      btn.removeEventListener("mouseout", handleMouseOut)
      btn.removeEventListener("mousedown", handleMouseDown)
      btn.removeEventListener("mouseup", handleMouseUp)
      btn.removeEventListener("mouseenter", handleMouseEnter)
      btn.removeEventListener("mouseleave", handleMouseLeave)
      btn.removeEventListener("click", handleBtnClick)
      window.removeEventListener("resize", resize)
      gl.deleteBuffer(buffer)
      gl.deleteProgram(program)
      gl.deleteShader(vs)
      gl.deleteShader(fs)
    }
  }, [onClick])

  return (
    <div
      ref={containerRef}
      className={cn("relative flex justify-center items-center w-full min-h-[200px]", className)}
      id="valence-core-container"
    >
      <button
        ref={btnRef}
        id="btn-valence"
        type="button"
        className="relative flex items-center justify-center w-[280px] h-[96px] bg-transparent cursor-pointer rounded-[18px] focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-cyan-500 focus-visible:ring-offset-2 focus-visible:ring-offset-neutral-950 group transition-transform duration-200 ease-[cubic-bezier(.34,1.4,.5,1)]"
      >
        <canvas
          ref={canvasRef}
          id="btn-gl-canvas"
          aria-hidden="true"
          className="absolute inset-0 w-full h-full block rounded-[18px] [filter:drop-shadow(0_0_15px_rgba(6,182,212,0.2))]"
        />
        
        <span
          className="relative z-10 pointer-events-none font-medium text-sm tracking-[0.3em] indent-[0.3em] text-[#e0f7f8]"
          style={{
            textShadow: "0 0 12px rgba(0, 210, 255, .6), 0 1px 4px rgba(0, 0, 0, .8)",
            fontFamily: "'Inter', sans-serif"
          }}
        >
          {label}
        </span>
      </button>
    </div>
  )
}

export default ValenceButton;

## Button #14: Shining Button
*A premium button featuring a shiny borders and a glare overlay effect that slides across the button on hover.*

### HTML
```html
<div class="shine-wrap-14">
  <button class="btn-shine-14">
    <div class="btn-shine-inner-14">
      See Calendar
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" class="shine-arrow-icon-14">
        <path d="M5 12h14"></path>
        <path d="m12 5 7 7-7 7"></path>
      </svg>
      <div class="shine-glare-14"></div>
    </div>
  </button>
</div>
```

### CSS
```css
@theme {
  --bg-striped: repeating-linear-gradient(45deg, #3B3A3D, #3B3A3D 5px, transparent 5px, transparent 20px);
  --animate-blink-red: blink-red 2s infinite linear;
}
@keyframes blink-red {
  0%, 100% {
    background-color: rgba(239, 68, 68, 0.7);
    box-shadow: 0 0 30px 10px rgba(239, 68, 68, 0.5);
  }
  50% {
    background-color: rgba(239, 68, 68, 0.5);
    box-shadow: 0 0 30px 10px rgba(239, 68, 68, 1);
  }
}
```

### JavaScript
```javascript
// Pure CSS interactive states - no JavaScript required.
```

### React/Next.js
```tsx
import { ArrowRight } from "lucide-react";
import { cn } from "@/lib/utils";

export default function ShiningButton() {
  const label = "See Calendar";
  return (
    <button className="group/shine cursor-pointer rounded-xl border-4 border-violet-800/0 bg-transparent p-1 transition-colors duration-500 hover:border-violet-800/100">
      <div className="relative flex items-center justify-center gap-4 overflow-hidden rounded-lg bg-violet-800 px-6 py-4 font-bold text-white">
        {label}
        <ArrowRight className="transition-all duration-700 ease-in-out group-hover/shine:translate-x-2 group-hover/shine:scale-125" />
        <div
          className={cn(
            "absolute -left-16 top-0 h-full w-12 rotate-[30deg] scale-y-150 bg-white/10 transition-all duration-700 ease-in-out group-hover/shine:left-[calc(100%+1rem)]",
          )}
        />
      </div>
    </button>
  );
}
```
