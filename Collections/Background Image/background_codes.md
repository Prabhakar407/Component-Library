# Premium Custom Background Code Database

This file contains the complete, self-contained HTML, CSS, and JavaScript code snippets for all **14 Premium Backgrounds** featured in the interactive showcase. Each background is numbered to match the UI labels in the application.

---

# Premium Custom Background Code Database

This file contains the complete, self-contained HTML, CSS, and JavaScript code snippets for all **15 Premium Backgrounds** featured in the interactive showcase. Each background is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Effect #1: Cinematic Ken Burns Slider](#effect-1-cinematic-ken-burns-slider)
2. [Effect #2: Floating Mesh Gradient Overlay](#effect-2-floating-mesh-gradient-overlay)
3. [Effect #3: Interactive Depth Focus](#effect-3-interactive-depth-focus)
4. [Effect #4: Neural Aurora WebGL Shader](#effect-4-neural-aurora-webgl-shader)
5. [Effect #5: 3D Stellar Starfield](#effect-5-3d-stellar-starfield)
6. [Effect #6: 3D Neon GLSL Hills](#effect-6-3d-neon-glsl-hills)
7. [Effect #7: Dark Linear Gradient Streaks](#effect-7-dark-linear-gradient-streaks)
8. [Effect #8: Interactive Neural Vortex](#effect-8-interactive-neural-vortex)
9. [Effect #9: Animated Digital Streams](#effect-9-animated-digital-streams)
10. [Effect #10: Nexbot 3D Spline Robot](#effect-10-nexbot-3d-spline-robot)
11. [Effect #11: Unicorn Studio Fluid Shader](#effect-11-unicorn-studio-fluid-shader)
12. [Effect #12: Unicorn Studio Cyber Shader](#effect-12-unicorn-studio-cyber-shader)
13. [Effect #13: WebGL Cyber Glowing Trails](#effect-13-webgl-cyber-glowing-trails)
14. [Effect #14: Retrofuturistic Circuit Loop](#effect-14-retrofuturistic-circuit-loop)
15. [Effect #15: Shooting Stars](#effect-15-shooting-stars)

---

## Effect #1: Cinematic Ken Burns Slider
*Smooth directional panning and zooming transitions of slides looping infinitely.*

### HTML
```html
<div class="bg-effect-1" id="kb-slider-1">
    <div class="kb-slide active" style="background-image: url('https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?auto=format&fit=crop&w=1000&q=80')"></div>
    <div class="kb-slide" style="background-image: url('https://images.unsplash.com/photo-1447752875215-b2761acb3c5d?auto=format&fit=crop&w=1000&q=80')"></div>
    <div class="kb-slide" style="background-image: url('https://images.unsplash.com/photo-1469474968028-56623f02e42e?auto=format&fit=crop&w=1000&q=80')"></div>
    <div class="bg-title-overlay">Ken Burns Slide</div>
</div>
```

### CSS
```css
.bg-effect-1 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #000;
}

.bg-effect-1 .kb-slide {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    opacity: 0;
    z-index: 1;
    transform: scale(1.0);
    transition: opacity 1.5s ease-in-out;
}

.bg-effect-1 .kb-slide.active {
    opacity: 1;
    z-index: 2;
    animation: kenburns-anim 9s linear forwards;
}

@keyframes kenburns-anim {
    0% { transform: scale(1.0) translate(0, 0); }
    100% { transform: scale(1.15) translate(-1.5%, -1%); }
}

.bg-title-overlay {
    position: absolute;
    bottom: 15px;
    left: 15px;
    z-index: 5;
    font-size: 0.85rem;
    font-weight: 600;
    color: #fff;
    letter-spacing: 2px;
    text-transform: uppercase;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.8);
    pointer-events: none;
    background: rgba(14, 19, 31, 0.55);
    backdrop-filter: blur(4px);
    padding: 4px 10px;
    border-radius: 6px;
    border: 1px solid rgba(255, 255, 255, 0.06);
}
```

### JavaScript
```javascript
function initKenBurnsSlider() {
    const slider = document.getElementById('kb-slider-1');
    if (!slider) return;

    const slides = Array.from(slider.querySelectorAll('.kb-slide'));
    let current = 0;

    const interval = setInterval(() => {
        slides[current].classList.remove('active');
        current = (current + 1) % slides.length;
        slides[current].classList.add('active');
    }, 6000);

    slider._cleanup = () => {
        clearInterval(interval);
    };
}
```

---

## Effect #2: Floating Mesh Gradient Overlay
*Organic liquid blobs drifting and morphing behind a blend overlay to create a premium fluid look.*

### HTML
```html
<div class="bg-effect-2">
    <div class="mesh-bg-image" style="background-image: url('https://images.unsplash.com/photo-1475924156734-496f6cac6ec1?auto=format&fit=crop&w=1000&q=80')"></div>
    <div class="mesh-overlay">
        <div class="mesh-blob blob-1"></div>
        <div class="mesh-blob blob-2"></div>
        <div class="mesh-blob blob-3"></div>
    </div>
    <div class="bg-title-overlay">Mesh Gradients</div>
</div>
```

### CSS
```css
.bg-effect-2 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #06070a;
}

.bg-effect-2 .mesh-bg-image {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    filter: grayscale(35%) contrast(110%);
    opacity: 0.65;
}

.bg-effect-2 .mesh-overlay {
    position: absolute;
    inset: 0;
    mix-blend-mode: color-dodge;
    filter: blur(40px);
    opacity: 0.7;
    pointer-events: none;
    z-index: 2;
}

.bg-effect-2 .mesh-blob {
    position: absolute;
    border-radius: 50%;
    will-change: transform;
}

.bg-effect-2 .blob-1 {
    width: 160px;
    height: 160px;
    background: radial-gradient(circle, #6366f1 0%, transparent 70%);
    top: -20px;
    left: -20px;
    animation: mesh-blob-move-1 12s infinite alternate ease-in-out;
}

.bg-effect-2 .blob-2 {
    width: 200px;
    height: 200px;
    background: radial-gradient(circle, #ec4899 0%, transparent 70%);
    bottom: -40px;
    right: -20px;
    animation: mesh-blob-move-2 15s infinite alternate ease-in-out;
}

.bg-effect-2 .blob-3 {
    width: 140px;
    height: 140px;
    background: radial-gradient(circle, #06b6d4 0%, transparent 70%);
    top: 30%;
    left: 35%;
    animation: mesh-blob-move-3 10s infinite alternate ease-in-out;
}

@keyframes mesh-blob-move-1 {
    0% { transform: translate(0, 0) scale(1); }
    100% { transform: translate(50px, 30px) scale(1.2); }
}

@keyframes mesh-blob-move-2 {
    0% { transform: translate(0, 0) scale(1.1); }
    100% { transform: translate(-40px, -50px) scale(0.9); }
}

@keyframes mesh-blob-move-3 {
    0% { transform: translate(0, 0) scale(0.95); }
    100% { transform: translate(30px, -30px) scale(1.15); }
}
```

---

## Effect #3: Interactive Depth Focus
*A soft, dark, heavily blurred image background that smoothly zooms and focuses/brightens on cursor hover.*

### HTML
```html
<div class="bg-effect-3">
    <div class="focus-image" style="background-image: url('https://images.unsplash.com/photo-1518495973542-4542c06a5843?auto=format&fit=crop&w=1000&q=80')"></div>
    <div class="focus-overlay"></div>
    <div class="bg-title-overlay">Focus Blur</div>
</div>
```

### CSS
```css
.bg-effect-3 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #000;
    cursor: pointer;
}

.bg-effect-3 .focus-image {
    position: absolute;
    top: -5%;
    left: -5%;
    width: 110%;
    height: 110%;
    background-size: cover;
    background-position: center;
    filter: blur(8px) brightness(0.35) saturate(0.5);
    transform: scale(1.06);
    transition: all 0.8s cubic-bezier(0.25, 1, 0.5, 1);
}

.bg-effect-3:hover .focus-image {
    filter: blur(0px) brightness(0.85) saturate(1.1);
    transform: scale(1.0);
}

.bg-effect-3 .focus-overlay {
    position: absolute;
    inset: 0;
    background: radial-gradient(circle, transparent 30%, rgba(0,0,0,0.8) 100%);
    pointer-events: none;
    z-index: 2;
    opacity: 0.8;
    transition: opacity 0.8s ease;
}

.bg-effect-3:hover .focus-overlay {
    opacity: 0.3;
}
```

---

## Effect #4: Neural Aurora WebGL Shader
*A high-performance WebGL shader generating organic, shifting aurora-like energy bands with customizable colors, noise, and time-based wave distortions.*

### HTML
```html
<div class="bg-effect-4" id="aurora-wrap-4">
    <canvas class="aurora-canvas" id="aurora-canvas-4"></canvas>
    <div class="bg-title-overlay">Neural Aurora</div>
</div>
```

### CSS
```css
.bg-effect-4 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #020205;
}

.bg-effect-4 .aurora-canvas {
    display: block;
    width: 100%;
    height: 100%;
}
```

### JavaScript
```javascript
function initNeuralAurora() {
    const wrap = document.getElementById('aurora-wrap-4');
    if (!wrap) return;

    const canvas = document.getElementById('aurora-canvas-4');
    if (!canvas) return;

    const gl = canvas.getContext('webgl');
    if (!gl) return;

    const VS = `
        attribute vec2 p;
        void main() {
            gl_Position = vec4(p, 0.0, 1.0);
        }
    `;
    
    const FS = `
        precision highp float;
        uniform float iTime;
        uniform vec2 iResolution;

        #define NUM_OCTAVES 3

        float rand(vec2 n) {
            return fract(sin(dot(n, vec2(12.9898, 4.1414))) * 43758.5453);
        }

        float noise(vec2 p) {
            vec2 ip = floor(p);
            vec2 u = fract(p);
            u = u*u*(3.0-2.0*u);

            float res = mix(
                mix(rand(ip), rand(ip + vec2(1.0, 0.0)), u.x),
                mix(rand(ip + vec2(0.0, 1.0)), rand(ip + vec2(1.0, 1.0)), u.x), u.y);
            return res * res;
        }

        float fbm(vec2 x) {
            float v = 0.0;
            float a = 0.3;
            vec2 shift = vec2(100.0);
            mat2 rot = mat2(cos(0.5), sin(0.5), -sin(0.5), cos(0.5));
            for (int i = 0; i < NUM_OCTAVES; ++i) {
                v += a * noise(x);
                x = rot * x * 2.0 + shift;
                a *= 0.4;
            }
            return v;
        }

        vec4 my_tanh(vec4 x) {
            vec4 ex = exp(x);
            vec4 emx = exp(-x);
            return (ex - emx) / (ex + emx);
        }

        void main() {
            vec2 shake = vec2(sin(iTime * 1.2) * 0.005, cos(iTime * 2.1) * 0.005);
            vec2 p = ((gl_FragCoord.xy + shake * iResolution) - iResolution * 0.5) / iResolution.y * mat2(6.0, -4.0, 4.0, 6.0);
            vec2 v;
            vec4 o = vec4(0.0);

            float f = 2.0 + fbm(p + vec2(iTime * 5.0, 0.0)) * 0.5;

            for (int i = 0; i < 35; i++) {
                float i_f = float(i);
                v = p + cos(vec2(i_f * i_f + (iTime + p.x * 0.08) * 0.025) + i_f * vec2(13.0, 11.0)) * 3.5 + vec2(sin(iTime * 3.0 + i_f) * 0.003, cos(iTime * 3.5 - i_f) * 0.003);
                float tailNoise = fbm(v + vec2(iTime * 0.5, i_f)) * 0.3 * (1.0 - (i_f / 35.0));
                vec4 auroraColors = vec4(
                    0.1 + 0.3 * sin(i_f * 0.2 + iTime * 0.4),
                    0.3 + 0.5 * cos(i_f * 0.3 + iTime * 0.5),
                    0.7 + 0.3 * sin(i_f * 0.4 + iTime * 0.3),
                    1.0
                );
                vec4 currentContribution = auroraColors * exp(sin(i_f * i_f + iTime * 0.8)) / length(max(v, vec2(v.x * f * 0.015, v.y * 1.5)));
                float thinnessFactor = smoothstep(0.0, 1.0, i_f / 35.0) * 0.6;
                o += currentContribution * (1.0 + tailNoise * 0.8) * thinnessFactor;
            }

            o = my_tanh(pow(o / 100.0, vec4(1.6)));
            gl_FragColor = o * 1.5;
        }
    `;

    function compile(type, src) {
        const s = gl.createShader(type);
        gl.shaderSource(s, src);
        gl.compileShader(s);
        if (!gl.getShaderParameter(s, gl.COMPILE_STATUS)) {
            console.error("Shader Compile Status Error: ", gl.getShaderInfoLog(s));
        }
        return s;
    }

    const prog = gl.createProgram();
    gl.attachShader(prog, compile(gl.VERTEX_SHADER, VS));
    gl.attachShader(prog, compile(gl.FRAGMENT_SHADER, FS));
    gl.linkProgram(prog);
    if (!gl.getProgramParameter(prog, gl.LINK_STATUS)) {
        console.error("Shader Link Program Status Error: ", gl.getProgramInfoLog(prog));
    }
    gl.useProgram(prog);

    const buf = gl.createBuffer();
    gl.bindBuffer(gl.ARRAY_BUFFER, buf);
    gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([-1,-1,3,-1,-1,3]), gl.STATIC_DRAW);
    
    const locP = gl.getAttribLocation(prog, 'p');
    gl.enableVertexAttribArray(locP);
    gl.vertexAttribPointer(locP, 2, gl.FLOAT, false, 0, 0);

    const locTime = gl.getUniformLocation(prog, 'iTime');
    const locRes = gl.getUniformLocation(prog, 'iResolution');

    let time = 0;
    let last = performance.now();
    let animId;

    function frame(now) {
        const dt = Math.min(0.05, (now - last) / 1000);
        last = now;
        time += dt;

        const w = canvas.clientWidth, h = canvas.clientHeight;
        if (canvas.width !== w || canvas.height !== h) {
            canvas.width = w;
            canvas.height = h;
            gl.viewport(0, 0, w, h);
        }

        gl.uniform1f(locTime, time);
        gl.uniform2f(locRes, canvas.width, canvas.height);
        gl.drawArrays(gl.TRIANGLES, 0, 3);

        animId = requestAnimationFrame(frame);
    }
    animId = requestAnimationFrame(frame);

    wrap._cleanup = () => {
        cancelAnimationFrame(animId);
    };
}
```

---

## Effect #5: 3D Stellar Starfield
*A custom HTML5 WebGL canvas displaying a 3D projected perspective starfield revolving around multiple axes, complete with OrbitControls, concentric spheres, and rotating interactive invite cards.*

### HTML
```html
<div class="bg-effect-5" id="stellar-wrap-5">
    <canvas class="stellar-canvas" id="stellar-canvas-5"></canvas>
    <div class="card-galaxy-container" id="card-galaxy-container-5"></div>
    <div class="cosmic-text-overlay">
        <h2>3D Stellar Card Galaxy</h2>
        <p>Drag to rotate • Scroll to zoom</p>
    </div>
    <div class="bg-title-overlay">Stellar Galaxy</div>
</div>
```

### CSS
```css
.bg-effect-5 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #020205;
}
.bg-effect-5 .stellar-canvas {
    display: block;
    width: 100%;
    height: 100%;
}
.bg-effect-5 .card-galaxy-container {
    position: absolute;
    inset: 0;
    z-index: 2;
    pointer-events: none;
    perspective: 800px;
}
.bg-effect-5 .stellar-card {
    position: absolute;
    width: 70px;
    height: 90px;
    background: #1F2121;
    border-radius: 8px;
    padding: 4px;
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    transition: box-shadow 0.3s ease, border 0.3s ease, transform 0.1s ease;
    cursor: pointer;
    pointer-events: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    transform-origin: center center;
}
.bg-effect-5 .stellar-card:hover {
    box-shadow: 0 10px 20px rgba(49, 184, 198, 0.6), 0 0 12px rgba(49, 184, 198, 0.3);
    border: 1.5px solid rgba(49, 184, 198, 0.6);
}
.bg-effect-5 .stellar-card img {
    width: 100%;
    height: 60px;
    object-fit: cover;
    border-radius: 4px;
    pointer-events: none;
}
.bg-effect-5 .stellar-card p {
    color: #fff;
    font-size: 7px;
    font-weight: 500;
    margin-top: 3px;
    text-align: center;
    width: 100%;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    pointer-events: none;
}
.bg-effect-5 .cosmic-text-overlay {
    position: absolute;
    top: 20px;
    left: 20px;
    z-index: 3;
    pointer-events: none;
}
.bg-effect-5 .cosmic-text-overlay h2 {
    font-size: 1rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: 2px;
    letter-spacing: 1px;
}
.bg-effect-5 .cosmic-text-overlay p {
    font-size: 0.65rem;
    color: rgba(255, 255, 255, 0.6);
}
```

### JavaScript
```javascript
function initStellarStarfield() {
    const wrap = document.getElementById('stellar-wrap-5');
    if (!wrap) return;
    const canvas = document.getElementById('stellar-canvas-5');
    if (!canvas) return;
    const galaxyContainer = document.getElementById('card-galaxy-container-5');
    if (!galaxyContainer) return;

    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(60, wrap.clientWidth / wrap.clientHeight, 0.1, 2000);
    camera.position.set(0, 0, 15);

    const renderer = new THREE.WebGLRenderer({ canvas: canvas, antialias: true, alpha: true });
    renderer.setSize(wrap.clientWidth, wrap.clientHeight);
    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    renderer.setClearColor(0x000000, 1);

    const controls = new THREE.OrbitControls(camera, renderer.domElement);
    controls.enablePan = true;
    controls.enableZoom = true;
    controls.enableRotate = true;
    controls.minDistance = 5;
    controls.maxDistance = 40;
    controls.rotateSpeed = 0.5;
    controls.zoomSpeed = 1.2;
    controls.panSpeed = 0.8;

    const starsGeometry = new THREE.BufferGeometry();
    const starsCount = 10000;
    const positions = new Float32Array(starsCount * 3);
    for (let i = 0; i < starsCount; i++) {
        positions[i * 3] = (Math.random() - 0.5) * 2000;
        positions[i * 3 + 1] = (Math.random() - 0.5) * 2000;
        positions[i * 3 + 2] = (Math.random() - 0.5) * 2000;
    }
    starsGeometry.setAttribute("position", new THREE.BufferAttribute(positions, 3));
    const starsMaterial = new THREE.PointsMaterial({ color: 0xffffff, size: 0.7, sizeAttenuation: true });
    const stars = new THREE.Points(starsGeometry, starsMaterial);
    scene.add(stars);

    const cardGalaxyGroup = new THREE.Group();
    scene.add(cardGalaxyGroup);

    const sphereMat = (opacity) => new THREE.MeshBasicMaterial({ color: 0x31b8c6, wireframe: true, transparent: true, opacity });
    const sp1 = new THREE.Mesh(new THREE.SphereGeometry(2, 24, 24), new THREE.MeshBasicMaterial({ color: 0x1a1a2e, wireframe: true, transparent: true, opacity: 0.15 }));
    const sp2 = new THREE.Mesh(new THREE.SphereGeometry(12, 32, 32), sphereMat(0.05));
    const sp3 = new THREE.Mesh(new THREE.SphereGeometry(16, 32, 32), sphereMat(0.03));
    const sp4 = new THREE.Mesh(new THREE.SphereGeometry(20, 32, 32), sphereMat(0.02));
    cardGalaxyGroup.add(sp1, sp2, sp3, sp4);

    const cards = [
        { id: "1", imageUrl: "https://i.ibb.co/4ZWcP129/1.png", alt: "Elegant Invitation", title: "Elegant Invitation" },
        { id: "2", imageUrl: "https://i.ibb.co/TMbhBRcL/2.png", alt: "Modern Design", title: "Modern Design" },
        { id: "3", imageUrl: "https://i.ibb.co/spXBFdSm/3.png", alt: "Vintage Style", title: "Vintage Style" },
        { id: "4", imageUrl: "https://i.ibb.co/N2TCN0bC/4.png", alt: "Minimalist", title: "Minimalist" },
        { id: "5", imageUrl: "https://i.ibb.co/jZkh6q1M/5.png", alt: "Floral Design", title: "Floral Design" },
        { id: "6", imageUrl: "https://i.ibb.co/6cc7mksr/6.png", alt: "Geometric", title: "Geometric" },
        { id: "7", imageUrl: "https://i.ibb.co/bjV35jNQ/7.png", alt: "Luxury Gold", title: "Luxury Gold" },
        { id: "8", imageUrl: "https://i.ibb.co/PZ7WLs7g/8.png", alt: "Rustic Style", title: "Rustic Style" },
        { id: "9", imageUrl: "https://i.ibb.co/qLR5bQRM/9.png", alt: "Dark Modern", title: "Dark Modern" },
        { id: "10", imageUrl: "https://i.ibb.co/PdNhw3K/10.png", alt: "Colorful Party", title: "Colorful Party" },
        { id: "11", imageUrl: "https://i.ibb.co/zWpN1nqJ/11.png", alt: "Geometric", title: "Geometric" },
        { id: "12", imageUrl: "https://i.ibb.co/fVYnCXgR/12.png", alt: "Luxury Gold", title: "Luxury Gold" },
        { id: "13", imageUrl: "https://i.ibb.co/1G6jZWcZ/13.png", alt: "Rustic Style", title: "Rustic Style" },
        { id: "14", imageUrl: "https://i.ibb.co/xKG7m905/14.png", alt: "Dark Modern", title: "Dark Modern" },
        { id: "15", imageUrl: "https://i.ibb.co/7dJzR3xK/15.png", alt: "Colorful Party", title: "Colorful Party" },
        { id: "16", imageUrl: "https://i.ibb.co/NdJ1csXB/16.png", alt: "Elegant Script", title: "Elegant Script" },
        { id: "17", imageUrl: "https://i.ibb.co/8L2Sdt5Q/17.png", alt: "Watercolor Art", title: "Watercolor Art" },
        { id: "18", imageUrl: "https://i.ibb.co/mC1zxJYq/18.png", alt: "Botanical", title: "Botanical" },
        { id: "19", imageUrl: "https://i.ibb.co/wryzsKs4/20.png", alt: "Art Deco", title: "Art Deco" },
        { id: "20", imageUrl: "https://i.ibb.co/1fvnxL3L/19.png", alt: "Marble Luxury", title: "Marble Luxury" }
    ];

    const dummyObjects = [];
    const cardDivs = [];
    const numCards = cards.length;
    const goldenRatio = (1 + Math.sqrt(5)) / 2;

    for (let i = 0; i < numCards; i++) {
        const y = 1 - (i / (numCards - 1)) * 2;
        const radiusAtY = Math.sqrt(1 - y * y);
        const theta = (2 * Math.PI * i) / goldenRatio;
        const x = Math.cos(theta) * radiusAtY;
        const z = Math.sin(theta) * radiusAtY;
        const layerRadius = 12 + (i % 3) * 4;

        const dummy = new THREE.Object3D();
        dummy.position.set(x * layerRadius, y * layerRadius, z * layerRadius);
        cardGalaxyGroup.add(dummy);
        dummyObjects.push(dummy);

        const cardDiv = document.createElement('div');
        cardDiv.className = 'stellar-card';
        cardDiv.innerHTML = `
            <img src="${cards[i].imageUrl}" alt="${cards[i].alt}">
            <p>${cards[i].title}</p>
        `;
        cardDiv.addEventListener('click', (e) => {
            e.stopPropagation();
            openStellarModal(cards[i]);
        });
        galaxyContainer.appendChild(cardDiv);
        cardDivs.push(cardDiv);
    }

    const resize = () => {
        const w = wrap.clientWidth, h = wrap.clientHeight;
        camera.aspect = w / h;
        camera.updateProjectionMatrix();
        renderer.setSize(w, h);
    };
    resize();
    window.addEventListener('resize', resize);

    const THREE_TEMP_VEC = new THREE.Vector3();
    let animId;
    const animate = () => {
        animId = requestAnimationFrame(animate);
        stars.rotation.y += 0.0001;
        stars.rotation.x += 0.00005;
        cardGalaxyGroup.rotation.y += 0.002;
        controls.update();
        renderer.render(scene, camera);

        dummyObjects.forEach((dummy, i) => {
            dummy.getWorldPosition(THREE_TEMP_VEC);
            THREE_TEMP_VEC.project(camera);
            if (THREE_TEMP_VEC.z > 1 || THREE_TEMP_VEC.z < -1) {
                cardDivs[i].style.display = 'none';
            } else {
                cardDivs[i].style.display = 'flex';
                const px = (THREE_TEMP_VEC.x * 0.5 + 0.5) * wrap.clientWidth;
                const py = (-(THREE_TEMP_VEC.y * 0.5) + 0.5) * wrap.clientHeight;
                
                dummy.getWorldPosition(THREE_TEMP_VEC);
                const dist = camera.position.distanceTo(THREE_TEMP_VEC);
                const scale = 15 / dist;
                
                cardDivs[i].style.left = `${px}px`;
                cardDivs[i].style.top = `${py}px`;
                cardDivs[i].style.transform = `translate(-50%, -50%) scale(${scale * 0.75})`;
                cardDivs[i].style.zIndex = Math.floor(1000 - dist * 10);
                cardDivs[i].style.opacity = Math.max(0.15, Math.min(1.0, (30 - dist) / 20));
            }
        });
    };
    animate();

    wrap._cleanup = () => {
        cancelAnimationFrame(animId);
        window.removeEventListener('resize', resize);
        controls.dispose();
        starsGeometry.dispose();
        starsMaterial.dispose();
        renderer.dispose();
    };
}
```

---

## Effect #6: 3D Neon GLSL Hills
*A WebGL wireframe plane rendered via Three.js and deformed by a vertex shader executing a raw cnoise (classic Perlin noise) algorithm to simulate scrolling hills.*

### HTML
```html
<div class="bg-effect-6" id="hills-wrap-6">
    <canvas class="hills-canvas" id="hills-canvas-6"></canvas>
    <div class="bg-title-overlay">GLSL Hills</div>
</div>
```

### CSS
```css
.bg-effect-6 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #030307;
}
.bg-effect-6 .hills-canvas {
    display: block;
    width: 100%;
    height: 100%;
}
```

### JavaScript
```javascript
function initGLSLHills() {
    const wrap = document.getElementById('hills-wrap-6');
    if (!wrap) return;
    const canvas = document.getElementById('hills-canvas-6');
    if (!canvas) return;

    const renderer = new THREE.WebGLRenderer({ canvas: canvas, antialias: false });
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(45, canvas.clientWidth / canvas.clientHeight, 1, 1000);
    
    const uniforms = {
        time: { type: 'f', value: 0 }
    };

    const vertexShader = `
        attribute vec3 position;
        uniform mat4 projectionMatrix;
        uniform mat4 modelViewMatrix;
        uniform float time;
        varying vec3 vPosition;

        mat4 rotateMatrixX(float radian) {
            return mat4(
                1.0, 0.0, 0.0, 0.0,
                0.0, cos(radian), -sin(radian), 0.0,
                0.0, sin(radian), cos(radian), 0.0,
                0.0, 0.0, 0.0, 1.0
            );
        }

        vec3 mod289(vec3 x) { return x - floor(x * (1.0 / 289.0)) * 289.0; }
        vec4 mod289(vec4 x) { return x - floor(x * (1.0 / 289.0)) * 289.0; }
        vec4 permute(vec4 x) { return mod289(((x*34.0)+1.0)*x); }
        vec4 taylorInvSqrt(vec4 r) { return 1.79284291400159 - 0.85373472095314 * r; }
        vec3 fade(vec3 t) { return t*t*t*(t*(t*6.0-15.0)+10.0); }

        float cnoise(vec3 P) {
            vec3 Pi0 = floor(P);
            vec3 Pi1 = Pi0 + vec3(1.0);
            Pi0 = mod289(Pi0);
            Pi1 = mod289(Pi1);
            vec3 Pf0 = fract(P);
            vec3 Pf1 = Pf0 - vec3(1.0);
            vec4 ix = vec4(Pi0.x, Pi1.x, Pi0.x, Pi1.x);
            vec4 iy = vec4(Pi0.yy, Pi1.yy);
            vec4 iz0 = Pi0.zzzz;
            vec4 iz1 = Pi1.zzzz;

            vec4 ixy = permute(permute(ix) + iy);
            vec4 ixy0 = permute(ixy + iz0);
            vec4 ixy1 = permute(ixy + iz1);

            vec4 gx0 = ixy0 * (1.0 / 7.0);
            vec4 gy0 = fract(floor(gx0) * (1.0 / 7.0)) - 0.5;
            gx0 = fract(gx0);
            vec4 gz0 = vec4(0.5) - abs(gx0) - abs(gy0);
            vec4 sz0 = step(gz0, vec4(0.0));
            gx0 -= sz0 * (step(0.0, gx0) - 0.5);
            gy0 -= sz0 * (step(0.0, gy0) - 0.5);

            vec4 gx1 = ixy1 * (1.0 / 7.0);
            vec4 gy1 = fract(floor(gx1) * (1.0 / 7.0)) - 0.5;
            gx1 = fract(gx1);
            vec4 gz1 = vec4(0.5) - abs(gx1) - abs(gy1);
            vec4 sz1 = step(gz1, vec4(0.0));
            gx1 -= sz1 * (step(0.0, gx1) - 0.5);
            gy1 -= sz1 * (step(0.0, gy1) - 0.5);

            vec3 g000 = vec3(gx0.x,gy0.x,gz0.x);
            vec3 g100 = vec3(gx0.y,gy0.y,gz0.y);
            vec3 g010 = vec3(gx0.z,gy0.z,gz0.z);
            vec3 g110 = vec3(gx0.w,gy0.w,gz0.w);
            vec3 g001 = vec3(gx1.x,gy1.x,gz1.x);
            vec3 g101 = vec3(gx1.y,gy1.y,gz1.y);
            vec3 g011 = vec3(gx1.z,gy1.z,gz1.z);
            vec3 g111 = vec3(gx1.w,gy1.w,gz1.w);

            vec4 norm0 = taylorInvSqrt(vec4(dot(g000, g000), dot(g010, g010), dot(g100, g100), dot(g110, g110)));
            g000 *= norm0.x;
            g010 *= norm0.y;
            g100 *= norm0.z;
            g110 *= norm0.w;
            vec4 norm1 = taylorInvSqrt(vec4(dot(g001, g001), dot(g011, g011), dot(g101, g101), dot(g111, g111)));
            g001 *= norm1.x;
            g011 *= norm1.y;
            g101 *= norm1.z;
            g111 *= norm1.w;

            float n000 = dot(g000, Pf0);
            float n100 = dot(g100, vec3(Pf1.x, Pf0.yz));
            float n010 = dot(g010, vec3(Pf0.x, Pf1.y, Pf0.z));
            float n110 = dot(g110, vec3(Pf1.xy, Pf0.z));
            float n001 = dot(g001, vec3(Pf0.xy, Pf1.z));
            float n101 = dot(g101, vec3(Pf1.x, Pf0.y, Pf1.z));
            float n011 = dot(g011, vec3(Pf0.x, Pf1.yz));
            float n111 = dot(g111, Pf1);

            vec3 fade_xyz = fade(Pf0);
            vec4 n_z = mix(vec4(n000, n100, n010, n110), vec4(n001, n101, n011, n111), fade_xyz.z);
            vec2 n_yz = mix(n_z.xy, n_z.zw, fade_xyz.y);
            float n_xyz = mix(n_yz.x, n_yz.y, fade_xyz.x);
            return 2.2 * n_xyz;
        }

        void main(void) {
            vec3 updatePosition = (rotateMatrixX(radians(90.0)) * vec4(position, 1.0)).xyz;
            float sin1 = sin(radians(updatePosition.x / 128.0 * 90.0));
            vec3 noisePosition = updatePosition + vec3(0.0, 0.0, time * -30.0);
            float noise1 = cnoise(noisePosition * 0.08);
            float noise2 = cnoise(noisePosition * 0.06);
            float noise3 = cnoise(noisePosition * 0.4);
            vec3 lastPosition = updatePosition + vec3(0.0,
                noise1 * sin1 * 8.0
                + noise2 * sin1 * 8.0
                + noise3 * (abs(sin1) * 2.0 + 0.5)
                + pow(sin1, 2.0) * 40.0, 0.0);

            vPosition = lastPosition;
            gl_Position = projectionMatrix * modelViewMatrix * vec4(lastPosition, 1.0);
        }
    `;

    const fragmentShader = `
        precision highp float;
        varying vec3 vPosition;

        void main(void) {
            float opacity = (96.0 - length(vPosition)) / 256.0 * 0.6;
            vec3 color = vec3(0.6);
            gl_FragColor = vec4(color, opacity);
        }
    `;

    const geometry = new THREE.PlaneGeometry(256, 256, 256, 256);
    const material = new THREE.RawShaderMaterial({
        uniforms: uniforms,
        vertexShader: vertexShader,
        fragmentShader: fragmentShader,
        transparent: true,
        wireframe: true
    });

    const mesh = new THREE.Mesh(geometry, material);
    scene.add(mesh);

    renderer.setSize(canvas.clientWidth, canvas.clientHeight);
    renderer.setClearColor(0x030307, 1);

    camera.position.set(0, 16, 125);
    camera.lookAt(new THREE.Vector3(0, 28, 0));

    const resize = () => {
        const w = wrap.clientWidth, h = wrap.clientHeight;
        camera.aspect = w / h;
        camera.updateProjectionMatrix();
        renderer.setSize(w, h);
    };
    resize();
    window.addEventListener('resize', resize);

    let animId;
    let lastTime = performance.now();
    function loop() {
        const now = performance.now();
        const dt = (now - lastTime) / 1000;
        lastTime = now;

        uniforms.time.value += dt * 0.5;
        renderer.render(scene, camera);
        animId = requestAnimationFrame(loop);
    }
    loop();

    wrap._cleanup = () => {
        cancelAnimationFrame(animId);
        window.removeEventListener('resize', resize);
        geometry.dispose();
        material.dispose();
        renderer.dispose();
    };
}
```

---

## Effect #7: Dark Linear Gradient Streaks
*A sleek, dark overlay using complex CSS radial mask filters, diagonal skewed streaks, and micro-grid textures to achieve a premium UI background.*

### HTML
```html
<div class="bg-effect-7">
    <div class="gradient-base">
        <div class="streak streak-1"></div>
        <div class="streak streak-2"></div>
        <div class="streak streak-3"></div>
        <div class="streak streak-4"></div>
        <div class="streak streak-5"></div>
    </div>
    <div class="grain-overlay"></div>
    <div class="dot-grid"></div>
    <div class="bg-title-overlay">Gradient Streaks</div>
</div>
```

### CSS
```css
.bg-effect-7 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #000;
}
.bg-effect-7 .gradient-base {
    position: absolute;
    inset: 0;
    background: radial-gradient(100% 100% at 0% 0%, #2e2e2e 0%, #000 100%);
    mask-image: radial-gradient(125% 100% at 0% 0%, #000 0%, rgba(0,0,0,0.22) 88%, transparent 100%);
    -webkit-mask-image: radial-gradient(125% 100% at 0% 0%, #000 0%, rgba(0,0,0,0.22) 88%, transparent 100%);
}
.bg-effect-7 .streak {
    position: absolute;
    inset: 0;
    opacity: 0.2;
    background: linear-gradient(180deg, #00cfff 0%, rgba(0,207,255,0) 100%);
    transform: skewX(45deg);
}
.bg-effect-7 .streak-1 {
    mask-image: linear-gradient(90deg, transparent 0%, #000 20%, transparent 36%, #000 55%, rgba(0,0,0,0.13) 67%, #000 78%, transparent 97%);
    -webkit-mask-image: linear-gradient(90deg, transparent 0%, #000 20%, transparent 36%, #000 55%, rgba(0,0,0,0.13) 67%, #000 78%, transparent 97%);
}
.bg-effect-7 .streak-2 {
    mask-image: linear-gradient(90deg, transparent 11%, #000 25%, rgba(0,0,0,0.55) 41%, rgba(0,0,0,0.13) 67%, #000 78%, transparent 97%);
    -webkit-mask-image: linear-gradient(90deg, transparent 11%, #000 25%, rgba(0,0,0,0.55) 41%, rgba(0,0,0,0.13) 67%, #000 78%, transparent 97%);
}
.bg-effect-7 .streak-3 {
    mask-image: linear-gradient(90deg, transparent 9%, #000 20%, rgba(0,0,0,0.55) 28%, rgba(0,0,0,0.42) 40%, #000 48%, rgba(0,0,0,0.26) 54%, rgba(0,0,0,0.13) 78%, #000 88%, transparent 97%);
    -webkit-mask-image: linear-gradient(90deg, transparent 9%, #000 20%, rgba(0,0,0,0.55) 28%, rgba(0,0,0,0.42) 40%, #000 48%, rgba(0,0,0,0.26) 54%, rgba(0,0,0,0.13) 78%, #000 88%, transparent 97%);
}
.bg-effect-7 .streak-4 {
    mask-image: linear-gradient(90deg, transparent 0%, #000 17%, rgba(0,0,0,0.55) 26%, #000 35%, transparent 47%, rgba(0,0,0,0.13) 69%, #000 79%, transparent 97%);
    -webkit-mask-image: linear-gradient(90deg, transparent 0%, #000 17%, rgba(0,0,0,0.55) 26%, #000 35%, transparent 47%, rgba(0,0,0,0.13) 69%, #000 79%, transparent 97%);
}
.bg-effect-7 .streak-5 {
    mask-image: linear-gradient(90deg, transparent 0%, #000 20%, rgba(0,0,0,0.55) 27%, #000 42%, transparent 48%, rgba(0,0,0,0.13) 67%, #000 74%, #000 82%, rgba(0,0,0,0.47) 88%, transparent 97%);
    -webkit-mask-image: linear-gradient(90deg, transparent 0%, #000 20%, rgba(0,0,0,0.55) 27%, #000 42%, transparent 48%, rgba(0,0,0,0.13) 67%, #000 74%, #000 82%, rgba(0,0,0,0.47) 88%, transparent 97%);
}
.bg-effect-7 .grain-overlay {
    position: absolute;
    inset: 0;
    opacity: 0.04;
    background-image: url("https://framerusercontent.com/images/6mcf62RlDfRfU61Yg5vb2pefpi4.png");
    background-size: 150px;
}
.bg-effect-7 .dot-grid {
    position: absolute;
    inset: 0;
    opacity: 0.15;
    background-image: radial-gradient(circle at 1px 1px, rgba(255,255,255,0.4) 1px, transparent 0);
    background-size: 20px 20px;
}
```

---

## Effect #8: Interactive Neural Vortex
*A highly complex WebGL fragment shader calculating fluid vortex simulations that interactively react and shift focus towards the mouse cursor's viewport position, layered under a futuristic hero overlay.*

### HTML
```html
<div class="bg-effect-8" id="vortex-wrap-8">
    <canvas class="vortex-canvas" id="vortex-canvas-8"></canvas>
    <div class="hero-overlay-8">
        <div class="hero-content-8">
            <h2 class="hero-h1-8">Step Into the Future of VR</h2>
            <p class="hero-h2-8">ImmersiaVR delivers breathtaking realism, seamless interaction, and endless possibilities.</p>
            <a href="#" class="hero-btn-8">Get Started</a>
        </div>
    </div>
    <div class="bg-title-overlay">Neural Vortex</div>
</div>
```

### CSS
```css
.bg-effect-8 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #020108;
}
.bg-effect-8 .vortex-canvas {
    display: block;
    width: 100%;
    height: 100%;
}
.bg-effect-8 .hero-overlay-8 {
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2;
    pointer-events: none;
    padding: 1.5rem;
}
.bg-effect-8 .hero-content-8 {
    max-width: 90%;
    text-align: center;
    pointer-events: auto;
    border: 1px solid rgba(255, 255, 255, 0.1);
    background: rgba(8, 11, 17, 0.45);
    backdrop-filter: blur(8px);
    padding: 1.5rem;
    border-radius: 16px;
}
.bg-effect-8 .hero-h1-8 {
    font-size: 1.25rem;
    font-weight: 600;
    color: #fff;
    margin-bottom: 0.5rem;
    line-height: 1.2;
}
.bg-effect-8 .hero-h2-8 {
    font-size: 0.8rem;
    color: rgba(255, 255, 255, 0.6);
    margin-bottom: 1rem;
    line-height: 1.4;
}
.bg-effect-8 .hero-btn-8 {
    display: inline-block;
    font-size: 0.8rem;
    font-weight: 600;
    color: #fff;
    border: 1.5px solid rgba(255, 255, 255, 0.15);
    padding: 6px 16px;
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.3s ease;
}
.bg-effect-8 .hero-btn-8:hover {
    background: rgba(255, 255, 255, 0.1);
    border-color: rgba(255, 255, 255, 0.3);
}
```

### JavaScript
```javascript
function initNeuralVortex() {
    const wrap = document.getElementById('vortex-wrap-8');
    if (!wrap) return;
    const canvas = document.getElementById('vortex-canvas-8');
    if (!canvas) return;

    const gl = canvas.getContext('webgl');
    if (!gl) return;

    const VS = `
        precision mediump float;
        attribute vec2 a_position;
        varying vec2 vUv;
        void main() {
            vUv = .5 * (a_position + 1.);
            gl_Position = vec4(a_position, 0.0, 1.0);
        }
    `;

    const FS = `
        precision mediump float;
        varying vec2 vUv;
        uniform float u_time;
        uniform float u_ratio;
        uniform vec2 u_pointer_position;
        uniform float u_scroll_progress;
        
        vec2 rotate(vec2 uv, float th) {
            return mat2(cos(th), sin(th), -sin(th), cos(th)) * uv;
        }
        
        float neuro_shape(vec2 uv, float t, float p) {
            vec2 sine_acc = vec2(0.);
            vec2 res = vec2(0.);
            float scale = 8.;
            for (int j = 0; j < 15; j++) {
                uv = rotate(uv, 1.);
                sine_acc = rotate(sine_acc, 1.);
                vec2 layer = uv * scale + float(j) + sine_acc - t;
                sine_acc += sin(layer) + 2.4 * p;
                res += (.5 + .5 * cos(layer)) / scale;
                scale *= (1.2);
            }
            return res.x + res.y;
        }
        
        void main() {
            vec2 uv = .5 * vUv;
            uv.x *= u_ratio;
            vec2 pointer = vUv - u_pointer_position;
            pointer.x *= u_ratio;
            float p = clamp(length(pointer), 0., 1.);
            p = .5 * pow(1. - p, 2.);
            float t = .001 * u_time;
            vec3 color = vec3(0.);
            float noise = neuro_shape(uv, t, p);
            noise = 1.2 * pow(noise, 3.);
            noise += pow(noise, 10.);
            noise = max(.0, noise - .5);
            noise *= (1. - length(vUv - .5));
            color = vec3(0.5, 0.15, 0.65);
            color = mix(color, vec3(0.02, 0.7, 0.9), 0.32 + 0.16 * sin(2.0 * u_scroll_progress + 1.2));
            color += vec3(0.15, 0.0, 0.6) * sin(2.0 * u_scroll_progress + 1.5);
            color = color * noise;
            gl_FragColor = vec4(color, noise);
        }
    `;

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

    const vertices = new Float32Array([-1, -1, 1, -1, -1, 1, 1, 1]);
    const buf = gl.createBuffer();
    gl.bindBuffer(gl.ARRAY_BUFFER, buf);
    gl.bufferData(gl.ARRAY_BUFFER, vertices, gl.STATIC_DRAW);

    const locP = gl.getAttribLocation(prog, 'a_position');
    gl.enableVertexAttribArray(locP);
    gl.vertexAttribPointer(locP, 2, gl.FLOAT, false, 0, 0);

    const uTime = gl.getUniformLocation(prog, 'u_time');
    const uRatio = gl.getUniformLocation(prog, 'u_ratio');
    const uPointerPosition = gl.getUniformLocation(prog, 'u_pointer_position');
    const uScrollProgress = gl.getUniformLocation(prog, 'u_scroll_progress');

    let pointerX = wrap.clientWidth / 2, pointerY = wrap.clientHeight / 2;
    let targetX = pointerX, targetY = pointerY;

    const resize = () => {
        canvas.width = wrap.clientWidth;
        canvas.height = wrap.clientHeight;
        gl.viewport(0, 0, canvas.width, canvas.height);
        gl.uniform1f(uRatio, canvas.width / canvas.height);
    };
    resize();
    window.addEventListener('resize', resize);

    const mousemove = (e) => {
        const rect = wrap.getBoundingClientRect();
        targetX = e.clientX - rect.left;
        targetY = e.clientY - rect.top;
    };
    wrap.addEventListener('mousemove', mousemove);

    let animId;
    function loop() {
        const currentTime = performance.now();
        pointerX += (targetX - pointerX) * 0.1;
        pointerY += (targetY - pointerY) * 0.1;

        gl.uniform1f(uTime, currentTime);
        gl.uniform2f(uPointerPosition, pointerX / wrap.clientWidth, 1.0 - (pointerY / wrap.clientHeight));
        gl.uniform1f(uScrollProgress, window.pageYOffset / (2 * window.innerHeight));
        gl.drawArrays(gl.TRIANGLE_STRIP, 0, 4);

        animId = requestAnimationFrame(loop);
    }
    loop();

    wrap._cleanup = () => {
        cancelAnimationFrame(animId);
        window.removeEventListener('resize', resize);
        wrap.removeEventListener('mousemove', mousemove);
        gl.deleteProgram(prog);
    };
}
```

---

## Effect #9: Animated Digital Streams
*Matrix-like dropping columns of glowing digital data beams animated over a sci-fi perspective grid floor and a center glow column.*

### HTML
```html
<div class="bg-effect-9" id="streams-wrap-9">
    <div class="floor"></div>
    <div class="main-column"></div>
    <div class="light-stream-container"></div>
    <div class="bg-title-overlay">Digital Streams</div>
</div>
```

### CSS
```css
.bg-effect-9 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #020204;
}
.bg-effect-9 .floor {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 50%;
    background-image: 
        linear-gradient(rgba(49, 184, 198, 0.08) 1px, transparent 1px),
        linear-gradient(90deg, rgba(49, 184, 198, 0.08) 1px, transparent 1px);
    background-size: 20px 20px;
    background-position: center;
    transform: perspective(150px) rotateX(60deg);
    transform-origin: bottom center;
    z-index: 1;
    opacity: 0.8;
    pointer-events: none;
}
.bg-effect-9 .main-column {
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 4px;
    transform: translateX(-50%);
    background: linear-gradient(to bottom, transparent, rgba(49, 184, 198, 0.3) 20%, rgba(49, 184, 198, 0.6) 50%, rgba(49, 184, 198, 0.3) 80%, transparent);
    box-shadow: 0 0 15px rgba(49, 184, 198, 0.4);
    z-index: 2;
    pointer-events: none;
}
.bg-effect-9 .light-stream-container {
    position: absolute;
    inset: 0;
    z-index: 3;
}
.bg-effect-9 .light-beam {
    position: absolute;
    top: -100px;
    height: 80px;
    background: linear-gradient(to bottom, transparent, #31b8c6);
    opacity: 0;
    animation-name: stream-drop-9, stream-fade-9;
    animation-timing-function: linear, ease-in-out;
    animation-iteration-count: infinite;
}
@keyframes stream-drop-9 {
    0% { transform: translateY(0); }
    100% { transform: translateY(450px); }
}
@keyframes stream-fade-9 {
    0% { opacity: 0; }
    30% { opacity: 0.65; }
    70% { opacity: 0.65; }
    100% { opacity: 0; }
}
```

### JavaScript
```javascript
function initDigitalStreams() {
    const wrap = document.getElementById('streams-wrap-9');
    if (!wrap) return;
    const container = wrap.querySelector('.light-stream-container');
    if (!container) return;

    container.innerHTML = '';
    const count = 60;
    for (let i = 0; i < count; i++) {
        const beam = document.createElement('div');
        beam.className = 'light-beam';
        beam.style.left = `${Math.random() * 100}%`;
        beam.style.width = `${Math.floor(Math.random() * 3) + 1}px`;
        
        const riseDur = Math.random() * 2 + 4;
        const fadeDur = riseDur;
        const dropDur = Math.random() * 3 + 3;
        
        beam.style.animationDuration = `${dropDur}s, ${fadeDur}s`;
        beam.style.animationDelay = `${Math.random() * 5}s`;
        
        container.appendChild(beam);
    }
}
```

---

## Effect #10: Nexbot 3D Spline Robot
*An interactive 3D Nexbot robot concept rendered using Spline's real-time WebGL engine.*

### HTML
```html
<div class="spline-container">
    <iframe src="https://my.spline.design/nexbotrobotcharacterconcept-kLwr8f6hgKgaa5gmU6oB00Si" frameborder="0" width="100%" height="100%" id="aura-spline"></iframe>
</div>
```

### CSS
```css
.spline-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -10;
}
```

### JavaScript
No JavaScript dependency required for iframe embed.

---

## Effect #11: Unicorn Studio Fluid Shader
*A premium fluid motion shader effect powered by Unicorn Studio WebGL runtime.*

### HTML
```html
<div class="aura-background-component top-0 w-full h-screen -z-10 fixed" data-alpha-mask="47"
  style="mask-image: linear-gradient(to bottom, transparent, black 0%, black 47%, transparent); -webkit-mask-image: linear-gradient(to bottom, transparent, black 0%, black 47%, transparent)">
  <div data-us-project="3eLGLP7pmQS4ozfklmrX" class="absolute top-0 left-0 -z-10 w-full h-full"></div>
  <script type="text/javascript">
    !function(){if(!window.UnicornStudio){window.UnicornStudio={isInitialized:!1};var i=document.createElement("script");i.src="https://cdn.jsdelivr.net/gh/hiunicornstudio/unicornstudio.js@v1.4.29/dist/unicornStudio.umd.js",i.onload=function(){window.UnicornStudio.isInitialized||(UnicornStudio.init(),window.UnicornStudio.isInitialized=!0)},(document.head || document.body).appendChild(i)}}();
  </script>
</div>
```

### CSS
No custom CSS required; uses Tailwind utility classes and inline masking styles.

### JavaScript
No additional custom JavaScript required. Init is executed on load via the inline CDN script snippet.

---

## Effect #12: Unicorn Studio Cyber Shader
*An interactive space/mesh grid shader powered by Unicorn Studio.*

### HTML
```html
<div data-us-project="bmaMERjX2VZDtPrh4Zwx" class="absolute w-full h-full left-0 top-0 -z-10"></div>
<script type="text/javascript">
  !function(){if(!window.UnicornStudio){window.UnicornStudio={isInitialized:!1};var i=document.createElement("script");i.src="https://cdn.jsdelivr.net/gh/hiunicornstudio/unicornstudio.js@v1.4.34/dist/unicornStudio.umd.js",i.onload=function(){window.UnicornStudio.isInitialized||(UnicornStudio.init(),window.UnicornStudio.isInitialized=!0)},(document.head || document.body).appendChild(i)}}();
</script>
```

### CSS
No custom CSS required; uses Tailwind utility classes.

### JavaScript
Init is executed automatically on script load via the inline snippet.

---

## Effect #13: WebGL Cyber Glowing Trails
*A high-performance WebGL glow shader featuring moving digital trails and neon nodes, designed with Three.js postprocessing and UnrealBloom.*

### HTML
```html
<!-- Background Image -->
<div class="fixed inset-0 z-0 pointer-events-none">
    <img src="https://hoirqrkdgbmvpwutwuwj.supabase.co/storage/v1/object/public/assets/assets/9aea64b5-bfda-4948-bf88-d4e5d45762fa_3840w.jpg" alt="Background Portrait" class="w-full h-full object-cover object-center opacity-40 mix-blend-luminosity scale-105 transform origin-center transition-transform duration-1000">
    <!-- Gradients to ensure text readability -->
    <div class="absolute inset-0 bg-gradient-to-t from-zinc-950 via-zinc-950/60 to-transparent"></div>
    <div class="absolute inset-0 bg-gradient-to-r from-zinc-950/90 via-zinc-950/40 to-transparent md:w-3/4"></div>
</div>

<!-- Diagonal Texture Overlay -->
<div class="fixed inset-0 z-0 pointer-events-none opacity-[0.03]"
    style="background-image: repeating-linear-gradient(-45deg, #ffffff, #ffffff 1px, transparent 1px, transparent 12px);">
</div>

<!-- WebGL Canvas for Trail Animation -->
<canvas id="webgl-canvas" class="fixed inset-0 z-0 pointer-events-none opacity-70 mix-blend-screen"></canvas>
```

### CSS
No custom CSS required; relies on Tailwind utility styles.

### JavaScript
```javascript
// Add these CDN scripts to your head:
// 1. Three.js: https://unpkg.com/three@0.160.0/build/three.module.js
// 2. Addons imports via importmap or dynamic ESM imports:
import * as THREE from 'three';
import { EffectComposer } from 'three/addons/postprocessing/EffectComposer.js';
import { RenderPass } from 'three/addons/postprocessing/RenderPass.js';
import { UnrealBloomPass } from 'three/addons/postprocessing/UnrealBloomPass.js';
import { ShaderPass } from 'three/addons/postprocessing/ShaderPass.js';
import { SMAAPass } from 'three/addons/postprocessing/SMAAPass.js';
import { OutputPass } from 'three/addons/postprocessing/OutputPass.js';

let scene, camera, renderer, composer, bloomPass, blurPass, smaaPass, outputPass;
let clock = new THREE.Clock();
let globalTime = 0;

let floorMesh;
const trailObjects = [];
const trailMaterials = [];

const config = {
    dpr: Math.min(window.devicePixelRatio, 1.5),
    exposure: 3.6505,
    brightness: 4.0131,
    bloomStrength: 0.2025,
    bloomRadius: 0.294,
    bloomThreshold: 0.0,
    speedMultiplier: 0.1,
    linesCount: 100,
    dotDensity: 70,
    dotSize: 0.25,
    dotSpeed: 1.5,
    blurStrength: 3.5,
    arcRadius: 10.0,
    bendStartZ: -150.0,
    floorLength: 132.75,
    wallHeight: 200.0,
    color0: '#0b101d',
    color1: '#334155',
    color2: '#429DFE',
    color3: '#FF91E3',
    color4: '#1f2937'
};

class CycCurve extends THREE.Curve {
    constructor(x, zStart, zBend, radius, yEnd) {
        super();
        this.x = x;
        this.zStart = zStart;
        this.zBend = zBend;
        this.radius = radius;
        this.yEnd = yEnd;
        
        this.L_flat = Math.abs(zStart - (zBend + radius));
        this.L_arc = (Math.PI * radius) * 0.5;
        this.L_up = Math.max(0.1, yEnd - radius);
        this.totalLength = this.L_flat + this.L_arc + this.L_up;
    }
    
    getPoint(t, optionalTarget = new THREE.Vector3()) {
        const d = t * this.totalLength;
        let py = 0, pz = 0;

        if (d <= this.L_flat) {
            pz = this.zStart - d;
        } else if (d <= this.L_flat + this.L_arc) {
            const norm = (d - this.L_flat) / this.L_arc;
            const eased = norm * norm * (3.0 - 2.0 * norm);
            const angle = (norm * 0.4 + eased * 0.6) * (Math.PI * 0.5);
            py = this.radius * (1.0 - Math.cos(angle));
            pz = (this.zBend + this.radius) - Math.sin(angle) * this.radius;
        } else {
            py = this.radius + (d - (this.L_flat + this.L_arc));
            pz = this.zBend;
        }
        return optionalTarget.set(this.x, py, pz);
    }
}

function init() {
    const canvas = document.querySelector('#webgl-canvas');
    scene = new THREE.Scene();
    scene.background = new THREE.Color(0x000000);

    camera = new THREE.PerspectiveCamera(55, window.innerWidth / window.innerHeight, 1, 2000);
    camera.position.set(0, 20, 140);

    renderer = new THREE.WebGLRenderer({ canvas: canvas, antialias: true, powerPreference: "high-performance" });
    renderer.setSize(window.innerWidth, window.innerHeight);
    renderer.setPixelRatio(config.dpr);
    renderer.toneMapping = THREE.LinearToneMapping;
    renderer.toneMappingExposure = config.exposure;

    camera.lookAt(0, 20, -50);

    const renderTarget = new THREE.WebGLRenderTarget(
        window.innerWidth * config.dpr,
        window.innerHeight * config.dpr,
        {
            type: THREE.HalfFloatType,
            format: THREE.RGBAFormat
        }
    );

    const renderScene = new RenderPass(scene, camera);
    smaaPass = new SMAAPass(window.innerWidth * config.dpr, window.innerHeight * config.dpr);
    bloomPass = new UnrealBloomPass(new THREE.Vector2(window.innerWidth, window.innerHeight), config.bloomStrength, config.bloomRadius, config.bloomThreshold);

    const foregroundBlurShader = {
        uniforms: {
            'tDiffuse': { value: null },
            'resolution': { value: new THREE.Vector2(window.innerWidth * config.dpr, window.innerHeight * config.dpr) },
            'blurStrength': { value: config.blurStrength }
        },
        vertexShader: `
            varying vec2 vUv;
            void main() {
                vUv = uv;
                gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
            }
        `,
        fragmentShader: `
            uniform sampler2D tDiffuse;
            uniform vec2 resolution;
            uniform float blurStrength;
            varying vec2 vUv;
            void main() {
                float mask = 1.0 - smoothstep(0.0, 0.35, vUv.y);
                float radius = mask * blurStrength;
                if (radius < 0.1) {
                    gl_FragColor = texture2D(tDiffuse, vUv);
                } else {
                    vec4 color = vec4(0.0);
                    float total = 0.0;
                    const float GA = 2.3999632;
                    for (int i = 0; i < 32; i++) {
                        float f = float(i);
                        float r = sqrt(f) * radius;
                        float theta = f * GA;
                        vec2 offset = vec2(cos(theta), sin(theta)) * (r / resolution);
                        color += texture2D(tDiffuse, vUv + offset);
                        total += 1.0;
                    }
                    gl_FragColor = color / total;
                }
            }
        `
    };
    blurPass = new ShaderPass(foregroundBlurShader);
    outputPass = new OutputPass();

    composer = new EffectComposer(renderer, renderTarget);
    composer.setPixelRatio(config.dpr);
    composer.addPass(renderScene);
    composer.addPass(smaaPass);
    composer.addPass(bloomPass);
    composer.addPass(blurPass);
    composer.addPass(outputPass);

    createFloor();
    generateTrails();
    updateGeometries();

    window.addEventListener('resize', onWindowResize);
}

function createFloor() {
    const floorMat = new THREE.MeshBasicMaterial({ color: 0x000000, transparent: true, opacity: 0.85, depthWrite: false, side: THREE.DoubleSide });
    floorMesh = new THREE.Mesh(new THREE.BufferGeometry(), floorMat);
    floorMesh.position.set(0, -0.5, -0.5);
    floorMesh.renderOrder = 1;
    scene.add(floorMesh);
}

function generateTrails() {
    const group = new THREE.Group();
    scene.add(group);

    const vertexShader = `
        varying vec2 vUv;
        varying vec3 vNormal;
        varying vec3 vViewPosition;
        void main() {
            vUv = uv;
            vNormal = normalMatrix * normal;
            vec4 mvPosition = modelViewMatrix * vec4(position, 1.0);
            vViewPosition = -mvPosition.xyz;
            gl_Position = projectionMatrix * mvPosition;
        }
    `;

    const fragmentShader = `
        varying vec2 vUv;
        varying vec3 vNormal;
        varying vec3 vViewPosition;
        uniform float uTime;
        uniform vec3 uColor;
        uniform float uSpeed;
        uniform float uOffset;
        uniform float uTailLength;
        uniform float uIntensityMultiplier;
        uniform float uBendUv;
        uniform float uIsReflection;
        uniform float uDotDensity;
        uniform float uDotSize;
        uniform float uDotSpeed;
        uniform float uBrightness;

        float hash(vec2 p) {
            return fract(sin(dot(p, vec2(12.9898, 78.233))) * 43758.5453);
        }

        void main() {
            float t = fract(uTime * uSpeed + uOffset);
            float dist = fract(t - vUv.x + 1.0);
            
            float baseAlpha = smoothstep(uTailLength, 0.0, dist);
            baseAlpha = pow(max(0.0, baseAlpha), 1.2);

            vec3 viewDir = normalize(vViewPosition);
            float fresnel = abs(dot(normalize(vNormal), viewDir));
            
            float edgeSoftness = smoothstep(0.0, 0.02, fresnel);
            baseAlpha *= edgeSoftness;

            float core = pow(max(0.0, baseAlpha), 3.0) * 1.5;

            float movingUV = vUv.x - (uTime * uSpeed * uDotSpeed) - uOffset;
            float signalPos = movingUV * uDotDensity;
            float dotId = floor(signalPos);
            float dotLocal = fract(signalPos);

            float distToCenter = length(vec2((dotLocal - 0.5) * 2.0, (fract(vUv.y + 0.5) - 0.5) * 6.0));
            float dotShape = 1.0 - smoothstep(0.0, max(0.001, uDotSize), distToCenter);
            float dotFinal = dotShape * step(0.6, hash(vec2(dotId, uOffset))) * (sin(uTime * 4.0 + hash(vec2(dotId)) * 6.28) * 0.3 + 0.7) * baseAlpha;
            
            if (uIsReflection > 0.5) {
                float refFade = 1.0 - smoothstep(uBendUv - 0.015, uBendUv, vUv.x);
                
                baseAlpha *= refFade;
                core *= refFade;
                dotFinal *= refFade * 0.1;
                baseAlpha = pow(max(0.0, baseAlpha), 0.5) * (0.7 + hash(vUv * 300.0 + uTime * 0.05) * 0.3);
                core *= 0.3;
            }

            vec3 trailColor = uColor * (baseAlpha + core * 1.5) * uIntensityMultiplier * uBrightness;
            vec3 rgb = trailColor / max(1.0 - clamp(dotFinal * 1.8, 0.0, 0.95), 0.001) + uColor * dotFinal * 2.5 * uIntensityMultiplier * uBrightness;

            gl_FragColor = vec4(rgb, (baseAlpha + dotFinal) * uIntensityMultiplier);
        }
    `;

    for (let i = 0; i < config.linesCount; i++) {
        const normIdx = (i / (config.linesCount - 1)) * 2 - 1;
        const linearPos = normIdx;
        const expPos = Math.sign(normIdx) * Math.pow(Math.abs(normIdx), 1.2);
        let startX = (linearPos * 0.5 + expPos * 0.5) * 80;
        startX += (Math.random() - 0.5) * 2.0;
        
        const thickness = Math.random() * 0.2 + 0.1;
        const colorIdx = Math.floor(Math.random() * 5);
        
        const uniforms = {
            uTime: { value: 0 },
            uColor: { value: new THREE.Color(config[`color${colorIdx}`]) },
            uColorIndex: { value: colorIdx },
            uSpeed: { value: Math.random() * 0.5 + 0.2 },
            uOffset: { value: Math.random() },
            uTailLength: { value: Math.random() * 0.4 + 0.3 },
            uIntensityMultiplier: { value: 1.0 },
            uBendUv: { value: 0.0 },
            uIsReflection: { value: 0.0 },
            uDotDensity: { value: config.dotDensity },
            uDotSize: { value: config.dotSize },
            uDotSpeed: { value: config.dotSpeed },
            uBrightness: { value: config.brightness }
        };

        const material = new THREE.ShaderMaterial({ vertexShader, fragmentShader, uniforms, transparent: true, depthWrite: false, blending: THREE.AdditiveBlending });
        const mesh = new THREE.Mesh(new THREE.BufferGeometry(), material);
        const refMaterial = material.clone();
        refMaterial.uniforms.uIntensityMultiplier.value = 0.4;
        refMaterial.uniforms.uIsReflection.value = 1.0;
        const refMesh = new THREE.Mesh(new THREE.BufferGeometry(), refMaterial);
        refMesh.scale.y = -1; refMesh.position.y = -1.0;

        group.add(mesh, refMesh);
        trailMaterials.push(material.uniforms, refMaterial.uniforms);
        trailObjects.push({ mesh, refMesh, startX, thickness });
    }
}

function updateGeometries() {
    if (floorMesh.geometry) floorMesh.geometry.dispose();
    
    const floorGeo = new THREE.PlaneGeometry(1000, 1000, 1, 1500);
    floorGeo.rotateX(-Math.PI * 0.5);
    const pos = floorGeo.attributes.position.array;
    
    for (let i = 0; i < pos.length; i += 3) {
        if (pos[i + 2] < config.bendStartZ) {
            let d = config.bendStartZ - pos[i + 2];
            let maxA = config.arcRadius * Math.PI * 0.5;
            if (d < maxA) {
                let n = d / maxA;
                let a = (n * 0.4 + (n * n * (3.0 - 2.0 * n)) * 0.6) * (Math.PI * 0.5);
                pos[i + 1] = config.arcRadius * (1.0 - Math.cos(a));
                pos[i + 2] = (config.bendStartZ) - Math.sin(a) * config.arcRadius;
            } else {
                pos[i + 1] = config.arcRadius + (d - maxA);
                pos[i + 2] = config.bendStartZ - config.arcRadius;
            }
        }
    }
    floorGeo.computeVertexNormals();
    floorMesh.geometry = floorGeo;

    const bendUv = Math.abs(config.floorLength - config.bendStartZ) / (Math.abs(config.floorLength - config.bendStartZ) + (Math.PI * config.arcRadius) * 0.5 + Math.max(0.1, config.wallHeight - config.arcRadius));

    trailObjects.forEach(obj => {
        const path = new CycCurve(obj.startX, config.floorLength, config.bendStartZ - config.arcRadius, config.arcRadius, config.wallHeight);
        const geo = new THREE.TubeGeometry(path, 200, obj.thickness, 8, false);
        if (obj.mesh.geometry) obj.mesh.geometry.dispose();
        obj.mesh.geometry = obj.refMesh.geometry = geo;
        obj.mesh.material.uniforms.uBendUv.value = obj.refMesh.material.uniforms.uBendUv.value = bendUv;
    });
}

function onWindowResize() {
    camera.aspect = window.innerWidth / window.innerHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
    composer.setSize(window.innerWidth, window.innerHeight);
    if (smaaPass) smaaPass.setSize(window.innerWidth * config.dpr, window.innerHeight * config.dpr);
    blurPass.uniforms.resolution.value.set(window.innerWidth * config.dpr, window.innerHeight * config.dpr);
}

function animate() {
    requestAnimationFrame(animate);
    globalTime += clock.getDelta() * config.speedMultiplier;
    trailMaterials.forEach(m => m.uTime.value = globalTime);
    composer.render();
}
```

---

## Effect #14: Retrofuturistic Circuit Loop
*An interactive 3D retrofuturistic circuit board loop rendered via Spline.*

### HTML
```html
<div class="spline-container">
    <iframe src="https://my.spline.design/retrofuturisticcircuitloop-JngSBMetOQh9Jn4XS5OxTiIc/" frameborder="0" width="100%" height="100%" id="aura-spline"></iframe>
</div>
```

### CSS
```css
.spline-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -10;
}
```

### JavaScript
No JavaScript dependency required for iframe embed.

---

## Effect #15: Shooting Stars
*A night sky where streaks shoot across with variable length, speed, and direction over a twinkling starfield.*

### HTML
```html
<div class="bg-effect-15" id="stars-wrap-15">
    <div class="stars-sky absolute inset-0 z-0">
        <div class="absolute inset-x-0 top-1/4 h-3/4 opacity-40 glow-overlay"></div>
        <svg class="absolute inset-0 h-full w-full stars-svg" aria-hidden="true">
            <defs>
                <linearGradient id="ss-white-15" x1="0" y1="0" x2="1" y2="0">
                    <stop offset="0%" stop-color="#ffffff" stop-opacity="0" />
                    <stop offset="100%" stop-color="#ffffff" stop-opacity="1" />
                </linearGradient>
                <linearGradient id="ss-blue-15" x1="0" y1="0" x2="1" y2="0">
                    <stop offset="0%" stop-color="#9ec1ff" stop-opacity="0" />
                    <stop offset="100%" stop-color="#cfe0ff" stop-opacity="1" />
                </linearGradient>
                <linearGradient id="ss-warm-15" x1="0" y1="0" x2="1" y2="0">
                    <stop offset="0%" stop-color="#ffd9a8" stop-opacity="0" />
                    <stop offset="100%" stop-color="#ffe9cf" stop-opacity="1" />
                </linearGradient>
                <radialGradient id="ss-glow-15">
                    <stop offset="0%" stop-color="#ffffff" stop-opacity="0.9" />
                    <stop offset="100%" stop-color="#ffffff" stop-opacity="0" />
                </radialGradient>
            </defs>
            <g class="dots-group"></g>
            <g class="stars-group"></g>
        </svg>
    </div>
</div>
```

### CSS
```css
.bg-effect-15 {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #05050f;
}
.bg-effect-15 .stars-sky {
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(to bottom, #1e1b4b, #05050f);
}
.bg-effect-15 .glow-overlay {
    position: absolute;
    inset: 0;
    top: 25%;
    height: 75%;
    opacity: 0.4;
    background: radial-gradient(55% 50% at 50% 45%, rgba(76,82,180,0.4) 0%, rgba(20,22,60,0.22) 45%, rgba(5,5,15,0) 100%);
}
.bg-effect-15 svg {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
}
@keyframes ss-shoot-15 {
    0% {
        transform: translate(0px, 0px);
        opacity: 0;
    }
    6% {
        opacity: 1;
    }
    82% {
        opacity: 1;
    }
    100% {
        transform: translate(var(--dx), var(--dy));
        opacity: 0;
    }
}
@keyframes ss-twinkle-15 {
    0%, 100% {
        opacity: var(--o);
    }
    50% {
        opacity: calc(var(--o) * 0.25);
    }
}
```

### JavaScript
```javascript
function initShootingStars() {
    const wrap = document.getElementById('stars-wrap-15');
    if (!wrap) return;
    const svg = wrap.querySelector('.stars-svg');
    const dotsGroup = wrap.querySelector('.dots-group');
    const starsGroup = wrap.querySelector('.stars-group');
    if (!svg || !dotsGroup || !starsGroup) return;

    const w = wrap.clientWidth;
    const h = wrap.clientHeight;

    // Generate dots (static background stars)
    dotsGroup.innerHTML = '';
    const dotCount = 40;
    for (let i = 0; i < dotCount; i++) {
        const cx = Math.random() * w;
        const cy = Math.random() * h;
        const r = Math.random() * 0.9 + 0.4;
        const o = Math.random() * 0.55 + 0.15;

        const circle = document.createElementNS('http://www.w3.org/2000/svg', 'circle');
        circle.setAttribute('cx', cx);
        circle.setAttribute('cy', cy);
        circle.setAttribute('r', r);
        circle.setAttribute('fill', '#fff');
        circle.style.setProperty('--o', o);
        circle.style.opacity = o;
        circle.style.animation = `ss-twinkle-15 ${4 + (i % 5)}s ease-in-out ${i % 7}s infinite`;
        dotsGroup.appendChild(circle);
    }

    // Generate shooting stars
    starsGroup.innerHTML = '';
    const starCount = 8;
    const rand = (min, max) => min + Math.random() * (max - min);

    function createAndAnimateStar() {
        const angle = rand(15, 31);
        const rad = (angle * Math.PI) / 180;
        const len = rand(60, 150);
        const margin = len + 48;
        const diag = Math.hypot(w, h);
        const travel = diag + margin * 2;
        const fromTop = Math.random() < w / (w + h);
        const x = fromTop ? rand(-0.15 * w, 0.85 * w) : -margin - rand(0, 0.2 * w);
        const y = fromTop ? -margin - rand(0, 0.2 * h) : rand(-0.15 * h, 0.6 * h);
        
        const dx = Math.cos(rad) * travel;
        const dy = Math.sin(rad) * travel;
        const width = rand(1, 2.2);
        const duration = rand(1.5, 3.5);
        const delay = rand(0, 2);
        
        const grads = ['ss-white-15', 'ss-blue-15', 'ss-warm-15'];
        const grad = Math.random() < 0.8 ? 'ss-white-15' : grads[Math.floor(Math.random() * 2) + 1];

        const gContainer = document.createElementNS('http://www.w3.org/2000/svg', 'g');
        gContainer.setAttribute('transform', `translate(${x} ${y})`);

        const gMotion = document.createElementNS('http://www.w3.org/2000/svg', 'g');
        gMotion.style.setProperty('--dx', `${dx}px`);
        gMotion.style.setProperty('--dy', `${dy}px`);
        gMotion.style.opacity = 0;
        gMotion.style.animation = `ss-shoot-15 ${duration}s cubic-bezier(0.4, 0, 0.7, 1) ${delay}s forwards`;

        const gRot = document.createElementNS('http://www.w3.org/2000/svg', 'g');
        gRot.setAttribute('transform', `rotate(${angle})`);

        const rect = document.createElementNS('http://www.w3.org/2000/svg', 'rect');
        rect.setAttribute('x', -len);
        rect.setAttribute('y', -width / 2);
        rect.setAttribute('width', len);
        rect.setAttribute('height', width);
        rect.setAttribute('rx', width / 2);
        rect.setAttribute('fill', `url(#${grad})`);

        const glow = document.createElementNS('http://www.w3.org/2000/svg', 'circle');
        glow.setAttribute('cx', 0);
        glow.setAttribute('cy', 0);
        glow.setAttribute('r', Math.max(5, width * 3.5));
        glow.setAttribute('fill', 'url(#ss-glow-15)');

        const core = document.createElementNS('http://www.w3.org/2000/svg', 'circle');
        core.setAttribute('cx', 0);
        core.setAttribute('cy', 0);
        core.setAttribute('r', Math.max(1.4, width * 1.05));
        core.setAttribute('fill', '#ffffff');

        gRot.appendChild(rect);
        gRot.appendChild(glow);
        gRot.appendChild(core);
        gMotion.appendChild(gRot);
        gContainer.appendChild(gMotion);
        starsGroup.appendChild(gContainer);

        gMotion.addEventListener('animationend', () => {
            gContainer.remove();
            createAndAnimateStar();
        });
    }

    for (let i = 0; i < starCount; i++) {
        setTimeout(createAndAnimateStar, i * 400);
    }
}
```
