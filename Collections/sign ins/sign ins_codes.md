# Premium Custom Sign In Forms Code Database

This file contains the complete, self-contained HTML, CSS, and JavaScript/React code snippets for all **12 Premium Sign In Components** featured in the interactive showcase. Each component is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Form #1: Canvas Reveal Developer Sign In](#form-1-canvas-reveal-developer-sign-in)
2. [Form #2: Aurora Glowing Input Sign In](#form-2-aurora-glowing-input-sign-in)
3. [Form #3: Glassmorphic Floating Bubbles Form](#form-3-glassmorphic-floating-bubbles-form)
4. [Form #4: Spotlight Cursor Tracking Sign In](#form-4-spotlight-cursor-tracking-sign-in)
5. [Form #5: Sliding Underline Border Form](#form-5-sliding-underline-border-form)
6. [Form #6: Password Reveal Shield Sign In](#form-6-password-reveal-shield-sign-in)
7. [Form #7: Neumorphic Soft-Glow Form](#form-7-neumorphic-soft-glow-form)
8. [Form #8: Biometric Fingerprint Scan Mock Sign In](#form-8-biometric-fingerprint-scan-mock-sign-in)
9. [Form #9: Sliding Segmented Toggle Form](#form-9-sliding-segmented-toggle-form)
10. [Form #10: Minimalist Border Draw Input Form](#form-10-minimalist-border-draw-input-form)
11. [Form #11: Cyber Glow Access Node Sheet](#form-11-cyber-glow-access-node-sheet)
12. [Form #12: Matrix Digital Code Grid Keypad](#form-12-matrix-digital-code-grid-keypad)

---

## Form #1: Canvas Reveal Developer Sign In
*An advanced developer sign-in component featuring a custom mini navbar, multiple transition steps (Email entry -> 6-digit verification code input -> success state), and interactive background canvas point-matrix reveals.*

### Project Prerequisites & Integration Instructions
* **shadcn-ui project structure**: Place the component at `/components/ui/sign-in-flow-1.tsx` and the demo usage at `/components/ui/demo.tsx`. If `/components/ui` does not exist, initialize it with `npx shadcn-ui@latest init` to ensure absolute component paths (like `@/components/ui/sign-in-flow-1`) function properly across import alias networks.
* **External dependencies**: `npm install three @types/three @react-three/fiber framer-motion lucide-react`
* **Tailwind config keyframes**: Verify you have standard animation keyframes (such as fade-ins) configured.

### HTML
```html
<div class="form-box-canvas-reveal" id="signin-reveal-1">
    <canvas class="reveal-canvas" id="canvas-reveal-1"></canvas>
    <div class="reveal-navbar">
        <div class="reveal-logo">
            <span class="dot top-dot"></span>
            <span class="dot left-dot"></span>
            <span class="dot right-dot"></span>
            <span class="dot bottom-dot"></span>
        </div>
        <div class="reveal-nav-links">
            <a href="#">Manifesto</a>
            <a href="#">Careers</a>
            <a href="#">Discover</a>
        </div>
        <div class="reveal-nav-actions">
            <button class="nav-login-btn">LogIn</button>
            <button class="nav-signup-btn">Signup</button>
        </div>
    </div>
    <div class="reveal-form-container">
        <div class="reveal-step active" id="reveal-step-email-1">
            <h2>Welcome Developer</h2>
            <p class="subtitle">Your sign in component</p>
            <button class="google-signin-btn">
                <span class="google-icon">G</span>
                <span>Sign in with Google</span>
            </button>
            <div class="divider">
                <span class="line"></span>
                <span class="divider-text">or</span>
                <span class="line"></span>
            </div>
            <form onsubmit="goToRevealCode(1); return false;">
                <div class="email-input-wrap">
                    <input type="email" placeholder="info@gmail.com" required />
                    <button type="submit" class="email-submit-btn">
                        <span class="arrow-container">
                            <span class="arrow-text">→</span>
                        </span>
                    </button>
                </div>
            </form>
            <p class="legal-text">
                By signing up, you agree to the <a href="#">MSA</a>, <a href="#">Product Terms</a>, <a href="#">Policies</a>, <a href="#">Privacy Notice</a>, and <a href="#">Cookie Notice</a>.
            </p>
        </div>
        <div class="reveal-step" id="reveal-step-code-1">
            <h2>We sent you a code</h2>
            <p class="subtitle">Please enter it</p>
            <div class="code-inputs-container">
                <div class="code-inputs-wrapper">
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleRevealCodeInput(1, 0, this)" onkeydown="handleRevealCodeKeydown(1, 0, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleRevealCodeInput(1, 1, this)" onkeydown="handleRevealCodeKeydown(1, 1, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleRevealCodeInput(1, 2, this)" onkeydown="handleRevealCodeKeydown(1, 2, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleRevealCodeInput(1, 3, this)" onkeydown="handleRevealCodeKeydown(1, 3, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleRevealCodeInput(1, 4, this)" onkeydown="handleRevealCodeKeydown(1, 4, event)" class="code-input" />
                    <span class="code-sep">|</span>
                    <input type="text" maxlength="1" inputmode="numeric" oninput="handleRevealCodeInput(1, 5, this)" onkeydown="handleRevealCodeKeydown(1, 5, event)" class="code-input" />
                </div>
            </div>
            <p class="resend-code-btn">Resend code</p>
            <div class="btn-group">
                <button class="back-btn" onclick="goToRevealEmail(1)">Back</button>
                <button class="continue-btn disabled" id="continue-btn-1" onclick="submitRevealCode(1)" disabled>Continue</button>
            </div>
            <p class="legal-text">
                By signing up, you agree to the <a href="#">MSA</a>, <a href="#">Product Terms</a>, <a href="#">Policies</a>, <a href="#">Privacy Notice</a>, and <a href="#">Cookie Notice</a>.
            </p>
        </div>
        <div class="reveal-step" id="reveal-step-success-1">
            <h2>You're in!</h2>
            <p class="subtitle">Welcome</p>
            <div class="success-icon-wrap">
                <div class="success-circle">
                    <svg viewBox="0 0 20 20" fill="currentColor" width="22" height="22">
                        <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"></path>
                    </svg>
                </div>
            </div>
            <button class="success-continue-btn" onclick="resetRevealForm(1)">Continue to Dashboard</button>
        </div>
    </div>
</div>
```

### CSS
```css
.form-box-canvas-reveal {
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
.reveal-navbar {
    position: absolute;
    top: 10px;
    left: 10px;
    right: 10px;
    z-index: 3;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 6px 12px;
    background: rgba(31, 31, 31, 0.35);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 20px;
}
.reveal-logo {
    width: 16px;
    height: 16px;
    position: relative;
}
.reveal-logo .dot {
    position: absolute;
    width: 4px;
    height: 4px;
    background: rgba(255, 255, 255, 0.8);
    border-radius: 50%;
}
.reveal-logo .top-dot { top: 0; left: 6px; }
.reveal-logo .left-dot { left: 0; top: 6px; }
.reveal-logo .right-dot { right: 0; top: 6px; }
.reveal-logo .bottom-dot { bottom: 0; left: 6px; }

.reveal-nav-links {
    display: flex;
    gap: 12px;
}
.reveal-nav-links a {
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.65rem;
    font-weight: 500;
    transition: color 0.2s;
}
.reveal-nav-links a:hover {
    color: #fff;
}
.reveal-nav-actions {
    display: flex;
    gap: 6px;
}
.nav-login-btn {
    background: rgba(31, 31, 31, 0.62);
    color: #cbd5e1;
    border: 1px solid rgba(255,255,255,0.15);
    font-size: 0.58rem;
    padding: 3px 8px;
    border-radius: 12px;
    cursor: pointer;
    transition: all 0.2s;
}
.nav-login-btn:hover {
    border-color: rgba(255,255,255,0.4);
    color: #fff;
}
.nav-signup-btn {
    background: linear-gradient(135deg, #fff 0%, #cbd5e1 100%);
    color: #000;
    border: none;
    font-size: 0.58rem;
    padding: 3px 8px;
    border-radius: 12px;
    cursor: pointer;
    font-weight: 600;
    transition: opacity 0.2s;
}
.nav-signup-btn:hover {
    opacity: 0.9;
}
.reveal-form-container {
    position: relative;
    z-index: 2;
    width: 280px;
    padding-top: 35px;
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
    font-size: 1rem;
    color: #fff;
    margin-bottom: 2px;
    font-weight: 600;
}
.reveal-step .subtitle {
    font-size: 0.7rem;
    color: rgba(255, 255, 255, 0.6);
    margin-bottom: 12px;
}
.google-signin-btn {
    width: 100%;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 20px;
    color: #fff;
    padding: 6px 12px;
    font-size: 0.7rem;
    font-weight: 500;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    cursor: pointer;
    transition: background 0.2s;
}
.google-signin-btn:hover {
    background: rgba(255, 255, 255, 0.08);
}
.google-icon {
    font-weight: bold;
    font-family: sans-serif;
}
.divider {
    display: flex;
    align-items: center;
    width: 100%;
    margin: 10px 0;
}
.divider .line {
    flex: 1;
    height: 1px;
    background: rgba(255, 255, 255, 0.08);
}
.divider-text {
    color: rgba(255, 255, 255, 0.3);
    font-size: 0.6rem;
    padding: 0 8px;
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
    font-size: 0.52rem;
    color: rgba(255, 255, 255, 0.35);
    margin-top: 15px;
    line-height: 1.4;
}
.legal-text a {
    color: rgba(255, 255, 255, 0.35);
    text-decoration: underline;
}
.legal-text a:hover {
    color: rgba(255, 255, 255, 0.6);
}

/* Step 2 specific */
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
.resend-code-btn {
    font-size: 0.65rem;
    color: rgba(255, 255, 255, 0.5);
    cursor: pointer;
    text-decoration: underline;
    margin-bottom: 12px;
    transition: color 0.2s;
}
.resend-code-btn:hover {
    color: rgba(255, 255, 255, 0.8);
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
.back-btn:hover {
    opacity: 0.9;
}
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
.continue-btn:not(.disabled):hover {
    opacity: 0.9;
}

/* Step 3 specific */
.success-icon-wrap {
    margin: 10px 0;
}
.success-circle {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background: linear-gradient(135deg, #fff 0%, #cbd5e1 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #000;
    box-shadow: 0 4px 10px rgba(255,255,255,0.1);
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
.success-continue-btn:hover {
    opacity: 0.9;
}
```

### JavaScript
```javascript
window.initRevealCanvas = function(id) {
    const box = document.getElementById(`signin-reveal-${id}`);
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

window.goToRevealCode = function(id) {
    const stepEmail = document.getElementById(`reveal-step-email-${id}`);
    const stepCode = document.getElementById(`reveal-step-code-${id}`);
    if (stepEmail && stepCode) {
        stepEmail.classList.remove('active');
        stepCode.classList.add('active');
        const inputs = stepCode.querySelectorAll('.code-input');
        if (inputs.length > 0) {
            setTimeout(() => inputs[0].focus(), 100);
        }
    }
};

window.goToRevealEmail = function(id) {
    const stepEmail = document.getElementById(`reveal-step-email-${id}`);
    const stepCode = document.getElementById(`reveal-step-code-${id}`);
    const stepSuccess = document.getElementById(`reveal-step-success-${id}`);
    
    if (stepEmail && stepCode) {
        stepEmail.classList.add('active');
        stepCode.classList.remove('active');
        if (stepSuccess) stepSuccess.classList.remove('active');
        
        const inputs = stepCode.querySelectorAll('.code-input');
        inputs.forEach(input => input.value = '');
        const continueBtn = document.getElementById(`continue-btn-${id}`);
        if (continueBtn) {
            continueBtn.classList.add('disabled');
            continueBtn.disabled = true;
        }
        
        const box = document.getElementById(`signin-reveal-${id}`);
        if (box && box.triggerReverse) {
            box.triggerReverse(false);
        }
    }
};

window.handleRevealCodeInput = function(id, index, el) {
    const stepCode = document.getElementById(`reveal-step-code-${id}`);
    const inputs = stepCode.querySelectorAll('.code-input');
    const val = el.value;
    
    if (val.length >= 1) {
        el.value = val.slice(0, 1);
        if (index < 5) {
            inputs[index + 1].focus();
        }
    }
    
    let allFilled = true;
    inputs.forEach(input => {
        if (!input.value) allFilled = false;
    });
    
    const continueBtn = document.getElementById(`continue-btn-${id}`);
    if (allFilled) {
        continueBtn.classList.remove('disabled');
        continueBtn.disabled = false;
        if (index === 5) {
            submitRevealCode(id);
        }
    } else {
        continueBtn.classList.add('disabled');
        continueBtn.disabled = true;
    }
};

window.handleRevealCodeKeydown = function(id, index, event) {
    const stepCode = document.getElementById(`reveal-step-code-${id}`);
    const inputs = stepCode.querySelectorAll('.code-input');
    
    if (event.key === "Backspace" && !inputs[index].value && index > 0) {
        inputs[index - 1].focus();
    }
};

window.submitRevealCode = function(id) {
    const box = document.getElementById(`signin-reveal-${id}`);
    if (box && box.triggerReverse) {
        box.triggerReverse(true);
    }
    setTimeout(() => {
        const stepCode = document.getElementById(`reveal-step-code-${id}`);
        const stepSuccess = document.getElementById(`reveal-step-success-${id}`);
        if (stepCode && stepSuccess) {
            stepCode.classList.remove('active');
            stepSuccess.classList.add('active');
        }
    }, 1200);
};

window.resetRevealForm = function(id) {
    goToRevealEmail(id);
};

window.initRevealCanvas(1);
```

### React/Next.js (Source Component)
```tsx
"use client";

import React, { useState, useMemo, useRef, useEffect } from "react";
import { motion, AnimatePresence } from "framer-motion";
import Link from "next/link";
import { cn } from "@/lib/utils";
import { Canvas, useFrame, useThree } from "@react-three/fiber";
import * as THREE from "three";

export const CanvasRevealEffect = ({
  animationSpeed = 10,
  opacities = [0.3, 0.3, 0.3, 0.5, 0.5, 0.5, 0.8, 0.8, 0.8, 1],
  colors = [[0, 255, 255]],
  containerClassName,
  dotSize,
  showGradient = true,
  reverse = false,
}: {
  animationSpeed?: number;
  opacities?: number[];
  colors?: number[][];
  containerClassName?: string;
  dotSize?: number;
  showGradient?: boolean;
  reverse?: boolean;
}) => {
  return (
    <div className={cn("h-full relative w-full", containerClassName)}>
      <div className="h-full w-full">
        <DotMatrix
          colors={colors ?? [[0, 255, 255]]}
          dotSize={dotSize ?? 3}
          opacities={
            opacities ?? [0.3, 0.3, 0.3, 0.5, 0.5, 0.5, 0.8, 0.8, 0.8, 1]
          }
          shader={`
            ${reverse ? 'u_reverse_active' : 'false'}_;
            animation_speed_factor_${animationSpeed.toFixed(1)}_;
          `}
          center={["x", "y"]}
        />
      </div>
      {showGradient && (
         <div className="absolute inset-0 bg-gradient-to-t from-black to-transparent" />
      )}
    </div>
  );
};

const DotMatrix: React.FC<{
  colors?: number[][];
  opacities?: number[];
  totalSize?: number;
  dotSize?: number;
  shader?: string;
  center?: ("x" | "y")[];
}> = ({
  colors = [[0, 0, 0]],
  opacities = [0.04, 0.04, 0.04, 0.04, 0.04, 0.08, 0.08, 0.08, 0.08, 0.14],
  totalSize = 20,
  dotSize = 2,
  shader = "",
  center = ["x", "y"],
}) => {
  const uniforms = React.useMemo(() => {
    let colorsArray = [colors[0], colors[0], colors[0], colors[0], colors[0], colors[0]];
    if (colors.length === 2) {
      colorsArray = [colors[0], colors[0], colors[0], colors[1], colors[1], colors[1]];
    } else if (colors.length === 3) {
      colorsArray = [colors[0], colors[0], colors[1], colors[1], colors[2], colors[2]];
    }
    return {
      u_colors: {
        value: colorsArray.map((color) => [color[0] / 255, color[1] / 255, color[2] / 255]),
        type: "uniform3fv",
      },
      u_opacities: { value: opacities, type: "uniform1fv" },
      u_total_size: { value: totalSize, type: "uniform1f" },
      u_dot_size: { value: dotSize, type: "uniform1f" },
      u_reverse: {
        value: shader.includes("u_reverse_active") ? 1 : 0,
        type: "uniform1i",
      },
    };
  }, [colors, opacities, totalSize, dotSize, shader]);

  return (
    <Shader
      source={`
        precision mediump float;
        in vec2 fragCoord;
        uniform float u_time;
        uniform float u_opacities[10];
        uniform vec3 u_colors[6];
        uniform float u_total_size;
        uniform float u_dot_size;
        uniform vec2 u_resolution;
        uniform int u_reverse;
        out vec4 fragColor;

        float PHI = 1.61803398874989484820459;
        float random(vec2 xy) {
            return fract(tan(distance(xy * PHI, xy) * 0.5) * xy.x);
        }

        void main() {
            vec2 st = fragCoord.xy;
            ${center.includes("x") ? "st.x -= abs(floor((mod(u_resolution.x, u_total_size) - u_dot_size) * 0.5));" : ""}
            ${center.includes("y") ? "st.y -= abs(floor((mod(u_resolution.y, u_total_size) - u_dot_size) * 0.5));" : ""}

            float opacity = step(0.0, st.x) * step(0.0, st.y);
            vec2 st2 = vec2(int(st.x / u_total_size), int(st.y / u_total_size));

            float frequency = 5.0;
            float show_offset = random(st2);
            float rand = random(st2 * floor((u_time / frequency) + show_offset + frequency));
            opacity *= u_opacities[int(rand * 10.0)];
            opacity *= 1.0 - step(u_dot_size / u_total_size, fract(st.x / u_total_size));
            opacity *= 1.0 - step(u_dot_size / u_total_size, fract(st.y / u_total_size));

            vec3 color = u_colors[int(show_offset * 6.0)];

            float animation_speed_factor = 0.5;
            vec2 center_grid = u_resolution / 2.0 / u_total_size;
            float dist_from_center = distance(center_grid, st2);

            float timing_offset_intro = dist_from_center * 0.01 + (random(st2) * 0.15);
            float max_grid_dist = distance(center_grid, vec2(0.0, 0.0));
            float timing_offset_outro = (max_grid_dist - dist_from_center) * 0.02 + (random(st2 + 42.0) * 0.2);

            float current_timing_offset;
            if (u_reverse == 1) {
                current_timing_offset = timing_offset_outro;
                opacity *= 1.0 - step(current_timing_offset, u_time * animation_speed_factor);
                opacity *= clamp((step(current_timing_offset + 0.1, u_time * animation_speed_factor)) * 1.25, 1.0, 1.25);
            } else {
                current_timing_offset = timing_offset_intro;
                opacity *= step(current_timing_offset, u_time * animation_speed_factor);
                opacity *= clamp((1.0 - step(current_timing_offset + 0.1, u_time * animation_speed_factor)) * 1.25, 1.0, 1.25);
            }

            fragColor = vec4(color, opacity);
            fragColor.rgb *= fragColor.a;
        }`}
      uniforms={uniforms}
    />
  );
};

const ShaderMaterial = ({ source, uniforms }: { source: string; uniforms: Uniforms }) => {
  const { size } = useThree();
  const ref = useRef<THREE.Mesh>(null);

  useFrame(({ clock }) => {
    if (!ref.current) return;
    const material: any = ref.current.material;
    material.uniforms.u_time.value = clock.getElapsedTime();
  });

  const getUniforms = () => {
    const preparedUniforms: any = {};
    for (const name in uniforms) {
      const u: any = uniforms[name];
      if (u.type === "uniform1f") preparedUniforms[name] = { value: u.value, type: "1f" };
      else if (u.type === "uniform1i") preparedUniforms[name] = { value: u.value, type: "1i" };
      else if (u.type === "uniform1fv") preparedUniforms[name] = { value: u.value, type: "1fv" };
      else if (u.type === "uniform3fv") {
        preparedUniforms[name] = { value: u.value.map((v: number[]) => new THREE.Vector3().fromArray(v)), type: "3fv" };
      }
    }
    preparedUniforms["u_time"] = { value: 0, type: "1f" };
    preparedUniforms["u_resolution"] = { value: new THREE.Vector2(size.width * 2, size.height * 2) };
    return preparedUniforms;
  };

  const material = useMemo(() => {
    return new THREE.ShaderMaterial({
      vertexShader: `
        precision mediump float;
        in vec2 coordinates;
        uniform vec2 u_resolution;
        out vec2 fragCoord;
        void main(){
          gl_Position = vec4(position.x, position.y, 0.0, 1.0);
          fragCoord = (position.xy + vec2(1.0)) * 0.5 * u_resolution;
          fragCoord.y = u_resolution.y - fragCoord.y;
        }
      `,
      fragmentShader: source,
      uniforms: getUniforms(),
      glslVersion: THREE.GLSL3,
      blending: THREE.CustomBlending,
      blendSrc: THREE.SrcAlphaFactor,
      blendDst: THREE.OneFactor,
    });
  }, [size.width, size.height, source]);

  return (
    <mesh ref={ref as any}>
      <planeGeometry args={[2, 2]} />
      <primitive object={material} attach="material" />
    </mesh>
  );
};

const Shader: React.FC<ShaderProps> = ({ source, uniforms }) => {
  return (
    <Canvas className="absolute inset-0 h-full w-full">
      <ShaderMaterial source={source} uniforms={uniforms} />
    </Canvas>
  );
};

export const SignInPage = () => {
  const [email, setEmail] = useState("");
  const [step, setStep] = useState<"email" | "code" | "success">("email");
  const [code, setCode] = useState(["", "", "", "", "", ""]);
  const codeInputRefs = useRef<(HTMLInputElement | null)[]>([]);
  const [initialCanvasVisible, setInitialCanvasVisible] = useState(true);
  const [reverseCanvasVisible, setReverseCanvasVisible] = useState(false);

  const handleEmailSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    if (email) setStep("code");
  };

  useEffect(() => {
    if (step === "code") {
      setTimeout(() => codeInputRefs.current[0]?.focus(), 500);
    }
  }, [step]);

  const handleCodeChange = (index: number, value: string) => {
    if (value.length <= 1) {
      const newCode = [...code];
      newCode[index] = value;
      setCode(newCode);
      if (value && index < 5) codeInputRefs.current[index + 1]?.focus();
      if (index === 5 && value) {
        if (newCode.every(d => d.length === 1)) {
          setReverseCanvasVisible(true);
          setTimeout(() => setInitialCanvasVisible(false), 50);
          setTimeout(() => setStep("success"), 2000);
        }
      }
    }
  };

  return (
    <div className="flex w-full flex-col min-h-screen bg-black relative">
      <div className="absolute inset-0 z-0">
        {initialCanvasVisible && (
          <CanvasRevealEffect animationSpeed={3} containerClassName="bg-black" colors={[[255, 255, 255]]} dotSize={6} />
        )}
        {reverseCanvasVisible && (
          <CanvasRevealEffect animationSpeed={4} containerClassName="bg-black" colors={[[255, 255, 255]]} dotSize={6} reverse />
        )}
      </div>
      <div className="relative z-10 flex flex-col flex-1 items-center justify-center">
        {/* Sign In UI Forms here */}
      </div>
    </div>
  );
};
```

---

## Form #2: Aurora Glowing Input Sign In
*A premium sign-in card component featuring a beautiful glowing linear-gradient moving bar (aurora-flow), custom floating input text labels, and focus glowing highlights. Comes with a complete TailwindCSS / React translation.*

### HTML
```html
<div class="signin-aurora-container">
    <div class="signin-aurora-card">
        <div class="signin-aurora-header">
            <h3>Sign In</h3>
            <p>Access neural network workspace</p>
        </div>
        <form class="signin-aurora-form" onsubmit="event.preventDefault()">
            <div class="aurora-field">
                <input type="email" placeholder=" " required />
                <label>Email Address</label>
            </div>
            <div class="aurora-field">
                <input type="password" placeholder=" " required />
                <label>Security Key</label>
            </div>
            <button type="submit" class="aurora-btn">Authenticate</button>
        </form>
    </div>
</div>
```

### CSS
```css
.signin-aurora-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #05060b;
    padding: 1rem;
}
.signin-aurora-card {
    width: 320px;
    background: #0b0d16;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    padding: 2rem 1.5rem;
    position: relative;
    overflow: hidden;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
}
.signin-aurora-card::before {
    content: '';
    position: absolute;
    top: -2px;
    left: -2px;
    right: -2px;
    height: 4px;
    background: linear-gradient(90deg, #6366f1, #d946ef, #3b82f6, #6366f1);
    background-size: 300% 100%;
    animation: aurora-flow 6s linear infinite;
}
@keyframes aurora-flow {
    0% { background-position: 0% 50%; }
    100% { background-position: 300% 50%; }
}
.signin-aurora-header {
    text-align: center;
    margin-bottom: 1.75rem;
}
.signin-aurora-header h3 {
    color: #fff;
    font-size: 1.35rem;
    font-weight: 600;
}
.signin-aurora-header p {
    color: #64748b;
    font-size: 0.8rem;
    margin-top: 4px;
}
.signin-aurora-form {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
}
.aurora-field {
    position: relative;
}
.aurora-field input {
    width: 100%;
    background: #0f1220;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 8px;
    padding: 11px 14px;
    color: #fff;
    font-size: 0.85rem;
    outline: none;
    transition: all 0.3s;
}
.aurora-field label {
    position: absolute;
    left: 14px;
    top: 50%;
    transform: translateY(-50%);
    color: #475569;
    font-size: 0.8rem;
    pointer-events: none;
    transition: all 0.3s;
}
.aurora-field input:focus ~ label,
.aurora-field input:not(:placeholder-shown) ~ label {
    top: -6px;
    left: 8px;
    font-size: 0.72rem;
    color: #d946ef;
    background: #0b0d16;
    padding: 0 4px;
}
.aurora-field input:focus {
    border-color: #d946ef;
    box-shadow: 0 0 10px rgba(217, 70, 239, 0.2);
}
.aurora-btn {
    background: linear-gradient(90deg, #6366f1, #3b82f6);
    color: #fff;
    border: none;
    border-radius: 8px;
    padding: 11px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    transition: opacity 0.2s;
    box-shadow: 0 4px 12px rgba(99, 102, 241, 0.35);
}
.aurora-btn:hover {
    opacity: 0.9;
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function AuroraSignIn() {
  const [email, setEmail] = useState("")
  const [key, setKey] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#05060b] p-4 font-sans">
      <div className="relative w-full max-w-[320px] overflow-hidden rounded-2xl border border-white/5 bg-[#0b0d16] p-6 shadow-2xl before:absolute before:left-0 before:top-0 before:h-[4px] before:w-full before:bg-gradient-to-r before:from-indigo-500 before:via-pink-500 before:to-blue-500 before:bg-[length:300%_100%] before:animate-[aurora-flow_6s_linear_infinite]">
        <div className="text-center mb-6">
          <h3 className="text-lg font-semibold text-white">Sign In</h3>
          <p className="text-xs text-slate-500 mt-1">Access neural network workspace</p>
        </div>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-5">
          <div className="relative">
            <input
              type="email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              placeholder=" "
              required
              className="w-full rounded-lg border border-white/10 bg-[#0f1220] px-4 py-2.5 text-sm text-white outline-none transition-all focus:border-pink-500 focus:shadow-[0_0_10px_rgba(217,_70,_239,_0.2)]"
            />
            <label className="pointer-events-none absolute left-4 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all focus:text-pink-500">
              Email Address
            </label>
          </div>
          <div className="relative">
            <input
              type="password"
              value={key}
              onChange={(e) => setKey(e.target.value)}
              placeholder=" "
              required
              className="w-full rounded-lg border border-white/10 bg-[#0f1220] px-4 py-2.5 text-sm text-white outline-none transition-all focus:border-pink-500 focus:shadow-[0_0_10px_rgba(217,_70,_239,_0.2)]"
            />
            <label className="pointer-events-none absolute left-4 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all focus:text-pink-500">
              Security Key
            </label>
          </div>
          <button className="rounded-lg bg-gradient-to-r from-indigo-500 to-blue-500 py-2.5 text-sm font-semibold text-white shadow-lg shadow-indigo-500/35 transition-all hover:opacity-90">
            Authenticate
          </button>
        </form>
      </div>
    </div>`
  )
}
```

---

## Form #3: Glassmorphic Floating Bubbles Form
*A glassmorphic sign-in component form suspended above animated glowing background mesh circles, complete with custom underlines and transparent blur styling.*

### HTML
```html
<div class="signin-glass-container">
    <div class="glass-bubble glass-bubble-1"></div>
    <div class="glass-bubble glass-bubble-2"></div>
    <div class="signin-glass-card">
        <div class="signin-glass-header">
            <h3>Authenticate</h3>
            <p>Access your dashboard workspace</p>
        </div>
        <form class="signin-glass-form" onsubmit="event.preventDefault()">
            <div class="glass-field">
                <input type="email" placeholder=" " required />
                <label>Email Address</label>
            </div>
            <div class="glass-field">
                <input type="password" placeholder=" " required />
                <label>Password</label>
            </div>
            <button type="submit" class="glass-btn">Proceed</button>
        </form>
    </div>
</div>
```

### CSS
```css
.signin-glass-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #080911;
    position: relative;
    overflow: hidden;
    padding: 1rem;
}
.glass-bubble {
    position: absolute;
    border-radius: 50%;
    filter: blur(20px);
    opacity: 0.45;
    z-index: 0;
    animation: bubble-float 10s ease-in-out infinite alternate;
}
.glass-bubble-1 {
    width: 80px;
    height: 80px;
    background: #6366f1;
    top: 20%;
    left: 20%;
}
.glass-bubble-2 {
    width: 90px;
    height: 90px;
    background: #ec4899;
    bottom: 25%;
    right: 20%;
    animation-delay: -3s;
}
@keyframes bubble-float {
    0% { transform: translateY(0) scale(1); }
    100% { transform: translateY(15px) scale(1.1); }
}
.signin-glass-card {
    position: relative;
    z-index: 1;
    width: 320px;
    background: rgba(255, 255, 255, 0.03);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 16px;
    padding: 2.25rem 1.5rem;
    box-shadow: 0 25px 45px rgba(0, 0, 0, 0.3);
}
.signin-glass-header {
    text-align: center;
    margin-bottom: 2rem;
}
.signin-glass-header h3 {
    color: #fff;
    font-size: 1.3rem;
    font-weight: 600;
}
.signin-glass-header p {
    color: #94a3b8;
    font-size: 0.78rem;
    margin-top: 4px;
}
.signin-glass-form {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
}
.glass-field {
    position: relative;
    border-bottom: 1px solid rgba(255, 255, 255, 0.15);
    padding-bottom: 4px;
}
.glass-field input {
    width: 100%;
    background: transparent;
    border: none;
    color: #fff;
    font-size: 0.85rem;
    outline: none;
    padding: 6px 0;
}
.glass-field label {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    color: #64748b;
    font-size: 0.8rem;
    pointer-events: none;
    transition: all 0.3s;
}
.glass-field input:focus ~ label,
.glass-field input:not(:placeholder-shown) ~ label {
    top: -8px;
    font-size: 0.7rem;
    color: #cbd5e1;
}
.glass-btn {
    background: rgba(255, 255, 255, 0.1);
    color: #fff;
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 8px;
    padding: 11px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    transition: all 0.3s;
    backdrop-filter: blur(4px);
}
.glass-btn:hover {
    background: rgba(255, 255, 255, 0.25);
    border-color: rgba(255, 255, 255, 0.35);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function GlassSignIn() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")

  return (
    <div className="relative flex min-h-screen items-center justify-center bg-[#080911] p-4 overflow-hidden font-sans">
      <div className="absolute top-[20%] left-[20%] h-[120px] w-[120px] rounded-full bg-indigo-500/40 blur-xl animate-[bounce_10s_infinite_alternate]" />
      <div className="absolute bottom-[25%] right-[20%] h-[130px] w-[130px] rounded-full bg-pink-500/40 blur-xl animate-[bounce_10s_infinite_alternate_3s]" />
      
      <div className="relative w-full max-w-[320px] rounded-2xl border border-white/10 bg-white/5 p-8 shadow-2xl backdrop-blur-lg">
        <div className="text-center mb-8">
          <h3 className="text-lg font-semibold text-white">Authenticate</h3>
          <p className="text-xs text-slate-400 mt-1">Access your dashboard workspace</p>
        </div>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-6">
          <div className="relative border-b border-white/15 pb-1">
            <input
              type="email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              placeholder=" "
              required
              className="w-full bg-transparent py-1.5 text-sm text-white outline-none"
            />
            <label className="pointer-events-none absolute left-0 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all">
              Email Address
            </label>
          </div>
          <div className="relative border-b border-white/15 pb-1">
            <input
              type="password"
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              placeholder=" "
              required
              className="w-full bg-transparent py-1.5 text-sm text-white outline-none"
            />
            <label className="pointer-events-none absolute left-0 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all">
              Password
            </label>
          </div>
          <button className="rounded-lg border border-white/20 bg-white/15 py-2.5 text-sm font-semibold text-white backdrop-blur transition-all hover:bg-white/25 hover:border-white/30">
            Proceed
          </button>
        </form>
      </div>
    </div>
  )
}
```

---

## Form #4: Spotlight Cursor Tracking Sign In
*An advanced sign-in component form where a glowing linear background radial spotlight follows the cursor's movements in real time using mouse events.*

### HTML
```html
<div class="signin-spot-container">
    <div class="signin-spot-card" id="spotlight-card-3">
        <div class="signin-spot-header">
            <h3>Sign In</h3>
            <p>Spotlight cursor alignment tracking</p>
        </div>
        <form class="signin-spot-form" onsubmit="event.preventDefault()">
            <div class="spot-field">
                <input type="email" placeholder="Email Address" required />
            </div>
            <div class="spot-field">
                <input type="password" placeholder="Password" required />
            </div>
            <button type="submit" class="spot-btn">Authenticate</button>
        </form>
    </div>
</div>
```

### CSS
```css
.signin-spot-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #030408;
    padding: 1rem;
}
.signin-spot-card {
    --x: 0px;
    --y: 0px;
    position: relative;
    width: 320px;
    background: #090a0f;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    padding: 2.25rem 1.5rem;
    overflow: hidden;
    box-shadow: 0 25px 45px rgba(0, 0, 0, 0.35);
}
.signin-spot-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(circle 120px at var(--x) var(--y), rgba(99, 102, 241, 0.13), transparent 80%);
    pointer-events: none;
    z-index: 0;
}
.signin-spot-header {
    position: relative;
    z-index: 1;
    text-align: center;
    margin-bottom: 2rem;
}
.signin-spot-header h3 {
    color: #fff;
    font-size: 1.3rem;
    font-weight: 600;
}
.signin-spot-header p {
    color: #64748b;
    font-size: 0.8rem;
    margin-top: 4px;
}
.signin-spot-form {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
}
.spot-field input {
    width: 100%;
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 8px;
    padding: 11px 14px;
    color: #fff;
    font-size: 0.85rem;
    outline: none;
    transition: all 0.3s;
}
.spot-field input:focus {
    border-color: rgba(99, 102, 241, 0.5);
    background: rgba(99, 102, 241, 0.02);
}
.spot-btn {
    background: #6366f1;
    color: #fff;
    border: none;
    border-radius: 8px;
    padding: 11px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    transition: background 0.2s;
}
.spot-btn:hover {
    background: #4f46e5;
}
```

### JavaScript
```javascript
window.initSpotlightForm = function(id) {
    const card = document.getElementById(`spotlight-card-${id}`);
    if (!card) return;
    card.addEventListener('mousemove', (e) => {
        const rect = card.getBoundingClientRect();
        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;
        card.style.setProperty('--x', `${x}px`);
        card.style.setProperty('--y', `${y}px`);
    });
};
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useRef, useState } from "react"

export function SpotlightSignIn() {
  const cardRef = useRef<HTMLDivElement>(null)
  const [coords, setCoords] = useState({ x: 0, y: 0 })

  const handleMouseMove = (e: React.MouseEvent) => {
    if (!cardRef.current) return
    const rect = cardRef.current.getBoundingClientRect()
    setCoords({
      x: e.clientX - rect.left,
      y: e.clientY - rect.top
    })
  }

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#030408] p-4 font-sans">
      <div
        ref={cardRef}
        onMouseMove={handleMouseMove}
        className="relative w-full max-w-[320px] overflow-hidden rounded-2xl border border-white/5 bg-[#090a0f] p-8 shadow-2xl"
        style={{
          backgroundImage: `radial-gradient(circle 120px at ${coords.x}px ${coords.y}px, rgba(99, 102, 241, 0.13), transparent 80%)`
        }}
      >
        <div className="text-center mb-8">
          <h3 className="text-lg font-semibold text-white">Sign In</h3>
          <p className="text-xs text-slate-500 mt-1">Spotlight cursor alignment tracking</p>
        </div>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-5">
          <div className="relative">
            <input
              type="email"
              placeholder="Email Address"
              required
              className="w-full rounded-lg border border-white/5 bg-white/[0.02] px-4 py-2.5 text-sm text-white outline-none transition-all focus:border-indigo-500/50 focus:bg-indigo-500/[0.02]"
            />
          </div>
          <div className="relative">
            <input
              type="password"
              placeholder="Password"
              required
              className="w-full rounded-lg border border-white/5 bg-white/[0.02] px-4 py-2.5 text-sm text-white outline-none transition-all focus:border-indigo-500/50 focus:bg-indigo-500/[0.02]"
            />
          </div>
          <button className="rounded-lg bg-indigo-600 py-2.5 text-sm font-semibold text-white transition-all hover:bg-indigo-500">
            Authenticate
          </button>
        </form>
      </div>
    </div>
  )
}
```

---

## Form #5: Sliding Underline Border Form
*A minimalist sign-in form where input underlines expand outwards dynamically on focus.*

### HTML
```html
<div class="signin-sliding-container">
    <div class="sliding-card">
        <h3>Sign In</h3>
        <form class="sliding-form" onsubmit="event.preventDefault()">
            <div class="sliding-group">
                <input type="email" required />
                <label>Email Address</label>
                <div class="underline-glow"></div>
            </div>
            <div class="sliding-group">
                <input type="password" required />
                <label>Password</label>
                <div class="underline-glow"></div>
            </div>
            <button type="submit" class="sliding-btn">Proceed</button>
        </form>
    </div>
</div>
```

### CSS
```css
.signin-sliding-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #090b0f;
    padding: 1rem;
}
.sliding-card {
    width: 320px;
    background: #11141d;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 12px;
    padding: 2.25rem 1.5rem;
    box-shadow: 0 15px 35px rgba(0,0,0,0.4);
}
.sliding-card h3 {
    color: #fff;
    font-size: 1.35rem;
    font-weight: 600;
    margin-bottom: 1.75rem;
}
.sliding-form {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}
.sliding-group {
    position: relative;
    border-bottom: 2px solid rgba(255,255,255,0.08);
}
.sliding-group input {
    width: 100%;
    background: transparent;
    border: none;
    outline: none;
    color: #fff;
    padding: 6px 0;
    font-size: 0.9rem;
}
.sliding-group label {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    color: #64748b;
    font-size: 0.85rem;
    pointer-events: none;
    transition: all 0.3s;
}
.sliding-group input:focus ~ label,
.sliding-group input:valid ~ label {
    top: -10px;
    font-size: 0.72rem;
    color: #6366f1;
}
.underline-glow {
    position: absolute;
    bottom: -2px;
    left: 50%;
    width: 0;
    height: 2px;
    background: #6366f1;
    transition: all 0.4s ease;
}
.sliding-group input:focus ~ .underline-glow {
    left: 0;
    width: 100%;
    box-shadow: 0 0 10px rgba(99,102,241,0.5);
}
.sliding-btn {
    background: #fff;
    color: #000;
    border: none;
    border-radius: 6px;
    padding: 10px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    transition: background 0.2s;
    margin-top: 4px;
    width: 100%;
    text-align: center;
}
.sliding-btn:hover {
    background: #cbd5e1;
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function SlidingUnderlineSignIn() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#090b0f] p-4 font-sans">
      <div className="w-full max-w-[320px] rounded-xl border border-white/5 bg-[#11141d] p-8 shadow-2xl">
        <h3 className="text-xl font-semibold text-white mb-6">Sign In</h3>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-6">
          <div className="relative border-b-2 border-white/10 pb-0.5">
            <input
              type="email"
              required
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="peer w-full bg-transparent py-1 text-sm text-white outline-none"
            />
            <label className="pointer-events-none absolute left-0 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all peer-focus:-top-2.5 peer-focus:text-indigo-500 peer-valid:-top-2.5 peer-valid:text-indigo-500">
              Email Address
            </label>
            <div className="absolute bottom-[-2px] left-1/2 h-[2px] w-0 bg-indigo-500 transition-all duration-300 peer-focus:left-0 peer-focus:w-full peer-focus:shadow-[0_0_10px_rgba(99,_102,_241,_0.5)]" />
          </div>
          <div className="relative border-b-2 border-white/10 pb-0.5">
            <input
              type="password"
              required
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              className="peer w-full bg-transparent py-1 text-sm text-white outline-none"
            />
            <label className="pointer-events-none absolute left-0 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all peer-focus:-top-2.5 peer-focus:text-indigo-500 peer-valid:-top-2.5 peer-valid:text-indigo-500">
              Password
            </label>
            <div className="absolute bottom-[-2px] left-1/2 h-[2px] w-0 bg-indigo-500 transition-all duration-300 peer-focus:left-0 peer-focus:w-full peer-focus:shadow-[0_0_10px_rgba(99,_102,_241,_0.5)]" />
          </div>
          <button className="mt-2 w-full rounded bg-white py-2 text-sm font-semibold text-black transition-all hover:bg-slate-200">
            Proceed
          </button>
        </form>
      </div>
    </div>`
  )
}
```

---

## Form #6: Password Reveal Shield Sign In
*A security-oriented form offering custom reveal password toggles.*

### HTML
```html
<div class="signin-shield-container" id="shield-container-5">
    <div class="shield-card">
        <div class="shield-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
            </svg>
        </div>
        <form class="shield-form" onsubmit="event.preventDefault()">
            <input type="email" placeholder="Account Email" required />
            <div class="shield-password-wrap">
                <input type="password" id="shield-pass-input-5" placeholder="Password" required />
                <button type="button" class="reveal-btn" onclick="toggleShieldPass(5)">
                    <svg class="eye-open" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                        <circle cx="12" cy="12" r="3"></circle>
                    </svg>
                </button>
            </div>
            <button type="submit" class="shield-btn">Open Vault</button>
        </form>
    </div>
</div>
```

### CSS
```css
.signin-shield-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #06080e;
    padding: 1rem;
}
.shield-card {
    width: 320px;
    background: #0f121d;
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 12px;
    padding: 2.25rem 1.5rem;
    box-shadow: 0 15px 35px rgba(0,0,0,0.4);
    text-align: center;
}
.shield-icon {
    display: inline-flex;
    background: rgba(99, 102, 241, 0.1);
    color: #6366f1;
    padding: 12px;
    border-radius: 50%;
    margin-bottom: 1.5rem;
}
.shield-form {
    display: flex;
    flex-direction: column;
    gap: 12px;
}
.shield-form input {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 6px;
    padding: 10px 12px;
    color: #fff;
    font-size: 0.85rem;
    outline: none;
    transition: all 0.3s;
}
.shield-form input:focus {
    border-color: #6366f1;
}
.shield-password-wrap {
    position: relative;
    width: 100%;
}
.shield-password-wrap input {
    width: 100%;
    padding-right: 40px;
}
.reveal-btn {
    position: absolute;
    right: 12px;
    top: 50%;
    transform: translateY(-50%);
    background: transparent;
    border: none;
    color: #64748b;
    cursor: pointer;
    display: flex;
    align-items: center;
}
.reveal-btn:hover {
    color: #94a3b8;
}
.shield-btn {
    background: #6366f1;
    color: #fff;
    border: none;
    border-radius: 6px;
    padding: 10px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    transition: background 0.2s;
    margin-top: 4px;
    width: 100%;
    text-align: center;
}
.shield-btn:hover {
    background: #4f46e5;
}
```

### JavaScript
```javascript
window.toggleShieldPass = function(id) {
    const input = document.getElementById(`shield-pass-input-${id}`);
    if (input) {
        if (input.type === 'password') {
            input.type = 'text';
        } else {
            input.type = 'password';
        }
    }
};
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function ShieldSignIn() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")
  const [showPassword, setShowPassword] = useState(false)

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#06080e] p-4 font-sans">
      <div className="w-full max-w-[320px] rounded-xl border border-white/5 bg-[#0f121d] p-8 shadow-2xl text-center">
        <div className="inline-flex rounded-full bg-indigo-500/10 p-3 text-indigo-500 mb-6">
          <svg className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth={2}>
            <path strokeLinecap="round" strokeLinejoin="round" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
          </svg>
        </div>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-4 text-left">
          <input
            type="email"
            placeholder="Account Email"
            required
            value={email}
            onChange={(e) => setEmail(e.target.value)}
            className="rounded-lg border border-white/10 bg-white/3 px-3.5 py-2 text-sm text-white outline-none focus:border-indigo-500"
          />
          <div className="relative w-full">
            <input
              type={showPassword ? "text" : "password"}
              placeholder="Password"
              required
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              className="w-full rounded-lg border border-white/10 bg-white/3 pl-3.5 pr-10 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
            <button
              type="button"
              onClick={() => setShowPassword(!showPassword)}
              className="absolute right-3 top-1/2 -translate-y-1/2 text-slate-500 hover:text-slate-400"
            >
              <svg className="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth={2}>
                <path strokeLinecap="round" strokeLinejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                <path strokeLinecap="round" strokeLinejoin="round" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z" />
              </svg>
            </button>
          </div>
          <button className="mt-2 w-full rounded-lg bg-indigo-600 py-2.5 text-sm font-semibold text-white transition-all hover:bg-indigo-500">
            Open Vault
          </button>
        </form>
      </div>
    </div>`
  )
}
```

---

## Form #7: Neumorphic Soft-Glow Form
*A modern neumorphic sign-in component form with inset/outset shadows and a custom neon accent.*

### HTML
```html
<div class="signin-neumorph-container">
    <div class="neumorph-card">
        <h3>Sign In</h3>
        <form class="neumorph-form" onsubmit="event.preventDefault()">
            <div class="neumorph-input-wrap">
                <input type="email" placeholder="Email" required />
            </div>
            <div class="neumorph-input-wrap">
                <input type="password" placeholder="Password" required />
            </div>
            <button type="submit" class="neumorph-btn">Unlock</button>
        </form>
    </div>
</div>
```

### CSS
```css
.signin-neumorph-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #090a10;
    padding: 1rem;
}
.neumorph-card {
    width: 300px;
    background: #090a10;
    border-radius: 16px;
    padding: 2.25rem 1.5rem;
    box-shadow: 
        5px 5px 15px rgba(0,0,0,0.7),
        -5px -5px 15px rgba(255,255,255,0.015);
    border: 1px solid rgba(255,255,255,0.02);
}
.neumorph-card h3 {
    color: #cbd5e1;
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 1.75rem;
    text-align: center;
    letter-spacing: 0.5px;
}
.neumorph-form {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
}
.neumorph-input-wrap {
    position: relative;
    border-radius: 8px;
    box-shadow: 
        inset 3px 3px 6px rgba(0,0,0,0.8),
        inset -3px -3px 6px rgba(255,255,255,0.01);
}
.neumorph-input-wrap input {
    width: 100%;
    background: transparent;
    border: none;
    outline: none;
    color: #fff;
    padding: 11px 14px;
    font-size: 0.85rem;
}
.neumorph-btn {
    background: #090a10;
    color: #6366f1;
    border: 1px solid rgba(99, 102, 241, 0.15);
    border-radius: 8px;
    padding: 11px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    box-shadow: 
        4px 4px 10px rgba(0,0,0,0.5),
        -4px -4px 10px rgba(255,255,255,0.01);
    transition: all 0.3s;
}
.neumorph-btn:hover {
    color: #fff;
    border-color: #6366f1;
    box-shadow: 0 0 15px rgba(99,102,241,0.25);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function NeumorphicSignIn() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#090a10] p-4 font-sans">
      <div className="w-full max-w-[300px] rounded-2xl border border-white/[0.02] bg-[#090a10] p-8 shadow-[5px_5px_15px_rgba(0,0,0,0.7),_-5px_-5px_15px_rgba(255,255,255,0.015)]">
        <h3 className="text-lg font-semibold text-slate-300 mb-6 text-center tracking-wide">Sign In</h3>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-5">
          <div className="rounded-lg shadow-[inset_3px_3px_6px_rgba(0,0,0,0.8),_inset_-3px_-3px_6px_rgba(255,255,255,0.01)]">
            <input
              type="email"
              placeholder="Email"
              required
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="w-full bg-transparent px-4 py-2.5 text-sm text-white outline-none"
            />
          </div>
          <div className="rounded-lg shadow-[inset_3px_3px_6px_rgba(0,0,0,0.8),_inset_-3px_-3px_6px_rgba(255,255,255,0.01)]">
            <input
              type="password"
              placeholder="Password"
              required
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              className="w-full bg-transparent px-4 py-2.5 text-sm text-white outline-none"
            />
          </div>
          <button className="rounded-lg border border-indigo-500/15 bg-[#090a10] py-2.5 text-sm font-semibold text-indigo-500 shadow-[4px_4px_10px_rgba(0,0,0,0.5),_-4px_-4px_10px_rgba(255,255,255,0.01)] transition-all hover:border-indigo-500 hover:text-white hover:shadow-[0_0_15px_rgba(99,_102,_241,_0.25)]">
            Unlock
          </button>
        </form>
      </div>
    </div>`
  )
}
```

---

## Form #8: Biometric Fingerprint Scan Mock Sign In
*A circular biometric fingerprint authentication scanner mock component featuring scanline animations and interactive status text.*

### HTML
```html
<div class="form-box-7" id="biometric-box-7">
    <div class="bio-scanner" onclick="triggerBioScan(7)">
        <svg class="fingerprint-svg" width="36" height="36" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
            <path d="M12 2a10 10 0 0 0-7.3 3.1M12 2a10 10 0 0 1 7.3 3.1M2 12a10 10 0 0 0 2.7 6.9M22 12a10 10 0 0 1-2.7 6.9"></path>
            <path d="M12 6a6 6 0 0 0-4.4 1.9M12 6a6 6 0 0 1 4.4 1.9"></path>
            <path d="M8.5 14.5a3.5 3.5 0 0 1 7 0"></path>
            <path d="M12 10a2 2 0 0 0-1.5.7M12 10a2 2 0 0 1 1.5.7"></path>
            <path d="M12 18v2"></path>
        </svg>
        <div class="scan-bar"></div>
    </div>
    <div class="bio-status">TAP TO SCAN BIOMETRICS</div>
</div>
```

### CSS
```css
.form-box-7 {
    width: 290px;
    background: #0b0f19;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 12px;
    padding: 1.5rem 1.25rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 1.25rem;
    box-shadow: 0 15px 30px rgba(0,0,0,0.3);
}
.bio-scanner {
    width: 70px;
    height: 70px;
    border-radius: 50%;
    background: rgba(34, 211, 238, 0.05);
    border: 2px solid rgba(34, 211, 238, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    cursor: pointer;
    color: #22d3ee;
    transition: all 0.3s;
}
.bio-scanner:hover {
    border-color: #22d3ee;
    box-shadow: 0 0 12px rgba(34, 211, 238, 0.3);
}
.scan-bar {
    position: absolute;
    left: 0;
    width: 100%;
    height: 2px;
    background: #22d3ee;
    box-shadow: 0 0 6px #22d3ee;
    top: 0;
    opacity: 0;
}
.bio-scanner.scanning .scan-bar {
    opacity: 1;
    animation: scan-move 2s ease-in-out infinite;
}
@keyframes scan-move {
    0%, 100% { top: 0%; }
    50% { top: 95%; }
}
.bio-status {
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 1px;
    color: #64748b;
    text-align: center;
}
```

### JavaScript
```javascript
window.triggerBioScan = function(id) {
    const container = document.getElementById(`biometric-box-${id}`);
    if (!container) return;
    const scanner = container.querySelector('.bio-scanner');
    const status = container.querySelector('.bio-status');
    if (scanner.classList.contains('scanning')) return;
    
    scanner.classList.add('scanning');
    status.textContent = 'SCANNING FINGERPRINT...';
    status.style.color = '#22d3ee';
    
    setTimeout(() => {
        scanner.classList.remove('scanning');
        status.textContent = 'ACCESS GRANTED';
        status.style.color = '#10b981';
        setTimeout(() => {
            status.textContent = 'TAP TO SCAN BIOMETRICS';
            status.style.color = '';
        }, 2000);
    }, 2000);
};
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function BiometricSignIn() {
  const [status, setStatus] = useState("TAP TO SCAN BIOMETRICS")
  const [isScanning, setIsScanning] = useState(false)

  const handleScan = () => {
    if (isScanning) return
    setIsScanning(true)
    setStatus("SCANNING FINGERPRINT...")
    
    setTimeout(() => {
      setIsScanning(false)
      setStatus("ACCESS GRANTED")
      setTimeout(() => {
        setStatus("TAP TO SCAN BIOMETRICS")
      }, 2000)
    }, 2000)
  }

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#0a0b12] p-4 font-sans">
      <div className="flex w-full max-w-[290px] flex-col items-center justify-center gap-6 rounded-xl border border-white/5 bg-[#0b0f19] p-6 shadow-2xl">
        <div
          onClick={handleScan}
          className={`relative flex h-20 w-20 cursor-pointer items-center justify-center rounded-full border-2 bg-cyan-500/5 text-cyan-400 transition-all hover:shadow-[0_0_15px_rgba(34,_211,_238,_0.3)] ${
            isScanning ? "border-cyan-400" : "border-cyan-400/20"
          }`}
        >
          <svg className="h-10 w-10" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth={1.5}>
            <path strokeLinecap="round" strokeLinejoin="round" d="M12 11c0 3.517-1.009 6.799-2.753 9.571m-3.44-2.04l.054-.09A13.916 13.916 0 009 11a14 14 0 00-6-11.796m22 12.571a13.921 13.921 0 01-3.197 8.718m-2.824-2.031a13.931 13.931 0 002.502-8.687M12 11c0-3.517 1.009-6.799 2.753-9.571m-3.44 2.04C10.548 6.097 9 8.377 9 11a14 14 0 006 11.796m22-12.571a13.92 13.92 0 00-3.197-8.718m-2.824 2.031a13.93 13.93 0 012.502 8.687" />
          </svg>
          {isScanning && (
            <div className="absolute left-0 top-0 h-0.5 w-full bg-cyan-400 shadow-[0_0_8px_#22d3ee] animate-[scan-move_2s_ease-in-out_infinite]" />
          )}
        </div>
        <div className={`text-xs font-semibold tracking-wider text-center ${
          status === "ACCESS GRANTED" ? "text-emerald-500" : status.startsWith("SCANNING") ? "text-cyan-400" : "text-slate-500"
        }`}>
          {status}
        </div>
      </div>
    </div>
  )
}
```

---

## Form #9: Sliding Segmented Toggle Form
*An interactive dual-mode sign-in component featuring a sliding segmented control to switch modes between Personal User and Corporate Enterprise.*

### HTML
```html
<div class="form-box-8" id="toggle-form-8">
    <div class="toggle-container">
        <div class="toggle-slider"></div>
        <button type="button" class="toggle-btn active" onclick="switchToggleMode(8, 'user')">User</button>
        <button type="button" class="toggle-btn" onclick="switchToggleMode(8, 'corp')">Enterprise</button>
    </div>
    <form onsubmit="event.preventDefault()">
        <div class="toggle-field" id="field-email-8">
            <input type="email" placeholder="Personal Email" required />
        </div>
        <div class="toggle-field" id="field-corp-8" style="display: none;">
            <input type="text" placeholder="Corporate ID" />
        </div>
        <div class="toggle-field">
            <input type="password" placeholder="Password" required />
        </div>
        <button type="submit" class="toggle-submit">Secure Enter</button>
    </form>
</div>
```

### CSS
```css
.form-box-8 {
    width: 290px;
    background: #0f172a;
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 1.5rem 1.25rem;
    box-shadow: 0 15px 30px rgba(0,0,0,0.3);
}
.toggle-container {
    display: flex;
    position: relative;
    background: rgba(255,255,255,0.04);
    border-radius: 8px;
    padding: 3px;
    margin-bottom: 1.25rem;
}
.toggle-slider {
    position: absolute;
    top: 3px;
    bottom: 3px;
    left: 3px;
    width: calc(50% - 3px);
    background: #6366f1;
    border-radius: 6px;
    transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
.toggle-btn {
    flex: 1;
    background: transparent;
    border: none;
    color: #94a3b8;
    font-size: 0.75rem;
    font-weight: 600;
    padding: 8px 0;
    cursor: pointer;
    z-index: 1;
    transition: color 0.3s;
}
.toggle-btn.active {
    color: #fff;
}
.toggle-field input {
    width: 100%;
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 6px;
    padding: 9px 12px;
    color: #fff;
    font-size: 0.8rem;
    outline: none;
    margin-bottom: 0.75rem;
}
.toggle-submit {
    width: 100%;
    background: #6366f1;
    color: #fff;
    border: none;
    border-radius: 6px;
    padding: 9px;
    font-weight: 600;
    font-size: 0.8rem;
    cursor: pointer;
    transition: opacity 0.2s;
}
```

### JavaScript
```javascript
window.switchToggleMode = function(id, mode) {
    const container = document.getElementById(`toggle-form-${id}`);
    if (!container) return;
    const slider = container.querySelector('.toggle-slider');
    const emailField = container.querySelector(`#field-email-${id}`);
    const corpField = container.querySelector(`#field-corp-${id}`);
    const btns = container.querySelectorAll('.toggle-btn');
    
    if (mode === 'user') {
        slider.style.transform = 'translateX(0)';
        emailField.style.display = 'block';
        emailField.querySelector('input').setAttribute('required', 'true');
        corpField.style.display = 'none';
        corpField.querySelector('input').removeAttribute('required');
        btns[0].classList.add('active');
        btns[1].classList.remove('active');
    } else {
        slider.style.transform = 'translateX(100%)';
        emailField.style.display = 'none';
        emailField.querySelector('input').removeAttribute('required');
        corpField.style.display = 'block';
        corpField.querySelector('input').setAttribute('required', 'true');
        btns[0].classList.remove('active');
        btns[1].classList.add('active');
    }
};
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function SegmentedToggleSignIn() {
  const [mode, setMode] = useState<"user" | "corp">("user")
  const [email, setEmail] = useState("")
  const [corpId, setCorpId] = useState("")
  const [password, setPassword] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#090b0f] p-4 font-sans">
      <div className="w-full max-w-[320px] rounded-xl border border-white/5 bg-[#0f172a] p-6 shadow-2xl">
        <div className="relative flex rounded-lg bg-white/5 p-1 mb-6">
          <div
            className="absolute bottom-1 top-1 left-1 bg-indigo-600 rounded-md transition-all duration-300 ease-[cubic-bezier(0.4,_0,_0.2,_1)]"
            style={{
              width: "calc(50% - 4px)",
              transform: mode === "user" ? "translateX(0)" : "translateX(100%)"
            }}
          />
          <button
            onClick={() => setMode("user")}
            className={`flex-1 text-center py-1.5 text-xs font-semibold z-10 transition-colors ${
              mode === "user" ? "text-white" : "text-slate-400"
            }`}
          >
            User
          </button>
          <button
            onClick={() => setMode("corp")}
            className={`flex-1 text-center py-1.5 text-xs font-semibold z-10 transition-colors ${
              mode === "corp" ? "text-white" : "text-slate-400"
            }`}
          >
            Enterprise
          </button>
        </div>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-4">
          {mode === "user" ? (
            <input
              type="email"
              placeholder="Personal Email"
              required
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
          ) : (
            <input
              type="text"
              placeholder="Corporate ID"
              required
              value={corpId}
              onChange={(e) => setCorpId(e.target.value)}
              className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
          )}
          <input
            type="password"
            placeholder="Password"
            required
            value={password}
            onChange={(e) => setPassword(e.target.value)}
            className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
          />
          <button className="w-full rounded-lg bg-indigo-600 py-2.5 text-sm font-semibold text-white transition-colors hover:bg-indigo-500">
            Secure Enter
          </button>
        </form>
      </div>
    </div>
  )
}
```

---

## Form #10: Minimalist Border Draw Input Form
*A minimalist border-tracing sign-in component where input borders draw themselves dynamically when focused.*

### HTML
```html
<div class="form-box-9">
    <h4>Border Draw</h4>
    <form onsubmit="event.preventDefault()">
        <div class="draw-input-wrap">
            <input type="email" placeholder="Email Address" required />
        </div>
        <div class="draw-input-wrap">
            <input type="password" placeholder="Password" required />
        </div>
        <button type="submit" class="draw-btn">Sign In</button>
    </form>
