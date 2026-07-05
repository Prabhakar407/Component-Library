# Premium Custom Calls to Action Code Database

This file contains the complete, self-contained HTML, CSS, and JavaScript/React code snippets for all **9 Premium Calls to Action** featured in the interactive showcase. Each component is numbered to match the UI labels in the application.

---

## Table of Contents
1. [CTA #1: Canvas Reveal Interactive Waitlist](#cta-1-canvas-reveal-interactive-waitlist)
2. [CTA #2: Aurora Glowing Border Subscription Card](#cta-2-aurora-glowing-border-subscription-card)
3. [CTA #3: Glassmorphic Floating Bubbles Discount Banner](#cta-3-glassmorphic-floating-bubbles-discount-banner)
4. [CTA #4: Spotlight Cursor Tracking Action Card Grid](#cta-4-spotlight-cursor-tracking-action-card-grid)
5. [CTA #5: Magnetic Button Newsletter Box](#cta-5-magnetic-button-newsletter-box)
6. [CTA #6: Cyber Glow Secure Beta Access Node](#cta-6-cyber-glow-secure-beta-access-node)
7. [CTA #7: Purple Aura Glowing Button](#cta-7-purple-aura-glowing-button)
8. [CTA #8: Jello Hover Discover Button](#cta-8-jello-hover-discover-button)
9. [CTA #9: Star Sparkle Letter-Anim Button](#cta-9-star-sparkle-letter-anim-button)

---

## CTA #1: Canvas Reveal Interactive Waitlist
*An advanced waitlist banner component featuring an interactive background canvas point-matrix reveal, multiple transition steps, and clean cyberpunk aesthetics.*

### Project Prerequisites & Integration Instructions
* **shadcn-ui project structure**: Place the component at `/components/ui/waitlist-cta.tsx`.
* **External dependencies**: `npm install three @types/three @react-three/fiber framer-motion lucide-react`

### HTML
```html
<div class="cta-box-canvas-reveal" id="cta-reveal-1">
    <canvas class="reveal-canvas" id="cta-canvas-reveal-1"></canvas>
    <div class="reveal-content-container">
        <div class="reveal-step active" id="cta-reveal-step-email-1">
            <h2>Join the Inner Circle</h2>
            <p class="subtitle">Get early developer beta access</p>
            <form onsubmit="goToCTARevealCode(1); return false;">
                <div class="email-input-wrap">
                    <input type="email" placeholder="enter your email..." required />
                    <button type="submit" class="email-submit-btn">
                        <span class="arrow-container">→</span>
                    </button>
                </div>
            </form>
            <p class="legal-text">Limited access nodes available weekly.</p>
        </div>
        <div class="reveal-step" id="cta-reveal-step-code-1">
            <h2>Verify your access</h2>
            <p class="subtitle">Enter the 4-digit temporary pass</p>
            <div class="code-inputs-container">
                <div class="code-inputs-wrapper">
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleCTARevealInput(1, 0, this)" onkeydown="handleCTARevealKeydown(1, 0, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleCTARevealInput(1, 1, this)" onkeydown="handleCTARevealKeydown(1, 1, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleCTARevealInput(1, 2, this)" onkeydown="handleCTARevealKeydown(1, 2, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleCTARevealInput(1, 3, this)" onkeydown="handleCTARevealKeydown(1, 3, event)" class="code-input" />
                </div>
            </div>
            <div class="btn-group">
                <button class="back-btn" onclick="goToCTARevealEmail(1)">Back</button>
                <button class="continue-btn disabled" id="cta-continue-btn-1" onclick="submitCTARevealCode(1)" disabled>Verify</button>
            </div>
        </div>
        <div class="reveal-step" id="cta-reveal-step-success-1">
            <h2>Welcome to the Future</h2>
            <p class="subtitle">Access Key Generated Successfully</p>
            <div class="success-icon-wrap">
                <div class="success-circle">
                    <svg viewBox="0 0 20 20" fill="currentColor" width="22" height="22">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                    </svg>
                </div>
            </div>
            <button class="success-continue-btn" onclick="resetCTARevealForm(1)">Proceed to Sandbox</button>
        </div>
    </div>
</div>
```

### CSS
```css
.cta-box-canvas-reveal {
    width: 100%;
    height: 100%;
    min-height: 270px;
    background: #000;
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 12px;
}
.reveal-canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
    pointer-events: none;
}
.reveal-content-container {
    position: relative;
    z-index: 2;
    width: 280px;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.reveal-step {
    display: none;
    width: 100%;
    flex-direction: column;
    align-items: center;
    text-align: center;
    animation: reveal-fade 0.3s ease forwards;
}
.reveal-step.active {
    display: flex;
}
@keyframes reveal-fade {
    from { opacity: 0; transform: translateY(6px); }
    to { opacity: 1; transform: translateY(0); }
}
.reveal-step h2 {
    font-size: 1.1rem;
    color: #fff;
    margin-bottom: 2px;
    font-weight: 600;
}
.reveal-step .subtitle {
    font-size: 0.72rem;
    color: rgba(255, 255, 255, 0.6);
    margin-bottom: 12px;
}
.email-input-wrap {
    position: relative;
    width: 100%;
}
.email-input-wrap input {
    width: 100%;
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 20px;
    padding: 6px 36px 6px 12px;
    color: #fff;
    font-size: 0.7rem;
    outline: none;
    text-align: center;
    transition: all 0.3s;
}
.email-input-wrap input:focus {
    border-color: rgba(255, 255, 255, 0.25);
}
.email-submit-btn {
    position: absolute;
    right: 4px;
    top: 4px;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.08);
    border: none;
    color: #fff;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.65rem;
    transition: background 0.2s;
}
.email-submit-btn:hover {
    background: rgba(255, 255, 255, 0.15);
}
.legal-text {
    font-size: 0.55rem;
    color: rgba(255, 255, 255, 0.35);
    margin-top: 15px;
}
.code-inputs-container {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-bottom: 10px;
}
.code-inputs-wrapper {
    display: inline-flex;
    align-items: center;
    background: transparent;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 20px;
    padding: 5px 12px;
}
.code-input {
    width: 16px;
    background: transparent;
    border: none;
    color: #fff;
    font-size: 0.85rem;
    text-align: center;
    outline: none;
}
.code-sep {
    color: rgba(255, 255, 255, 0.15);
    font-size: 0.85rem;
    margin: 0 2px;
    pointer-events: none;
}
.btn-group {
    display: flex;
    gap: 8px;
    width: 100%;
}
.back-btn {
    background: #fff;
    color: #000;
    border: none;
    border-radius: 20px;
    padding: 6px 12px;
    font-size: 0.7rem;
    font-weight: 500;
    cursor: pointer;
    width: 30%;
    transition: opacity 0.2s;
}
.back-btn:hover { opacity: 0.9; }
.continue-btn {
    flex: 1;
    background: #fff;
    color: #000;
    border: none;
    border-radius: 20px;
    padding: 6px 12px;
    font-size: 0.7rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s;
}
.continue-btn.disabled {
    background: #111;
    color: rgba(255,255,255,0.3);
    border: 1px solid rgba(255,255,255,0.08);
    cursor: not-allowed;
}
.success-icon-wrap { margin: 10px 0; }
.success-circle {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background: linear-gradient(135deg, #fff 0%, #cbd5e1 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #000;
}
.success-continue-btn {
    width: 100%;
    background: #fff;
    color: #000;
    border: none;
    border-radius: 20px;
    padding: 7px 12px;
    font-size: 0.7rem;
    font-weight: 500;
    cursor: pointer;
    transition: opacity 0.2s;
}
.success-continue-btn:hover { opacity: 0.9; }
```

### JS
```javascript
window.initCTARevealCanvas = function(id) {
    const box = document.getElementById(`cta-reveal-${id}`);
    if (!box) return;
    const canvas = box.querySelector('.reveal-canvas');
    if (!canvas) return;
    
    const resize = () => {
        const rect = box.getBoundingClientRect();
        canvas.width = rect.width * 2;
        canvas.height = rect.height * 2;
    };
    resize();
    
    const ctx = canvas.getContext('2d');
    let time = 0;
    let isReverse = false;
    
    const dotSpacing = 16;
    const dotSize = 2.5;
    
    box.triggerReverse = function(val) {
        isReverse = val;
        time = 0;
    };
    
    const render = () => {
        if (!ctx) return;
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        const w = canvas.width;
        const h = canvas.height;
        
        const cols = Math.floor(w / dotSpacing);
        const rows = Math.floor(h / dotSpacing);
        
        const centerX = w / 2;
        const centerY = h / 2;
        
        time += 0.04;
        const speed = 0.5;
        const maxDist = Math.sqrt(centerX * centerX + centerY * centerY);
        
        for (let r = 0; r < rows; r++) {
            for (let c = 0; c < cols; c++) {
                const x = c * dotSpacing + (w % dotSpacing) / 2;
                const y = r * dotSpacing + (h % dotSpacing) / 2;
                
                const dx = x - centerX;
                const dy = y - centerY;
                const dist = Math.sqrt(dx * dx + dy * dy);
                
                const phi = 1.6180339887;
                const showOffset = Math.sin(c * phi + r) * 0.5 + 0.5;
                const rand = Math.sin((c * 3 + r * 7) * Math.floor(time * 0.2 + showOffset)) * 0.5 + 0.5;
                
                let baseOpacity = 0.03 + rand * 0.15;
                const timingIntro = dist * 0.003 + showOffset * 0.2;
                const timingOutro = ((maxDist - dist) * 0.004) + showOffset * 0.2;
                
                let visibility = 1;
                
                if (isReverse) {
                    visibility = 1.0 - (time * speed > timingOutro ? 1.0 : 0.0);
                    if (time * speed > timingOutro) {
                        visibility = Math.max(0, 1 - (time * speed - timingOutro) * 4);
                    }
                } else {
                    visibility = (time * speed > timingIntro ? 1.0 : 0.0);
                    if (time * speed > timingIntro) {
                        visibility = Math.min(1, (time * speed - timingIntro) * 4);
                    }
                }
                
                const finalOpacity = baseOpacity * visibility;
                if (finalOpacity > 0.001) {
                    ctx.fillStyle = `rgba(255, 255, 255, ${finalOpacity})`;
                    ctx.beginPath();
                    ctx.arc(x, y, dotSize / 2, 0, Math.PI * 2);
                    ctx.fill();
                }
            }
        }
        requestAnimationFrame(render);
    };
    render();
    window.addEventListener('resize', resize);
};
```

### React
```tsx
"use client";

import React, { useState } from "react";
import { motion, AnimatePresence } from "framer-motion";
import { Canvas } from "@react-three/fiber";

export default function CanvasRevealWaitlist() {
  const [step, setStep] = useState<"email" | "code" | "success">("email");
  const [email, setEmail] = useState("");
  const [code, setCode] = useState(["", "", "", ""]);

  return (
    <div className="relative w-full min-h-[300px] bg-black flex items-center justify-center rounded-xl overflow-hidden p-6">
      <div className="z-10 text-center max-w-xs w-full text-white">
        <AnimatePresence mode="wait">
          {step === "email" && (
            <motion.div exit={{ opacity: 0, y: -10 }}>
              <h3 className="text-xl font-bold">Join the Inner Circle</h3>
              <p className="text-xs text-zinc-400 mt-1 mb-4">Get early developer beta access</p>
              <form onSubmit={(e) => { e.preventDefault(); setStep("code"); }} className="relative">
                <input 
                  type="email" 
                  value={email}
                  onChange={(e) => setEmail(e.target.value)}
                  placeholder="enter your email..." 
                  className="w-full bg-zinc-900 border border-zinc-800 rounded-full py-2 px-4 text-sm text-center focus:outline-none focus:border-zinc-600"
                  required
                />
                <button type="submit" className="absolute right-1.5 top-1.5 bg-zinc-800 w-7 h-7 rounded-full flex items-center justify-center hover:bg-zinc-700">
                  →
                </button>
              </form>
            </motion.div>
          )}
          {step === "code" && (
            <motion.div initial={{ opacity: 0, y: 10 }} animate={{ opacity: 1, y: 0 }} exit={{ opacity: 0, y: -10 }}>
              <h3 className="text-xl font-bold">Verify access</h3>
              <p className="text-xs text-zinc-400 mt-1 mb-4">Enter verification pass</p>
              <div className="flex gap-2 justify-center mb-4">
                {code.map((val, idx) => (
                  <input
                    key={idx}
                    type="text"
                    maxLength={1}
                    value={val}
                    onChange={(e) => {
                      const next = [...code];
                      next[idx] = e.target.value;
                      setCode(next);
                      if (e.target.value && idx < 3) {
                        const nextEl = document.getElementById(`c-${idx+1}`);
                        nextEl?.focus();
                      }
                    }}
                    id={`c-${idx}`}
                    className="w-8 h-10 bg-zinc-900 border border-zinc-800 rounded text-center text-lg focus:outline-none focus:border-white"
                  />
                ))}
              </div>
              <div className="flex gap-2">
                <button onClick={() => setStep("email")} className="w-1/3 py-2 bg-zinc-800 text-sm rounded-full">Back</button>
                <button onClick={() => setStep("success")} className="flex-1 py-2 bg-white text-black text-sm rounded-full font-semibold">Verify</button>
              </div>
            </motion.div>
          )}
          {step === "success" && (
            <motion.div initial={{ opacity: 0, scale: 0.9 }} animate={{ opacity: 1, scale: 1 }}>
              <h3 className="text-xl font-bold">Welcome to the Future</h3>
              <p className="text-xs text-zinc-400 mt-1 mb-4">Access key generated successfully</p>
              <button onClick={() => { setStep("email"); setCode(["","","",""]); }} className="w-full py-2 bg-white text-black text-sm rounded-full font-semibold">
                Proceed to Sandbox
              </button>
            </motion.div>
          )}
        </AnimatePresence>
      </div>
    </div>
  );
}
```

---

## CTA #2: Aurora Glowing Border Subscription Card
*A gorgeous call to action card wrapped in a dynamic, continuous glowing linear gradient border with modern glassmorphism elements.*

### Project Prerequisites & Integration Instructions
* **Tailwind CSS keyframes**: Add `@keyframes aurora-border` and animation utilities to your styles.

### HTML
```html
<div class="cta-box-aurora" id="cta-aurora-2">
    <div class="aurora-inner">
        <h4>Weekly Design Gems</h4>
        <p>Zero spam. Just premium UI ideas, animations, and clean CSS code blocks directly in your inbox.</p>
        <form onsubmit="showToast('Subscribed to Weekly Design Gems!'); return false;">
            <div class="aurora-field">
                <input type="email" placeholder=" " required />
                <label>Email Address</label>
            </div>
            <button type="submit" class="aurora-btn">Receive Gems</button>
        </form>
    </div>
</div>
```

### CSS
```css
.cta-box-aurora {
    position: relative;
    width: 290px;
    background: #060913;
    border-radius: 16px;
    padding: 2px;
    overflow: hidden;
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
}
.cta-box-aurora::before {
    content: '';
    position: absolute;
    inset: -150px;
    background: conic-gradient(from 0deg at 50% 50%, #6366f1, #d946ef, #3b82f6, #6366f1);
    animation: rotate-aurora-border 4s linear infinite;
    z-index: 1;
}
@keyframes rotate-aurora-border {
    100% { transform: rotate(360deg); }
}
.aurora-inner {
    position: relative;
    z-index: 2;
    background: #0d1220;
    border-radius: 14px;
    padding: 1.5rem 1.25rem;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
}
.aurora-inner h4 {
    color: #fff;
    font-size: 1.05rem;
    font-weight: 600;
    text-align: center;
}
.aurora-inner p {
    color: #94a3b8;
    font-size: 0.72rem;
    line-height: 1.4;
    text-align: center;
    margin-bottom: 0.5rem;
}
.aurora-field {
    position: relative;
    width: 100%;
}
.aurora-field input {
    width: 100%;
    background: rgba(15, 18, 32, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 8px;
    padding: 10px 12px;
    color: #fff;
    font-size: 0.78rem;
    outline: none;
    transition: border-color 0.3s;
}
.aurora-field label {
    position: absolute;
    left: 12px;
    top: 50%;
    transform: translateY(-50%);
    color: #64748b;
    font-size: 0.75rem;
    pointer-events: none;
    transition: all 0.3s;
}
.aurora-field input:focus ~ label,
.aurora-field input:not(:placeholder-shown) ~ label {
    top: -5px;
    left: 8px;
    font-size: 0.65rem;
    color: #a5b4fc;
    background: #0d1220;
    padding: 0 4px;
}
.aurora-field input:focus {
    border-color: #6366f1;
}
.aurora-btn {
    width: 100%;
    background: linear-gradient(90deg, #6366f1, #3b82f6);
    color: #fff;
    border: none;
    border-radius: 8px;
    padding: 10px;
    font-weight: 600;
    font-size: 0.78rem;
    cursor: pointer;
    margin-top: 4px;
    transition: opacity 0.2s;
}
.aurora-btn:hover { opacity: 0.9; }
```

### React
```tsx
import React from "react";

export default function AuroraCTA() {
  return (
    <div className="relative w-[290px] rounded-2xl p-[2px] overflow-hidden bg-zinc-950 shadow-2xl group">
      <div className="absolute inset-[-100px] bg-[conic-gradient(from_0deg_at_50%_50%,#6366f1,#d946ef,#3b82f6,#6366f1)] animate-[spin_5s_linear_infinite] z-0" />
      <div className="relative z-10 bg-zinc-900 rounded-[14px] p-6 flex flex-col gap-4 text-center">
        <h4 className="text-white text-lg font-bold">Weekly Design Gems</h4>
        <p className="text-xs text-zinc-400">Zero spam. Just premium UI ideas, animations, and clean CSS code blocks.</p>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-3">
          <input 
            type="email" 
            placeholder="Email Address" 
            className="w-full bg-black/40 border border-zinc-800 rounded-lg py-2 px-3 text-xs text-white placeholder-zinc-600 focus:outline-none focus:border-indigo-500" 
            required 
          />
          <button type="submit" className="w-full bg-gradient-to-r from-indigo-500 to-blue-500 text-white rounded-lg py-2 text-xs font-bold hover:opacity-90 transition-opacity">
            Receive Gems
          </button>
        </form>
      </div>
    </div>
  );
}
```

---

## CTA #3: Glassmorphic Floating Bubbles Discount Banner
*A highly interactive glassmorphism block containing floating color blobs that drift in the background, promoting a code copy function.*

### Project Prerequisites & Integration Instructions
* **Glassmorphism Backdrop Support**: Ensure your browser supports CSS `backdrop-filter`.

### HTML
```html
<div class="cta-box-glass" id="cta-glass-3">
    <div class="glass-bubble bubble-1"></div>
    <div class="glass-bubble bubble-2"></div>
    <div class="glass-inner">
        <span class="glass-tag">Limited Time</span>
        <h3>Get 30% Off</h3>
        <p class="desc">Unlock access to our entire premium suite of interactive resources.</p>
        <div class="coupon-box" onclick="copyCouponCode('UPGRADE30')">
            <span class="code">UPGRADE30</span>
            <span class="copy-hint">Copy</span>
        </div>
    </div>
</div>
```

### CSS
```css
.cta-box-glass {
    position: relative;
    width: 290px;
    height: 250px;
    background: #0a0d18;
    border: 1px solid rgba(255,255,255,0.05);
    border-radius: 16px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
}
.glass-bubble {
    position: absolute;
    border-radius: 50%;
    filter: blur(15px);
    opacity: 0.35;
    z-index: 1;
    animation: drift-bubble 6s ease-in-out infinite alternate;
}
.bubble-1 {
    width: 80px;
    height: 80px;
    background: #6366f1;
    top: 10%;
    left: 10%;
}
.bubble-2 {
    width: 90px;
    height: 90px;
    background: #ec4899;
    bottom: 10%;
    right: 10%;
    animation-delay: -3s;
}
@keyframes drift-bubble {
    0% { transform: translateY(0) scale(1); }
    100% { transform: translateY(15px) scale(1.1); }
}
.glass-inner {
    position: relative;
    z-index: 2;
    width: 90%;
    height: 90%;
    background: rgba(255, 255, 255, 0.03);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 12px;
    padding: 1.25rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
}
.glass-tag {
    background: rgba(236, 72, 153, 0.15);
    border: 1px solid rgba(236, 72, 153, 0.3);
    color: #f472b6;
    padding: 2px 8px;
    border-radius: 12px;
    font-size: 0.6rem;
    font-weight: 600;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
}
.glass-inner h3 {
    color: #fff;
    font-size: 1.4rem;
    font-weight: 700;
    margin-bottom: 0.25rem;
}
.glass-inner .desc {
    color: #94a3b8;
    font-size: 0.7rem;
    line-height: 1.4;
    margin-bottom: 1rem;
}
.coupon-box {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(255,255,255,0.05);
    border: 1px dashed rgba(255,255,255,0.2);
    border-radius: 6px;
    width: 100%;
    padding: 8px 12px;
    cursor: pointer;
    transition: all 0.2s;
}
.coupon-box:hover {
    background: rgba(255,255,255,0.08);
    border-color: rgba(255,255,255,0.3);
}
.coupon-box .code {
    color: #fff;
    font-family: monospace;
    font-weight: 700;
    font-size: 0.85rem;
    letter-spacing: 1px;
}
.coupon-box .copy-hint {
    color: #a5b4fc;
    font-size: 0.7rem;
    font-weight: 600;
}
```

### JS
```javascript
window.copyCouponCode = function(code) {
    navigator.clipboard.writeText(code).then(() => {
        if (window.showToast) {
            window.showToast(`Coupon code "${code}" copied to clipboard!`);
        }
    });
};
```

### React
```tsx
import React, { useState } from "react";

export default function GlassDiscountCTA() {
  const [copied, setCopied] = useState(false);

  const handleCopy = () => {
    navigator.clipboard.writeText("UPGRADE30");
    setCopied(true);
    setTimeout(() => setCopied(false), 2000);
  };

  return (
    <div className="relative w-[290px] h-[250px] bg-[#0a0d18] rounded-2xl overflow-hidden flex items-center justify-center">
      <div className="absolute top-[10%] left-[10%] w-20 h-20 bg-indigo-500 rounded-full filter blur-[15px] opacity-40 animate-pulse" />
      <div className="absolute bottom-[10%] right-[10%] w-24 h-24 bg-pink-500 rounded-full filter blur-[15px] opacity-35 animate-bounce" />
      
      <div className="relative z-10 w-[90%] h-[90%] bg-white/5 backdrop-blur-md border border-white/10 rounded-xl p-4 flex flex-col items-center justify-center text-center">
        <span className="bg-pink-500/20 border border-pink-500/30 text-pink-300 text-[10px] font-bold px-2 py-0.5 rounded-full uppercase tracking-wider mb-2">
          Limited Time
        </span>
        <h3 className="text-white text-xl font-extrabold mb-1">Get 30% Off</h3>
        <p className="text-xs text-zinc-400 mb-4 px-2 leading-relaxed">
          Unlock access to our entire premium suite of interactive resources.
        </p>
        <button 
          onClick={handleCopy}
          className="w-full flex items-center justify-between border border-dashed border-white/20 bg-white/5 rounded-lg py-2 px-3 hover:bg-white/10 transition-colors"
        >
          <span className="text-white font-mono font-bold text-sm tracking-wider">UPGRADE30</span>
          <span className="text-indigo-300 text-xs font-semibold">{copied ? "Copied!" : "Copy"}</span>
        </button>
      </div>
    </div>
  );
}
```

---

## CTA #4: Spotlight Cursor Tracking Action Card Grid
*An interactive group of calls to action that feature cursor coordinate spotlight reflections.*

### Project Prerequisites & Integration Instructions
* **Spotlight Script**: Requires cursor hover tracking via Javascript to update CSS variables `--x` and `--y`.

### HTML
```html
<div class="cta-box-spotlight" id="cta-spotlight-4">
    <div class="spot-card" onclick="showToast('Navigating to Documentation...')">
        <h4>Developer APIs</h4>
        <p>Explore comprehensive technical docs, code references, and endpoints.</p>
        <span class="spot-link">View Docs →</span>
    </div>
    <div class="spot-card" onclick="showToast('Launching Discord Server invitation...')">
        <h4>Community Hub</h4>
        <p>Connect with 12k+ coders, discuss solutions, and share components.</p>
        <span class="spot-link">Join Discord →</span>
    </div>
</div>
```

### CSS
```css
.cta-box-spotlight {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 290px;
}
.spot-card {
    --x: 0px;
    --y: 0px;
    position: relative;
    background: #090a0f;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 12px;
    padding: 1.25rem;
    cursor: pointer;
    overflow: hidden;
    transition: border-color 0.3s;
}
.spot-card:hover {
    border-color: rgba(99, 102, 241, 0.3);
}
.spot-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle 80px at var(--x) var(--y), rgba(99, 102, 241, 0.12), transparent 80%);
    pointer-events: none;
    z-index: 0;
}
.spot-card h4 {
    color: #fff;
    font-size: 0.95rem;
    font-weight: 600;
    margin-bottom: 0.25rem;
    position: relative;
    z-index: 1;
}
.spot-card p {
    color: #64748b;
    font-size: 0.68rem;
    line-height: 1.4;
    margin-bottom: 0.75rem;
    position: relative;
    z-index: 1;
}
.spot-link {
    color: #a5b4fc;
    font-size: 0.7rem;
    font-weight: 600;
    position: relative;
    z-index: 1;
}
```

### JS
```javascript
window.initCTASpotlight = function(id) {
    const container = document.getElementById(`cta-spotlight-${id}`);
    if (!container) return;
    const cards = container.querySelectorAll('.spot-card');
    
    cards.forEach(card => {
        card.addEventListener('mousemove', (e) => {
            const rect = card.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;
            card.style.setProperty('--x', `${x}px`);
            card.style.setProperty('--y', `${y}px`);
        });
    });
};
```

### React
```tsx
import React, { useRef, useState } from "react";

export default function SpotlightGrid() {
  const cards = [
    { title: "Developer APIs", desc: "Explore technical docs, code references, and endpoints.", link: "View Docs →" },
    { title: "Community Hub", desc: "Connect with 12k+ coders, discuss, and share templates.", link: "Join Discord →" }
  ];

  return (
    <div className="flex flex-col gap-4 w-[290px]">
      {cards.map((card, idx) => {
        const cardRef = useRef<HTMLDivElement>(null);
        const [coords, setCoords] = useState({ x: 0, y: 0 });

        const handleMouseMove = (e: React.MouseEvent) => {
          if (!cardRef.current) return;
          const rect = cardRef.current.getBoundingClientRect();
          setCoords({
            x: e.clientX - rect.left,
            y: e.clientY - rect.top
          });
        };

        return (
          <div 
            key={idx}
            ref={cardRef}
            onMouseMove={handleMouseMove}
            className="relative bg-zinc-950 border border-zinc-800 hover:border-indigo-500/30 rounded-xl p-5 cursor-pointer overflow-hidden group transition-colors"
          >
            <div 
              className="absolute inset-0 pointer-events-none transition-opacity duration-300 opacity-0 group-hover:opacity-100"
              style={{
                background: `radial-gradient(circle 80px at ${coords.x}px ${coords.y}px, rgba(99, 102, 241, 0.1), transparent 80%)`
              }}
            />
            <h4 className="text-white text-sm font-bold mb-1 relative z-10">{card.title}</h4>
            <p className="text-zinc-400 text-[11px] leading-relaxed mb-3 relative z-10">{card.desc}</p>
            <span className="text-indigo-400 text-xs font-bold relative z-10">{card.link}</span>
          </div>
        );
      })}
    </div>
  );
}
```

---

## CTA #5: Magnetic Button Newsletter Box
*A modern subscription interface with an input box and a magnetic action button that follows user cursors.*

### Project Prerequisites & Integration Instructions
* **Cursor Attraction**: The JS handles the magnetic offset calculations.

### HTML
```html
<div class="cta-box-magnetic" id="cta-magnetic-5">
    <h4>Subscribe to Newsletter</h4>
    <p>Get curated weekly developer tool reviews.</p>
    <form onsubmit="showToast('Subscription Successful!'); return false;">
        <div class="mag-input-wrap">
            <input type="email" placeholder="example@mail.com" required />
            <div class="mag-btn-container">
                <button type="submit" class="magnetic-btn">
                    <span>Subscribe</span>
                </button>
            </div>
        </div>
    </form>
</div>
```

### CSS
```css
.cta-box-magnetic {
    width: 290px;
    background: #0b0c10;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 1.5rem 1.25rem;
    text-align: center;
}
.cta-box-magnetic h4 {
    color: #fff;
    font-size: 1.05rem;
    margin-bottom: 0.25rem;
}
.cta-box-magnetic p {
    color: #64748b;
    font-size: 0.7rem;
    margin-bottom: 1.25rem;
}
.mag-input-wrap {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    align-items: center;
    width: 100%;
}
.mag-input-wrap input {
    width: 100%;
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 8px;
    padding: 10px 12px;
    color: #fff;
    font-size: 0.8rem;
    outline: none;
    text-align: center;
    transition: all 0.3s;
}
.mag-input-wrap input:focus {
    border-color: rgba(99, 102, 241, 0.4);
    background: rgba(99, 102, 241, 0.02);
}
.mag-btn-container {
    width: 100%;
    height: 45px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.magnetic-btn {
    background: #fff;
    color: #000;
    border: none;
    border-radius: 8px;
    width: 100%;
    height: 38px;
    font-weight: 600;
    font-size: 0.8rem;
    cursor: pointer;
    transition: transform 0.2s cubic-bezier(0.2, 0.8, 0.2, 1);
    display: flex;
    align-items: center;
    justify-content: center;
}
.magnetic-btn span {
    pointer-events: none;
}
```

### JS
```javascript
window.initCTAMagnetic = function(id) {
    const container = document.getElementById(`cta-magnetic-${id}`);
    if (!container) return;
    const btn = container.querySelector('.magnetic-btn');
    const wrapper = container.querySelector('.mag-btn-container');
    if (!btn || !wrapper) return;
    
    wrapper.addEventListener('mousemove', (e) => {
        const rect = wrapper.getBoundingClientRect();
        const mouseX = e.clientX - rect.left - rect.width/2;
        const mouseY = e.clientY - rect.top - rect.height/2;
        
        // Attraction strength divisor (higher = less movement)
        btn.style.transform = `translate(${mouseX * 0.35}px, ${mouseY * 0.35}px)`;
    });
    
    wrapper.addEventListener('mouseleave', () => {
        btn.style.transform = 'translate(0px, 0px)';
    });
};
```

### React
```tsx
import React, { useRef, useState } from "react";
import { motion } from "framer-motion";

export default function MagneticNewsletter() {
  const containerRef = useRef<HTMLDivElement>(null);
  const [position, setPosition] = useState({ x: 0, y: 0 });

  const handleMouseMove = (e: React.MouseEvent) => {
    if (!containerRef.current) return;
    const { left, top, width, height } = containerRef.current.getBoundingClientRect();
    const x = e.clientX - (left + width / 2);
    const y = e.clientY - (top + height / 2);
    setPosition({ x: x * 0.35, y: y * 0.35 });
  };

  const handleMouseLeave = () => {
    setPosition({ x: 0, y: 0 });
  };

  return (
    <div className="w-[290px] bg-zinc-950 border border-zinc-800 rounded-xl p-5 text-center">
      <h4 className="text-white text-sm font-bold mb-1">Subscribe to Newsletter</h4>
      <p className="text-zinc-500 text-[11px] mb-4">Get curated weekly developer tool reviews.</p>
      <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-3">
        <input 
          type="email" 
          placeholder="example@mail.com" 
          className="w-full bg-black/40 border border-zinc-800 rounded-lg py-2 px-3 text-xs text-white text-center focus:outline-none focus:border-indigo-500" 
          required 
        />
        <div ref={containerRef} onMouseMove={handleMouseMove} onMouseLeave={handleMouseLeave} className="h-10 w-full flex items-center justify-center">
          <motion.button 
            animate={{ x: position.x, y: position.y }}
            transition={{ type: "spring", stiffness: 150, damping: 15 }}
            className="w-full py-2 bg-white text-black text-xs font-bold rounded-lg hover:opacity-90 transition-opacity"
          >
            Subscribe
          </motion.button>
        </div>
      </form>
    </div>
  );
}
```

---

## CTA #6: Cyber Glow Secure Beta Access Node
*Futuristic sci-fi terminal block with neon glows, passcode validation, and simulated access grant animations.*

### Project Prerequisites & Integration Instructions
* **Cyber Aesthetic**: Font imports such as JetBrains Mono recommended for code displays.

### HTML
```html
<div class="cta-box-cyber" id="cta-cyber-6">
    <div class="cyber-header">
        <span>STATUS: CLOSED</span>
        <span class="blink">●</span>
    </div>
    <h4>SECURE ACCESS NODE</h4>
    <div class="cyber-display" id="cyber-display-6">PASSCODE NEEDED</div>
    <div class="cyber-keypad">
        <button class="cyber-key" onclick="pressCyberKey(6, '7')">7</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '8')">8</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '9')">9</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '4')">4</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '5')">5</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '6')">6</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '1')">1</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '2')">2</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '3')">3</button>
        <button class="cyber-key red-key" onclick="clearCyberKey(6)">C</button>
        <button class="cyber-key" onclick="pressCyberKey(6, '0')">0</button>
        <button class="cyber-key green-key" onclick="submitCyberKey(6)">ENT</button>
    </div>
</div>
```

### CSS
```css
.cta-box-cyber {
    width: 250px;
    background: #020204;
    border: 1px solid #10b981;
    border-radius: 12px;
    padding: 1.25rem;
    box-shadow: 0 0 15px rgba(16,185,129,0.15);
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    align-items: center;
}
.cyber-header {
    width: 100%;
    display: flex;
    justify-content: space-between;
    font-size: 0.58rem;
    color: #10b981;
    letter-spacing: 1px;
}
.cyber-header .blink {
    animation: cyber-blink 1s infinite alternate;
}
@keyframes cyber-blink {
    0% { opacity: 0.2; }
    100% { opacity: 1; }
}
.cta-box-cyber h4 {
    color: #10b981;
    font-family: monospace;
    font-size: 0.85rem;
    letter-spacing: 1px;
}
.cyber-display {
    width: 100%;
    background: rgba(16,185,129,0.05);
    border: 1px solid rgba(16,185,129,0.3);
    color: #10b981;
    font-family: monospace;
    font-size: 1rem;
    letter-spacing: 2px;
    text-align: center;
    padding: 6px;
    border-radius: 6px;
    height: 34px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.cyber-keypad {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 6px;
    width: 100%;
}
.cyber-key {
    background: rgba(16,185,129,0.02);
    border: 1px solid rgba(16,185,129,0.2);
    color: #10b981;
    font-family: monospace;
    font-size: 0.85rem;
    font-weight: 600;
    padding: 8px 0;
    border-radius: 6px;
    cursor: pointer;
    transition: all 0.2s;
}
.cyber-key:hover {
    background: rgba(16,185,129,0.12);
    border-color: #10b981;
}
.red-key {
    color: #ef4444;
    border-color: rgba(239,68,68,0.2);
}
.green-key {
    color: #10b981;
    border-color: rgba(16,185,129,0.4);
    background: rgba(16,185,129,0.1);
}
.green-key:hover {
    background: #10b981;
    color: #000;
}
```

### JS
```javascript
let cyberInputCode = "";
window.pressCyberKey = function(id, val) {
    const display = document.getElementById(`cyber-display-${id}`);
    if (cyberInputCode.length < 4) {
        cyberInputCode += val;
        display.textContent = "*".repeat(cyberInputCode.length) + "•".repeat(4 - cyberInputCode.length);
    }
};
window.clearCyberKey = function(id) {
    cyberInputCode = "";
    const display = document.getElementById(`cyber-display-${id}`);
    display.textContent = "ENTER CODE";
};
window.submitCyberKey = function(id) {
    const display = document.getElementById(`cyber-display-${id}`);
    if (cyberInputCode === "1337" || cyberInputCode.length === 4) {
        display.textContent = "GRANTED";
        display.style.color = "#10b981";
        if (window.showToast) window.showToast("ACCESS GRANTED - Redirecting...");
        setTimeout(() => {
            cyberInputCode = "";
            display.textContent = "SECURED";
        }, 2000);
    } else {
        display.textContent = "DENIED";
        display.style.color = "#ef4444";
        setTimeout(() => {
            cyberInputCode = "";
            display.style.color = "#10b981";
            display.textContent = "ENTER CODE";
        }, 1200);
    }
};
```

### React
```tsx
import React, { useState } from "react";

export default function CyberAccessCTA() {
  const [code, setCode] = useState("");
  const [status, setStatus] = useState("PASSCODE NEEDED");

  const handlePress = (n: string) => {
    if (code.length < 4) {
      const nextCode = code + n;
      setCode(nextCode);
      setStatus("*".repeat(nextCode.length) + "•".repeat(4 - nextCode.length));
    }
  };

  const handleClear = () => {
    setCode("");
    setStatus("ENTER CODE");
  };

  const handleSubmit = () => {
    if (code.length === 4) {
      setStatus("GRANTED");
      setTimeout(() => {
        setCode("");
        setStatus("SECURED");
      }, 2000);
    } else {
      setStatus("DENIED");
      setTimeout(() => {
        setCode("");
        setStatus("ENTER CODE");
      }, 1200);
    }
  };

  return (
    <div className="w-[250px] bg-black border border-emerald-500 rounded-xl p-5 shadow-[0_0_15px_rgba(16,185,129,0.15)] flex flex-col items-center gap-3">
      <div className="w-full flex justify-between text-[10px] text-emerald-500 font-mono tracking-wider">
        <span>STATUS: CLOSED</span>
        <span className="animate-pulse">●</span>
      </div>
      <h4 className="text-emerald-500 text-xs font-mono font-bold tracking-widest">SECURE ACCESS NODE</h4>
      <div className="w-full bg-emerald-500/5 border border-emerald-500/30 text-emerald-500 font-mono text-center py-2.5 rounded text-sm tracking-wider">
        {status}
      </div>
      <div className="grid grid-cols-3 gap-2 w-full">
        {["7", "8", "9", "4", "5", "6", "1", "2", "3"].map((n) => (
          <button key={n} onClick={() => handlePress(n)} className="border border-emerald-500/20 bg-emerald-500/5 text-emerald-500 font-mono py-2 rounded text-xs hover:bg-emerald-500/10 hover:border-emerald-500">
            {n}
          </button>
        ))}
        <button onClick={handleClear} className="border border-red-500/20 bg-red-500/5 text-red-500 font-mono py-2 rounded text-xs hover:bg-red-500/10">C</button>
        <button onClick={() => handlePress("0")} className="border border-emerald-500/20 bg-emerald-500/5 text-emerald-500 font-mono py-2 rounded text-xs">0</button>
        <button onClick={handleSubmit} className="border border-emerald-500/40 bg-emerald-500/10 text-emerald-500 font-mono py-2 rounded text-xs hover:bg-emerald-500 hover:text-black">ENT</button>
      </div>
    </div>
  );
}
```

---

## CTA #7: Purple Aura Glowing Button
*A premium glowing button with a deep-space violet backdrop, multi-layered color gradients, and glassmorphic interior borders.*

### Project Prerequisites & Integration Instructions
* **shadcn-ui project structure**: Place the component at `/components/ui/button-cta.tsx`.
* **External dependencies**: `npm install lucide-react` (if icons added), plus standard `@/components/ui/button` shadcn-ui component.

### HTML
```html
<div class="btn-cta-wrapper">
    <button class="btn-cta" onclick="showToast('Access Unlocked!')">
        <div class="btn-cta-bg-border">
            <div class="btn-cta-bg-border-inner"></div>
        </div>
        <div class="btn-cta-bg-inner1"></div>
        <div class="btn-cta-bg-gradient-r"></div>
        <div class="btn-cta-bg-gradient-b"></div>
        <div class="btn-cta-bg-gradient-br"></div>
        <div class="btn-cta-shadow"></div>
        <div class="btn-cta-label-container">
            <span class="btn-cta-label">Get Access</span>
        </div>
        <div class="btn-cta-hover-bg"></div>
    </button>
</div>
```

### CSS
```css
.btn-cta-wrapper {
    display: flex;
    justify-content: center;
    width: 100%;
}
.btn-cta {
    position: relative;
    width: 180px;
    height: 48px;
    padding: 0 16px;
    border-radius: 8px;
    overflow: hidden;
    transition: all 0.5s ease;
    background: transparent;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
}
.btn-cta-bg-border {
    position: absolute;
    inset: 0;
    border-radius: 8px;
    padding: 2px;
    background: linear-gradient(to bottom, #654358, #17092A, #2F0D64);
}
.btn-cta-bg-border-inner {
    width: 100%;
    height: 100%;
    background: #170928;
    border-radius: 8px;
    opacity: 0.9;
}
.btn-cta-bg-inner1 {
    position: absolute;
    inset: 2px;
    background: #170928;
    border-radius: 8px;
    opacity: 0.95;
}
.btn-cta-bg-gradient-r {
    position: absolute;
    inset: 2px;
    background: linear-gradient(to right, #170928, #1d0d33, #170928);
    border-radius: 8px;
    opacity: 0.90;
}
.btn-cta-bg-gradient-b {
    position: absolute;
    inset: 2px;
    background: linear-gradient(to bottom, rgba(101, 67, 88, 0.4), #1d0d33, rgba(47, 13, 100, 0.3));
    border-radius: 8px;
    opacity: 0.80;
}
.btn-cta-bg-gradient-br {
    position: absolute;
    inset: 2px;
    background: linear-gradient(to bottom right, rgba(199, 135, 246, 0.1), #1d0d33, rgba(42, 23, 54, 0.5));
    border-radius: 8px;
}
.btn-cta-shadow {
    position: absolute;
    inset: 2px;
    box-shadow: inset 0 0 15px rgba(199, 135, 246, 0.15);
    border-radius: 8px;
}
.btn-cta-label-container {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    z-index: 10;
}
.btn-cta-label {
    font-family: var(--font-main);
    font-size: 1.1rem;
    font-weight: 300;
    background: linear-gradient(to bottom, #D69DDE, #B873F8);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 0 12px rgba(199, 135, 246, 0.4));
    letter-spacing: -0.05em;
}
.btn-cta-hover-bg {
    position: absolute;
    inset: 2px;
    opacity: 0;
    transition: opacity 0.3s ease;
    background: linear-gradient(to right, rgba(42, 23, 54, 0.2), rgba(199, 135, 246, 0.1), rgba(42, 23, 54, 0.2));
    border-radius: 8px;
}
.btn-cta:hover .btn-cta-hover-bg {
    opacity: 1;
}
```

### React
```tsx
import * as React from "react"
import { Button } from "@/components/ui/button";
import { cn } from "@/lib/utils";

interface ButtonCtaProps extends React.ButtonHTMLAttributes<HTMLButtonElement> {
    label?: string;
    className?: string;
}

function ButtonCta({ label = "Get Access", className, ...props }: ButtonCtaProps) {
    return (
        <Button
            variant="ghost"
            className={cn(
                "group relative w-1/2 h-12 px-4 rounded-lg overflow-hidden transition-all duration-500",
                className
            )}
            {...props}
        >
            <div className="absolute inset-0 rounded-lg p-[2px] bg-gradient-to-b from-[#654358] via-[#17092A] to-[#2F0D64]">
                <div className="absolute inset-0 bg-[#170928] rounded-lg opacity-90" />
            </div>

            <div className="absolute inset-[2px] bg-[#170928] rounded-lg opacity-95" />

            <div className="absolute inset-[2px] bg-gradient-to-r from-[#170928] via-[#1d0d33] to-[#170928] rounded-lg opacity-90" />
            <div className="absolute inset-[2px] bg-gradient-to-b from-[#654358]/40 via-[#1d0d33] to-[#2F0D64]/30 rounded-lg opacity-80" />
            <div className="absolute inset-[2px] bg-gradient-to-br from-[#C787F6]/10 via-[#1d0d33] to-[#2A1736]/50 rounded-lg" />

            <div className="absolute inset-[2px] shadow-[inset_0_0_15px_rgba(199,135,246,0.15)] rounded-lg" />

            <div className="relative flex items-center justify-center gap-2">
                <span className="text-lg font-light bg-gradient-to-b from-[#D69DDE] to-[#B873F8] bg-clip-text text-transparent drop-shadow-[0_0_12px_rgba(199,135,246,0.4)] tracking-tighter">
                    {label}
                </span>
            </div>

            <div className="absolute inset-[2px] opacity-0 transition-opacity duration-300 bg-gradient-to-r from-[#2A1736]/20 via-[#C787F6]/10 to-[#2A1736]/20 group-hover:opacity-100 rounded-lg" />
        </Button>
    );
}

export { ButtonCta }
```

---

## CTA #8: Jello Hover Discover Button
*A rounded blue button with a thick sky-blue border that features a jello-wiggle SVG arrow hover animation.*

### Project Prerequisites & Integration Instructions
* **No Dependency**: Standard HTML/CSS, clean vanilla animations.

### HTML
```html
<div class="jello-btn-wrapper">
    <button class="jello-btn" onclick="showToast('Exploring items...')">
      <span class="jello-btn-text">Discover</span>
      <span class="jello-btn-svg">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="50"
          height="20"
          viewBox="0 0 38 15"
          fill="none"
        >
          <path
            fill="white"
            d="M10 7.519l-.939-.344h0l.939.344zm14.386-1.205l-.981-.192.981.192zm1.276 5.509l.537.843.148-.094.107-.139-.792-.611zm4.819-4.304l-.385-.923h0l.385.923zm7.227.707a1 1 0 0 0 0-1.414L31.343.448a1 1 0 0 0-1.414 0 1 1 0 0 0 0 1.414l5.657 5.657-5.657 5.657a1 1 0 0 0 1.414 1.414l6.364-6.364zM1 7.519l.554.833.029-.019.094-.061.361-.23 1.277-.77c1.054-.609 2.397-1.32 3.629-1.787.617-.234 1.17-.392 1.623-.455.477-.066.707-.008.788.034.025.013.031.021.039.034a.56.56 0 0 1 .058.235c.029.327-.047.906-.39 1.842l1.878.689c.383-1.044.571-1.949.505-2.705-.072-.815-.45-1.493-1.16-1.865-.627-.329-1.358-.332-1.993-.244-.659.092-1.367.305-2.056.566-1.381.523-2.833 1.297-3.921 1.925l-1.341.808-.385.245-.104.068-.028.018c-.011.007-.011.007.543.84zm8.061-.344c-.198.54-.328 1.038-.36 1.484-.032.441.024.94.325 1.364.319.45.786.64 1.21.697.403.054.824-.001 1.21-.09.775-.179 1.694-.566 2.633-1.014l3.023-1.554c2.115-1.122 4.107-2.168 5.476-2.524.329-.086.573-.117.742-.115s.195.038.161.014c-.15-.105.085-.139-.076.685l1.963.384c.192-.98.152-2.083-.74-2.707-.405-.283-.868-.37-1.28-.376s-.849.069-1.274.179c-1.65.43-3.888 1.621-5.909 2.693l-2.948 1.517c-.92.439-1.673.743-2.221.87-.276.064-.429.065-.492.057-.043-.006.066.003.155.127.07.099.024.131.038-.063.014-.187.078-.49.243-.94l-1.878-.689zm14.343-1.053c-.361 1.844-.474 3.185-.413 4.161.059.95.294 1.72.811 2.215.567.544 1.242.546 1.664.459a2.34 2.34 0 0 0 .502-.167l.15-.076.049-.028.018-.011c.013-.008.013-.008-.524-.852l-.536-.844.019-.012c-.038.018-.064.027-.084.032-.037.008.053-.013.125.056.021.02-.151-.135-.198-.895-.046-.734.034-1.887.38-3.652l-1.963-.384zm2.257 5.701l.791.611.024-.031.08-.101.311-.377 1.093-1.213c.922-.954 2.005-1.894 2.904-2.27l-.771-1.846c-1.31.547-2.637 1.758-3.572 2.725l-1.184 1.314-.341.414-.093.117-.025.032c-.01.013-.01.013.781.624zm5.204-3.381c.989-.413 1.791-.42 2.697-.307.871.108 2.083.385 3.437.385v-2c-1.197 0-2.041-.226-3.19-.369-1.114-.139-2.297-.146-3.715.447l.771 1.846z"
          ></path>
        </svg>
      </span>
    </button>
</div>
```

### CSS
```css
.jello-btn-wrapper {
  display: flex;
  justify-content: center;
  width: 100%;
}
.jello-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 16px 32px;
  background-color: #006aff;
  border: 8px solid #c0dfff;
  color: white;
  gap: 8px;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s;
}
.jello-btn-text {
  font-size: 1.7em;
  font-weight: 700;
  letter-spacing: 1px;
}
.jello-btn-svg {
  padding-top: 5px;
  height: 100%;
  width: fit-content;
}
.jello-btn-svg svg {
  width: 50px;
  height: 30px;
}
.jello-btn:hover {
  border: 8px solid #b1d8ff;
  background-color: #1b7aff;
}
.jello-btn:active {
  border: 5px solid #c0dfff;
}
.jello-btn:hover .jello-btn-svg svg {
  animation: jello-vertical-anim 0.9s both;
  transform-origin: left;
}

@keyframes jello-vertical-anim {
  0% {
    transform: scale3d(1, 1, 1);
  }
  30% {
    transform: scale3d(0.75, 1.25, 1);
  }
  40% {
    transform: scale3d(1.25, 0.75, 1);
  }
  50% {
    transform: scale3d(0.85, 1.15, 1);
  }
  65% {
    transform: scale3d(1.05, 0.95, 1);
  }
  75% {
    transform: scale3d(0.95, 1.05, 1);
  }
  100% {
    transform: scale3d(1, 1, 1);
  }
}
```

### React
```tsx
import React from "react";

export default function JelloDiscoverCTA() {
  return (
    <div className="flex items-center justify-center w-full">
      <button className="flex items-center justify-center px-8 py-4 bg-[#006aff] border-[8px] border-[#c0dfff] text-white gap-2 rounded-[50px] cursor-pointer transition-all duration-300 hover:border-[#b1d8ff] hover:bg-[#1b7aff] active:border-[5px] group">
        <span className="text-[1.7em] font-bold tracking-wider">Discover</span>
        <span className="pt-1 h-full w-fit group-hover:animate-[jello-vertical_0.9s_both] origin-left">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="50"
            height="20"
            viewBox="0 0 38 15"
            fill="none"
          >
            <path
              fill="white"
              d="M10 7.519l-.939-.344h0l.939.344zm14.386-1.205l-.981-.192.981.192zm1.276 5.509l.537.843.148-.094.107-.139-.792-.611zm4.819-4.304l-.385-.923h0l.385.923zm7.227.707a1 1 0 0 0 0-1.414L31.343.448a1 1 0 0 0-1.414 0 1 1 0 0 0 0 1.414l5.657 5.657-5.657 5.657a1 1 0 0 0 1.414 1.414l6.364-6.364zM1 7.519l.554.833.029-.019.094-.061.361-.23 1.277-.77c1.054-.609 2.397-1.32 3.629-1.787.617-.234 1.17-.392 1.623-.455.477-.066.707-.008.788.034.025.013.031.021.039.034a.56.56 0 0 1 .058.235c.029.327-.047.906-.39 1.842l1.878.689c.383-1.044.571-1.949.505-2.705-.072-.815-.45-1.493-1.16-1.865-.627-.329-1.358-.332-1.993-.244-.659.092-1.367.305-2.056.566-1.381.523-2.833 1.297-3.921 1.925l-1.341.808-.385.245-.104.068-.028.018c-.011.007-.011.007.543.84zm8.061-.344c-.198.54-.328 1.038-.36 1.484-.032.441.024.94.325 1.364.319.45.786.64 1.21.697.403.054.824-.001 1.21-.09.775-.179 1.694-.566 2.633-1.014l3.023-1.554c2.115-1.122 4.107-2.168 5.476-2.524.329-.086.573-.117.742-.115s.195.038.161.014c-.15-.105.085-.139-.076.685l1.963.384c.192-.98.152-2.083-.74-2.707-.405-.283-.868-.37-1.28-.376s-.849.069-1.274.179c-1.65.43-3.888 1.621-5.909 2.693l-2.948 1.517c-.92.439-1.673.743-2.221.87-.276.064-.429.065-.492.057-.043-.006.066.003.155.127.07.099.024.131.038-.063.014-.187.078-.49.243-.94l-1.878-.689zm14.343-1.053c-.361 1.844-.474 3.185-.413 4.161.059.95.294 1.72.811 2.215.567.544 1.242.546 1.664.459a2.34 2.34 0 0 0 .502-.167l.15-.076.049-.028.018-.011c.013-.008.013-.008-.524-.852l-.536-.844.019-.012c-.038.018-.064.027-.084.032-.037.008.053-.013.125.056.021.02-.151-.135-.198-.895-.046-.734.034-1.887.38-3.652l-1.963-.384zm2.257 5.701l.791.611.024-.031.08-.101.311-.377 1.093-1.213c.922-.954 2.005-1.894 2.904-2.27l-.771-1.846c-1.31.547-2.637 1.758-3.572 2.725l-1.184 1.314-.341.414-.093.117-.025.032c-.01.013-.01.013.781.624zm5.204-3.381c.989-.413 1.791-.42 2.697-.307.871.108 2.083.385 3.437.385v-2c-1.197 0-2.041-.226-3.19-.369-1.114-.139-2.297-.146-3.715.447l.771 1.846z"
            />
          </svg>
        </span>
      </button>
    </div>
  );
}
```

---

## CTA #9: Star Sparkle Letter-Anim Button
*A dark themed button with sparkle SVG icons and animated letters that glow and slide on focus/hover.*

### Project Prerequisites & Integration Instructions
* **Typography**: Import Google Fonts or Tailwind Sans family for best readability.

### HTML
```html
<div class="sparkle-btn-wrapper">
  <button class="sparkle-btn" onclick="showToast('Action Initiated!')">
    <svg class="sparkle-btn-svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M9.813 15.904 9 18.75l-.813-2.846a4.5 4.5 0 0 0-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 0 0 3.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 0 0 3.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 0 0-3.09 3.09ZM18.259 8.715 18 9.75l-.259-1.035a3.375 3.375 0 0 0-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 0 0 2.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 0 0 2.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 0 0-2.456 2.456ZM16.894 20.567 16.5 21.75l-.394-1.183a2.25 2.25 0 0 0-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 0 0 1.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 0 0 1.423 1.423l1.183.394-1.183.394a2.25 2.25 0 0 0-1.423 1.423Z"
      ></path>
    </svg>

    <div class="sparkle-txt-wrapper">
      <div class="sparkle-txt-1">
        <span class="sparkle-btn-letter">G</span>
        <span class="sparkle-btn-letter">e</span>
        <span class="sparkle-btn-letter">n</span>
        <span class="sparkle-btn-letter">e</span>
        <span class="sparkle-btn-letter">r</span>
        <span class="sparkle-btn-letter">a</span>
        <span class="sparkle-btn-letter">t</span>
        <span class="sparkle-btn-letter">e</span>
      </div>
      <div class="sparkle-txt-2">
        <span class="sparkle-btn-letter">G</span>
        <span class="sparkle-btn-letter">e</span>
        <span class="sparkle-btn-letter">n</span>
        <span class="sparkle-btn-letter">e</span>
        <span class="sparkle-btn-letter">r</span>
        <span class="sparkle-btn-letter">a</span>
        <span class="sparkle-btn-letter">t</span>
        <span class="sparkle-btn-letter">i</span>
        <span class="sparkle-btn-letter">n</span>
        <span class="sparkle-btn-letter">g</span>
      </div>
    </div>
  </button>
</div>
```

### CSS
```css
.sparkle-btn-wrapper {
  position: relative;
  display: inline-block;
}

.sparkle-btn {
  --border-radius: 24px;
  --padding: 4px;
  --transition: 0.4s;
  --button-color: #101010;
  --highlight-color-hue: 210deg;

  user-select: none;
  display: flex;
  justify-content: center;
  padding: 0.5em 0.5em 0.5em 1.1em;
  font-family: "Poppins", "Inter", "Segoe UI", sans-serif;
  font-size: 1em;
  font-weight: 400;

  background-color: var(--button-color);

  box-shadow:
    inset 0px 1px 1px rgba(255, 255, 255, 0.2),
    inset 0px 2px 2px rgba(255, 255, 255, 0.15),
    inset 0px 4px 4px rgba(255, 255, 255, 0.1),
    inset 0px 8px 8px rgba(255, 255, 255, 0.05),
    inset 0px 16px 16px rgba(255, 255, 255, 0.05),
    0px -1px 1px rgba(0, 0, 0, 0.02),
    0px -2px 2px rgba(0, 0, 0, 0.03),
    0px -4px 4px rgba(0, 0, 0, 0.05),
    0px -8px 8px rgba(0, 0, 0, 0.06),
    0px -16px 16px rgba(0, 0, 0, 0.08);

  border: solid 1px rgba(255, 255, 255, 0.13);
  border-radius: var(--border-radius);
  cursor: pointer;

  transition:
    box-shadow var(--transition),
    border var(--transition),
    background-color var(--transition);
}
.sparkle-btn::before {
  content: "";
  position: absolute;
  top: calc(0px - var(--padding));
  left: calc(0px - var(--padding));
  width: calc(100% + var(--padding) * 2);
  height: calc(100% + var(--padding) * 2);
  border-radius: calc(var(--border-radius) + var(--padding));
  pointer-events: none;
  background-image: linear-gradient(0deg, rgba(0,0,0,0.27), rgba(0,0,0,0.67));

  z-index: -1;
  transition:
    box-shadow var(--transition),
    filter var(--transition);
  box-shadow:
    0 -8px 8px -6px rgba(0,0,0,0) inset,
    0 -16px 16px -8px rgba(0,0,0,0) inset,
    1px 1px 1px rgba(255,255,255,0.13),
    2px 2px 2px rgba(255,255,255,0.06),
    -1px -1px 1px rgba(0,0,0,0.13),
    -2px -2px 2px rgba(0,0,0,0.06);
}
.sparkle-btn::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  pointer-events: none;
  background-image: linear-gradient(
    0deg,
    #fff,
    hsl(var(--highlight-color-hue), 100%, 70%),
    hsla(var(--highlight-color-hue), 100%, 70%, 50%),
    8%,
    transparent
  );
  background-position: 0 0;
  opacity: 0;
  transition:
    opacity var(--transition),
    filter var(--transition);
}

.sparkle-btn-letter {
  position: relative;
  display: inline-block;
  color: rgba(255,255,255,0.33);
  animation: letter-anim-sparkle 2s ease-in-out infinite;
  transition:
    color var(--transition),
    text-shadow var(--transition),
    opacity var(--transition);
}

@keyframes letter-anim-sparkle {
  50% {
    text-shadow: 0 0 3px rgba(255,255,255,0.53);
    color: #fff;
  }
}

.sparkle-btn-svg {
  flex-grow: 1;
  height: 24px;
  width: 24px;
  margin-right: 0.5rem;
  fill: #e8e8e8;
  animation: flicker-sparkle 2s linear infinite;
  animation-delay: 0.5s;
  filter: drop-shadow(0 0 2px rgba(255,255,255,0.6));
  transition:
    fill var(--transition),
    filter var(--transition),
    opacity var(--transition);
}
@keyframes flicker-sparkle {
  50% {
    opacity: 0.3;
  }
}

.sparkle-txt-wrapper {
  position: relative;
  display: flex;
  align-items: center;
  min-width: 6.4em;
}
.sparkle-txt-1,
.sparkle-txt-2 {
  position: absolute;
  word-spacing: -1em;
}
.sparkle-txt-1 {
  animation: appear-anim-sparkle 1s ease-in-out forwards;
}
.sparkle-txt-2 {
  opacity: 0;
}
@keyframes appear-anim-sparkle {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.sparkle-btn:focus .sparkle-txt-1 {
  animation: opacity-anim-sparkle 0.3s ease-in-out forwards;
  animation-delay: 1s;
}
.sparkle-btn:focus .sparkle-txt-2 {
  animation: opacity-anim-sparkle 0.3s ease-in-out reverse forwards;
  animation-delay: 1s;
}
@keyframes opacity-anim-sparkle {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

.sparkle-btn:focus .sparkle-btn-letter {
  animation:
    focused-letter-anim-sparkle 1s ease-in-out forwards,
    letter-anim-sparkle 1.2s ease-in-out infinite;
  animation-delay: 0s, 1s;
}
@keyframes focused-letter-anim-sparkle {
  0%,
  100% {
    filter: blur(0px);
  }
  50% {
    transform: scale(2);
    filter: blur(10px) brightness(150%)
      drop-shadow(-36px 12px 12px hsl(var(--highlight-color-hue), 100%, 70%));
  }
}
.sparkle-btn:focus .sparkle-btn-svg {
  animation-duration: 1.2s;
  animation-delay: 0.2s;
}

.sparkle-btn:focus::before {
  box-shadow:
    0 -8px 12px -6px rgba(255,255,255,0.2) inset,
    0 -16px 16px -8px hsla(var(--highlight-color-hue), 100%, 70%, 20%) inset,
    1px 1px 1px rgba(255,255,255,0.2),
    2px 2px 2px rgba(255,255,255,0.06),
    -1px -1px 1px rgba(0,0,0,0.13),
    -2px -2px 2px rgba(0,0,0,0.06);
}
.sparkle-btn:focus::after {
  opacity: 0.6;
  mask-image: linear-gradient(0deg, #fff, transparent);
  filter: brightness(100%);
}

.sparkle-btn-letter:nth-child(1),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(1) {
  animation-delay: 0s;
}
.sparkle-btn-letter:nth-child(2),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(2) {
  animation-delay: 0.08s;
}
.sparkle-btn-letter:nth-child(3),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(3) {
  animation-delay: 0.16s;
}
.sparkle-btn-letter:nth-child(4),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(4) {
  animation-delay: 0.24s;
}
.sparkle-btn-letter:nth-child(5),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(5) {
  animation-delay: 0.32s;
}
.sparkle-btn-letter:nth-child(6),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(6) {
  animation-delay: 0.4s;
}
.sparkle-btn-letter:nth-child(7),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(7) {
  animation-delay: 0.48s;
}
.sparkle-btn-letter:nth-child(8),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(8) {
  animation-delay: 0.56s;
}
.sparkle-btn-letter:nth-child(9),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(9) {
  animation-delay: 0.64s;
}
.sparkle-btn-letter:nth-child(10),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(10) {
  animation-delay: 0.72s;
}
.sparkle-btn-letter:nth-child(11),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(11) {
  animation-delay: 0.8s;
}
.sparkle-btn-letter:nth-child(12),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(12) {
  animation-delay: 0.88s;
}
.sparkle-btn-letter:nth-child(13),
.sparkle-btn:focus .sparkle-btn-letter:nth-child(13) {
  animation-delay: 0.96s;
}

.sparkle-btn:active {
  border: solid 1px hsla(var(--highlight-color-hue), 100%, 80%, 70%);
  background-color: hsla(var(--highlight-color-hue), 50%, 20%, 0.5);
}
.sparkle-btn:active::before {
  box-shadow:
    0 -8px 12px -6px rgba(255,255,255,0.67) inset,
    0 -16px 16px -8px hsla(var(--highlight-color-hue), 100%, 70%, 80%) inset,
    1px 1px 1px rgba(255,255,255,0.27),
    2px 2px 2px rgba(255,255,255,0.13),
    -1px -1px 1px rgba(0,0,0,0.13),
    -2px -2px 2px rgba(0,0,0,0.06);
}
.sparkle-btn:active::after {
  opacity: 1;
  mask-image: linear-gradient(0deg, #fff, transparent);
  filter: brightness(200%);
}
.sparkle-btn:active .sparkle-btn-letter {
  text-shadow: 0 0 1px hsla(var(--highlight-color-hue), 100%, 90%, 90%);
  animation: none;
}

.sparkle-btn:hover {
  border: solid 1px hsla(var(--highlight-color-hue), 100%, 80%, 40%);
}

.sparkle-btn:hover::before {
  box-shadow:
    0 -8px 8px -6px rgba(255,255,255,0.67) inset,
    0 -16px 16px -8px hsla(var(--highlight-color-hue), 100%, 70%, 30%) inset,
    1px 1px 1px rgba(255,255,255,0.13),
    2px 2px 2px rgba(255,255,255,0.06),
    -1px -1px 1px rgba(0,0,0,0.13),
    -2px -2px 2px rgba(0,0,0,0.06);
}

.sparkle-btn:hover::after {
  opacity: 1;
  mask-image: linear-gradient(0deg, #fff, transparent);
}

.sparkle-btn:hover .sparkle-btn-svg {
  fill: #fff;
  filter: drop-shadow(0 0 3px hsl(var(--highlight-color-hue), 100%, 70%))
    drop-shadow(0 -4px 6px rgba(0,0,0,0.56));
  animation: none;
}
```

### React
```tsx
import React from "react";

export default function SparkleGenerateCTA() {
  const letters1 = ["G", "e", "n", "e", "r", "a", "t", "e"];
  const letters2 = ["G", "e", "n", "e", "r", "a", "t", "i", "n", "g"];

  return (
    <div className="relative inline-block">
      <button className="flex justify-center p-[0.5em_0.5em_0.5em_1.1em] border border-white/13 rounded-[24px] bg-[#101010] cursor-pointer transition-all duration-400 hover:border-sky-400/40 active:border-sky-400/70 active:bg-sky-950/50 group focus:outline-none shadow-[inset_0_1px_1px_rgba(255,255,255,0.2),_inset_0_2px_2px_rgba(255,255,255,0.15)] before:absolute before:inset-[-4px] before:rounded-[28px] before:bg-gradient-to-b before:from-black/27 before:to-black/67 before:z-[-1] before:transition-all before:duration-400 before:shadow-[inset_0_-8px_8px_-6px_transparent,_1px_1px_1px_rgba(255,255,255,0.13)] hover:before:shadow-[inset_0_-8px_8px_-6px_rgba(255,255,255,0.67),_1px_1px_1px_rgba(255,255,255,0.13)] after:absolute after:inset-0 after:rounded-inherit after:bg-gradient-to-t after:from-white after:to-sky-300 after:opacity-0 hover:after:opacity-100 after:transition-all after:duration-400">
        <svg className="flex-grow h-6 w-6 mr-2 fill-[#e8e8e8] animate-[flicker-sparkle_2s_linear_infinite] group-hover:fill-white group-hover:drop-shadow-[0_0_3px_#38bdf8] group-hover:animate-none transition-all duration-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
          <path
            strokeLinecap="round"
            strokeLinejoin="round"
            d="M9.813 15.904 9 18.75l-.813-2.846a4.5 4.5 0 0 0-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 0 0 3.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 0 0 3.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 0 0-3.09 3.09ZM18.259 8.715 18 9.75l-.259-1.035a3.375 3.375 0 0 0-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 0 0 2.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 0 0 2.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 0 0-2.456 2.456ZM16.894 20.567 16.5 21.75l-.394-1.183a2.25 2.25 0 0 0-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 0 0 1.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 0 0 1.423 1.423l1.183.394-1.183.394a2.25 2.25 0 0 0-1.423 1.423Z"
          ></path>
        </svg>

        <div className="relative flex items-center min-w-[6.4em] text-white">
          <div className="absolute word-spacing-[-1em] transition-opacity duration-400 group-focus:opacity-0">
            {letters1.map((letter, i) => (
              <span 
                key={i} 
                style={{ animationDelay: `${i * 0.08}s` }} 
                className="relative inline-block text-white/33 animate-[letter-anim-sparkle_2s_ease-in-out_infinite]"
              >
                {letter}
              </span>
            ))}
          </div>
          <div className="absolute word-spacing-[-1em] opacity-0 group-focus:opacity-100 transition-opacity duration-400">
            {letters2.map((letter, i) => (
              <span 
                key={i} 
                style={{ animationDelay: `${i * 0.08}s` }} 
                className="relative inline-block text-white/33 animate-[letter-anim-sparkle_2s_ease-in-out_infinite]"
              >
                {letter}
              </span>
            ))}
          </div>
        </div>
      </button>
    </div>
  );
}
```