</div>
```

### CSS
```css
.form-box-9 {
    width: 290px;
    background: #0d0e12;
    border: 1px solid rgba(255,255,255,0.05);
    border-radius: 12px;
    padding: 1.5rem 1.25rem;
    box-shadow: 0 15px 30px rgba(0,0,0,0.3);
}
.form-box-9 h4 {
    color: #fff;
    font-size: 1.1rem;
    font-weight: 600;
    margin-bottom: 1.25rem;
    text-align: center;
}
.draw-input-wrap {
    position: relative;
    width: 100%;
    margin-bottom: 12px;
}
.draw-input-wrap input {
    width: 100%;
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 6px;
    padding: 9px 12px;
    color: #fff;
    font-size: 0.8rem;
    outline: none;
}
.draw-input-wrap::after {
    content: '';
    position: absolute;
    inset: 0;
    border: 1.5px solid #6366f1;
    border-radius: 6px;
    clip-path: polygon(0 0, 0 0, 0 0, 0 0);
    transition: clip-path 0.4s ease-in-out;
    pointer-events: none;
}
.draw-input-wrap:focus-within::after {
    clip-path: polygon(-10% -10%, 110% -10%, 110% 110%, -10% 110%);
}
.draw-btn {
    width: 100%;
    background: transparent;
    border: 1px solid rgba(255,255,255,0.15);
    color: #fff;
    border-radius: 6px;
    padding: 9px;
    font-weight: 600;
    font-size: 0.8rem;
    cursor: pointer;
    transition: all 0.3s;
}
.draw-btn:hover {
    border-color: #6366f1;
    background: rgba(99,102,241,0.05);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function BorderDrawSignIn() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#0d0e12] p-4 font-sans">
      <div className="w-full max-w-[290px] rounded-xl border border-white/5 bg-[#0d0e12] p-6 shadow-2xl">
        <h4 className="text-lg font-semibold text-white mb-6 text-center">Border Draw</h4>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-4">
          <div className="relative w-full group">
            <input
              type="email"
              placeholder="Email"
              required
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none"
            />
            <div className="absolute inset-0 rounded-lg border-2 border-indigo-500 pointer-events-none transition-all duration-300 [clip-path:polygon(0_0,_0_0,_0_0,_0_0)] group-focus-within:[clip-path:polygon(-10%_-10%,_110%_-10%,_110%_110%,_-10%_110%)]" />
          </div>
          <div className="relative w-full group">
            <input
              type="password"
              placeholder="Password"
              required
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none"
            />
            <div className="absolute inset-0 rounded-lg border-2 border-indigo-500 pointer-events-none transition-all duration-300 [clip-path:polygon(0_0,_0_0,_0_0,_0_0)] group-focus-within:[clip-path:polygon(-10%_-10%,_110%_-10%,_110%_110%,_-10%_110%)]" />
          </div>
          <button className="w-full rounded-lg border border-white/15 bg-transparent py-2.5 text-sm font-semibold text-white transition-all hover:border-indigo-500 hover:bg-indigo-500/5">
            Sign In
          </button>
        </form>
      </div>
    </div>
  )
}
```

---

## Form #11: Cyber Glow Access Node Sheet
*A dark blue cyber access panel designed with center-aligned inputs and interactive high-intensity border glows.*

### HTML
```html
<div class="form-box-10">
    <h4>Access Node</h4>
    <form onsubmit="event.preventDefault()">
        <div class="cyber-glow-wrap">
            <input type="text" placeholder="Access Code" required />
        </div>
        <button type="submit" class="cyber-glow-btn">Establish Access</button>
    </form>
</div>
```

### CSS
```css
.form-box-10 {
    width: 290px;
    background: #040815;
    border: 1px solid rgba(59, 130, 246, 0.15);
    border-radius: 12px;
    padding: 1.5rem 1.25rem;
    box-shadow: 0 0 20px rgba(59,130,246,0.05);
}
.form-box-10 h4 {
    color: #60a5fa;
    font-size: 1.1rem;
    font-weight: 600;
    margin-bottom: 1.25rem;
    text-align: center;
    letter-spacing: 0.5px;
}
.cyber-glow-wrap input {
    width: 100%;
    background: rgba(59,130,246,0.02);
    border: 1px solid rgba(59,130,246,0.2);
    border-radius: 6px;
    padding: 9px 12px;
    color: #fff;
    font-size: 0.8rem;
    outline: none;
    text-align: center;
    transition: all 0.3s;
}
.cyber-glow-wrap input:focus {
    border-color: #3b82f6;
    box-shadow: 0 0 12px rgba(59, 130, 246, 0.4);
}
.cyber-glow-btn {
    width: 100%;
    background: rgba(59, 130, 246, 0.1);
    color: #60a5fa;
    border: 1px solid rgba(59, 130, 246, 0.3);
    border-radius: 6px;
    padding: 9px;
    font-weight: 600;
    font-size: 0.8rem;
    cursor: pointer;
    transition: all 0.3s;
}
.cyber-glow-btn:hover {
    background: #3b82f6;
    color: #fff;
    box-shadow: 0 0 15px rgba(59,130,246,0.4);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function CyberGlowSignIn() {
  const [accessCode, setAccessCode] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#040815] p-4 font-sans">
      <div className="w-full max-w-[290px] rounded-xl border border-blue-500/20 bg-[#040815] p-6 shadow-[0_0_20px_rgba(59,_130,_246,_0.1)]">
        <h4 className="text-lg font-semibold text-blue-400 mb-6 text-center tracking-wide">Access Node</h4>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-5">
          <div className="relative">
            <input
              type="text"
              placeholder="Access Code"
              required
              value={accessCode}
              onChange={(e) => setAccessCode(e.target.value)}
              className="w-full rounded-lg border border-blue-500/20 bg-blue-500/5 px-4 py-2.5 text-center text-sm text-white outline-none transition-all focus:border-blue-500 focus:shadow-[0_0_12px_rgba(59,_130,_246,_0.4)]"
            />
          </div>
          <button className="w-full rounded-lg border border-blue-500/30 bg-blue-500/10 py-2.5 text-sm font-semibold text-blue-400 transition-all hover:bg-blue-500 hover:text-white hover:shadow-[0_0_15px_rgba(59,_130,_246,_0.4)]">
            Establish Access
          </button>
        </form>
      </div>
    </div>
  )
}
```

---

## Form #12: Matrix Digital Code Grid Keypad
*A matrix green console digital keypad form for numeric access code authorization with active click functions.*

### HTML
```html
<div class="form-box-11" id="matrix-auth-11">
    <div class="matrix-code-display">••••</div>
    <div class="matrix-keypad">
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '1')">1</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '2')">2</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '3')">3</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '4')">4</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '5')">5</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '6')">6</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '7')">7</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '8')">8</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '9')">9</button>
        <button type="button" class="matrix-key red" onclick="pressMatrixKey(11, 'C')">C</button>
        <button type="button" class="matrix-key" onclick="pressMatrixKey(11, '0')">0</button>
        <button type="button" class="matrix-key green" onclick="pressMatrixKey(11, 'E')">E</button>
    </div>
</div>
```

### CSS
```css
.form-box-11 {
    width: 260px;
    background: #020204;
    border: 1px solid #10b981;
    border-radius: 12px;
    padding: 1.25rem;
    box-shadow: 0 0 15px rgba(16,185,129,0.15);
    display: flex;
    flex-direction: column;
    gap: 1rem;
    align-items: center;
}
.matrix-code-display {
    width: 100%;
    background: rgba(16,185,129,0.05);
    border: 1px solid rgba(16,185,129,0.3);
    color: #10b981;
    font-family: var(--font-mono);
    font-size: 1.25rem;
    letter-spacing: 6px;
    text-align: center;
    padding: 8px;
    border-radius: 6px;
    height: 42px;
    display: flex;
    align-items: center;
    justify-content: center;
}
.matrix-keypad {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
    width: 100%;
}
.matrix-key {
    background: rgba(16,185,129,0.02);
    border: 1px solid rgba(16,185,129,0.2);
    color: #10b981;
    font-family: var(--font-mono);
    font-size: 0.95rem;
    font-weight: 600;
    padding: 10px 0;
    border-radius: 6px;
    cursor: pointer;
    transition: all 0.2s;
}
.matrix-key:hover {
    background: rgba(16,185,129,0.12);
    border-color: #10b981;
    box-shadow: 0 0 8px rgba(16,185,129,0.25);
}
.matrix-key.red {
    color: #ef4444;
    border-color: rgba(239,68,68,0.2);
}
.matrix-key.red:hover {
    background: rgba(239,68,68,0.1);
    border-color: #ef4444;
}
.matrix-key.green {
    color: #10b981;
    border-color: rgba(16,185,129,0.4);
    background: rgba(16,185,129,0.1);
}
.matrix-key.green:hover {
    background: #10b981;
    color: #000;
}
```

### JavaScript
```javascript
window.pressMatrixKey = function(id, key) {
    const container = document.getElementById(`matrix-auth-${id}`);
    if (!container) return;
    const display = container.querySelector('.matrix-code-display');
    if (!window._matrixCode) window._matrixCode = '';
    
    if (key === 'C') {
        window._matrixCode = '';
        display.textContent = '••••';
    } else if (key === 'E') {
        if (window._matrixCode.length > 0) {
            display.textContent = 'GRANTED';
            display.style.color = '#10b981';
            setTimeout(() => {
                window._matrixCode = '';
                display.textContent = '••••';
                display.style.color = '';
            }, 1500);
        }
    } else {
        if (window._matrixCode.length < 4) {
            window._matrixCode += key;
            display.textContent = '*'.repeat(window._matrixCode.length) + '•'.repeat(4 - window._matrixCode.length);
        }
    }
};
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function MatrixKeypadSignIn() {
  const [code, setCode] = useState("")
  const [status, setStatus] = useState("••••")

  const handlePress = (key: string) => {
    if (key === "C") {
      setCode("")
      setStatus("••••")
    } else if (key === "E") {
      if (code.length > 0) {
        setStatus("GRANTED")
        setTimeout(() => {
          setCode("")
          setStatus("••••")
        }, 1500)
      }
    } else {
      if (code.length < 4) {
        const nextCode = code + key
        setCode(nextCode)
        setStatus("*".repeat(nextCode.length) + "•".repeat(4 - nextCode.length))
      }
    }
  }

  return (
    <div className="flex min-h-screen items-center justify-center bg-black p-4 font-mono">
      <div className="flex w-full max-w-[260px] flex-col gap-4 rounded-xl border border-emerald-500 bg-zinc-950 p-5 shadow-[0_0_15px_rgba(16,_185,_129,_0.15)]">
        <div className={`flex h-10 w-full items-center justify-center rounded border border-emerald-500/30 bg-emerald-500/5 text-lg tracking-[6px] ${
          status === "GRANTED" ? "text-emerald-400 font-bold" : "text-emerald-500"
        }`}>
          {status}
        </div>
        <div className="grid grid-cols-3 gap-2">
          {["1", "2", "3", "4", "5", "6", "7", "8", "9"].map((n) => (
            <button
              key={n}
              onClick={() => handlePress(n)}
              className="rounded border border-emerald-500/20 bg-emerald-500/5 py-2.5 text-sm font-semibold text-emerald-500 transition-all hover:bg-emerald-500/10 hover:border-emerald-500 hover:shadow-[0_0_8px_rgba(16,_185,_129,_0.25)]"
            >
              {n}
            </button>
          ))}
          <button
            onClick={() => handlePress("C")}
            className="rounded border border-red-500/20 bg-red-500/5 py-2.5 text-sm font-semibold text-red-500 transition-all hover:bg-red-500/10 hover:border-red-500"
          >
            C
          </button>
          <button
            onClick={() => handlePress("0")}
            className="rounded border border-emerald-500/20 bg-emerald-500/5 py-2.5 text-sm font-semibold text-emerald-500 transition-all hover:bg-emerald-500/10 hover:border-emerald-500"
          >
            0
          </button>
          <button
            onClick={() => handlePress("E")}
            className="rounded border border-emerald-500/40 bg-emerald-500/10 py-2.5 text-sm font-semibold text-emerald-500 transition-all hover:bg-emerald-500 hover:text-black"
          >
            E
          </button>
        </div>
      </div>
    </div>
  )
}
```
