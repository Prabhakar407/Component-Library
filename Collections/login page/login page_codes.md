# Premium Custom Login Page Code Database

This file contains the complete, self-contained HTML, CSS, and JavaScript/React code snippets for all **6 Premium Login Pages** featured in the interactive showcase. Each page layout is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Login #1: Neon Cyberpunk Glassmorphic Login](#login-1-neon-cyberpunk-glassmorphic-login)
2. [Login #2: Split-Screen Minimalist Editorial Login](#login-2-split-screen-minimalist-editorial-login)
3. [Login #3: 3D Card Flip (Login / Register)](#login-3-3d-card-flip-login--register)
4. [Login #4: Retro Terminal Command-Line Login](#login-4-retro-terminal-command-line-login)
5. [Login #5: Interactive Particle Mesh Login](#login-5-interactive-particle-mesh-login)
6. [Login #6: Futuristic Hologram Circle Login](#login-6-futuristic-hologram-circle-login)

---

## Login #1: Neon Cyberpunk Glassmorphic Login
*A gorgeous cyberpunk dark-mode login card with glassmorphism, radial glow effect, floating labels, input glows, and Next.js/React support.*

### HTML
```html
<div class="login-cyber-container">
    <div class="login-cyber-card">
        <div class="login-cyber-glow"></div>
        <div class="login-cyber-header">
            <h2>Welcome Back</h2>
            <p>Access the neural network</p>
        </div>
        <form class="login-cyber-form" onsubmit="event.preventDefault()">
            <div class="cyber-input-group">
                <input type="email" placeholder=" " required />
                <label>Email Address</label>
            </div>
            <div class="cyber-input-group">
                <input type="password" placeholder=" " required />
                <label>Access Key</label>
            </div>
            <button type="submit" class="cyber-login-btn">
                <span>Initiate Login</span>
            </button>
        </form>
    </div>
</div>
```

### CSS
```css
.login-cyber-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #060913;
    padding: 1rem;
}
.login-cyber-card {
    position: relative;
    width: 320px;
    background: rgba(14, 19, 31, 0.6);
    backdrop-filter: blur(12px);
    border: 1px solid rgba(99, 102, 241, 0.2);
    border-radius: 16px;
    padding: 2rem 1.5rem;
    overflow: hidden;
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
}
.login-cyber-glow {
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.15) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
}
.login-cyber-header {
    position: relative;
    z-index: 1;
    text-align: center;
    margin-bottom: 2rem;
}
.login-cyber-header h2 {
    color: #fff;
    font-size: 1.5rem;
    font-weight: 700;
    letter-spacing: -0.5px;
    margin-bottom: 6px;
}
.login-cyber-header p {
    color: #94a3b8;
    font-size: 0.8rem;
    margin-top: 4px;
}
.login-cyber-form {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}
.cyber-input-group {
    position: relative;
    width: 100%;
}
.cyber-input-group input {
    width: 100%;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 8px;
    padding: 10px 12px;
    color: #fff;
    font-size: 0.9rem;
    outline: none;
    transition: all 0.3s;
}
.cyber-input-group label {
    position: absolute;
    left: 12px;
    top: 50%;
    transform: translateY(-50%);
    color: #64748b;
    font-size: 0.85rem;
    pointer-events: none;
    transition: all 0.3s;
}
.cyber-input-group input:focus ~ label,
.cyber-input-group input:not(:placeholder-shown) ~ label {
    top: -8px;
    left: 8px;
    font-size: 0.75rem;
    color: #6366f1;
    background: #0e131f;
    padding: 0 4px;
}
.cyber-input-group input:focus {
    border-color: #6366f1;
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.25);
}
.cyber-login-btn {
    width: 100%;
    background: linear-gradient(135deg, #6366f1 0%, #ec4899 100%);
    border: none;
    border-radius: 8px;
    padding: 12px;
    color: #fff;
    font-weight: 600;
    font-size: 0.9rem;
    cursor: pointer;
    transition: all 0.3s;
    box-shadow: 0 4px 15px rgba(99, 102, 241, 0.4);
}
.cyber-login-btn:hover {
    transform: translateY(-1px);
    box-shadow: 0 6px 20px rgba(99, 102, 241, 0.6);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function CyberLogin() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault()
    console.log("Cyber login initiation for:", email)
  }

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#060913] p-4 font-sans">
      <div className="relative w-full max-w-[360px] overflow-hidden rounded-2xl border border-indigo-500/20 bg-slate-900/60 p-8 shadow-2xl backdrop-blur-xl">
        <div className="absolute -left-1/2 -top-1/2 -z-10 h-[200%] w-[200%] bg-[radial-gradient(circle,_rgba(99,_102,_241,_0.15)_0%,_transparent_60%)]" />
        <div className="text-center mb-8">
          <h2 className="text-2xl font-bold tracking-tight text-white">Welcome Back</h2>
          <p className="text-xs text-slate-400 mt-1">Access the neural network</p>
        </div>
        <form onSubmit={handleSubmit} className="flex flex-col gap-6">
          <div className="relative w-full">
            <input
              type="email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              placeholder=" "
              required
              className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none transition-all focus:border-indigo-500 focus:shadow-[0_0_10px_rgba(99,_102,_241,_0.25)]"
            />
            <label className="pointer-events-none absolute left-3 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all focus:text-indigo-500">
              Email Address
            </label>
          </div>
          <div className="relative w-full">
            <input
              type="password"
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              placeholder=" "
              required
              className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none transition-all focus:border-indigo-500 focus:shadow-[0_0_10px_rgba(99,_102,_241,_0.25)]"
            />
            <label className="pointer-events-none absolute left-3 top-1/2 -translate-y-1/2 text-xs text-slate-500 transition-all focus:text-indigo-500">
              Access Key
            </label>
          </div>
          <button
            type="submit"
            className="w-full rounded-lg bg-gradient-to-r from-indigo-500 to-pink-500 py-3 text-sm font-semibold text-white shadow-lg shadow-indigo-500/40 transition-all hover:-translate-y-0.5 hover:shadow-indigo-500/60"
          >
            Initiate Login
          </button>
        </form>
      </div>
    </div>
  )
}
```

---

## Login #2: Split-Screen Minimalist Editorial Login
*A gorgeous photography-integrated split screen for high-end digital agency or product workspaces. Uses CSS media queries to automatically fall back to full screen forms on mobile screens.*

### HTML
```html
<div class="login-split-container">
    <div class="split-side-image">
        <div class="image-overlay"></div>
        <div class="image-text">
            <h3>NEXUS</h3>
            <p>Elevate your creative ecosystem with next-generation interactive modules.</p>
        </div>
    </div>
    <div class="split-side-form">
        <div class="form-wrapper">
            <div class="form-header">
                <h2>Welcome Back</h2>
                <p>Please enter your details to sign in</p>
            </div>
            <form onsubmit="event.preventDefault()">
                <div class="input-field">
                    <label>Email Address</label>
                    <input type="email" placeholder="name@company.com" required />
                </div>
                <div class="input-field">
                    <label>Password</label>
                    <input type="password" placeholder="••••••••" required />
                </div>
                <button type="submit" class="split-submit-btn">Sign In</button>
            </form>
        </div>
    </div>
</div>
```

### CSS
```css
.login-split-container {
    width: 100%;
    height: 100%;
    display: flex;
    background: #080b10;
}
.split-side-image {
    flex: 1.2;
    position: relative;
    background-image: url('https://images.unsplash.com/photo-1518495973542-4542c06a5843?auto=format&fit=crop&w=600&q=80');
    background-size: cover;
    background-position: center;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 2rem;
    min-height: 230px;
}
@media (max-width: 600px) {
    .split-side-image {
        display: none;
    }
}
.image-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, rgba(8, 11, 16, 0.9) 0%, rgba(8, 11, 16, 0.2) 100%);
}
.image-text {
    position: relative;
    z-index: 1;
    color: #fff;
}
.image-text h3 {
    font-size: 1.5rem;
    font-weight: 700;
    letter-spacing: 2px;
}
.image-text p {
    font-size: 0.75rem;
    color: #94a3b8;
    margin-top: 6px;
    line-height: 1.4;
}
.split-side-form {
    flex: 1.5;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #0c0f17;
    padding: 2rem 1.5rem;
}
.form-wrapper {
    width: 100%;
    max-width: 280px;
}
.form-header {
    margin-bottom: 1.5rem;
}
.form-header h2 {
    color: #fff;
    font-size: 1.35rem;
    font-weight: 600;
}
.form-header p {
    color: #64748b;
    font-size: 0.8rem;
    margin-top: 4px;
}
.split-side-form form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}
.input-field {
    display: flex;
    flex-direction: column;
    gap: 6px;
}
.input-field label {
    color: #94a3b8;
    font-size: 0.75rem;
    font-weight: 500;
}
.input-field input {
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 6px;
    padding: 8px 12px;
    color: #fff;
    font-size: 0.85rem;
    outline: none;
    transition: all 0.3s;
}
.input-field input:focus {
    border-color: #6366f1;
    background: rgba(99, 102, 241, 0.02);
}
.split-submit-btn {
    margin-top: 0.5rem;
    background: #fff;
    color: #000;
    border: none;
    border-radius: 6px;
    padding: 10px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    transition: all 0.3s;
}
.split-submit-btn:hover {
    background: #e2e8f0;
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function SplitLogin() {
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault()
    console.log("Split sign in for:", email)
  }

  return (
    <div className="flex min-h-screen w-full rounded-xl overflow-hidden bg-slate-950 font-sans shadow-2xl">
      <div className="relative hidden flex-1 flex-col justify-end p-8 bg-[url('https://images.unsplash.com/photo-1518495973542-4542c06a5843?auto=format&fit=crop&w=800&q=80')] bg-cover bg-center md:flex">
        <div className="absolute inset-0 bg-gradient-to-t from-slate-950/90 to-slate-950/20" />
        <div className="relative z-10 text-white">
          <h3 className="text-2xl font-bold tracking-widest">NEXUS</h3>
          <p className="text-xs text-slate-400 mt-2 leading-relaxed">
            Elevate your creative ecosystem with next-generation interactive modules.
          </p>
        </div>
      </div>
      <div className="flex flex-1 items-center justify-center bg-slate-900 px-6 py-12">
        <div className="w-full max-w-[320px]">
          <div className="mb-8">
            <h2 className="text-2xl font-semibold text-white">Welcome Back</h2>
            <p className="text-xs text-slate-500 mt-1">Please enter your details to sign in</p>
          </div>
          <form onSubmit={handleSubmit} className="flex flex-col gap-5">
            <div className="flex flex-col gap-1.5">
              <label className="text-xs font-medium text-slate-400">Email Address</label>
              <input
                type="email"
                value={email}
                onChange={(e) => setEmail(e.target.value)}
                placeholder="name@company.com"
                required
                className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none transition-all focus:border-indigo-500 focus:bg-indigo-500/5"
              />
            </div>
            <div className="flex flex-col gap-1.5">
              <label className="text-xs font-medium text-slate-400">Password</label>
              <input
                type="password"
                value={password}
                onChange={(e) => setPassword(e.target.value)}
                placeholder="••••••••"
                required
                className="w-full rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none transition-all focus:border-indigo-500 focus:bg-indigo-500/5"
              />
            </div>
            <button
              type="submit"
              className="mt-2 w-full rounded-lg bg-white py-2.5 text-sm font-semibold text-black transition-all hover:bg-slate-200"
            >
              Sign In
            </button>
          </form>
        </div>
      </div>
    </div>
  )
}
```

---

## Login #3: 3D Card Flip (Login / Register)
*An interactive 3D card flipping page layout that seamlessly transitions from a Sign-in Form to a Sign-up / Register Form with 3D transform animations.*

### HTML
```html
<div class="login-flip-container" id="flip-container-3">
    <div class="flip-card">
        <div class="flip-card-inner">
            <div class="flip-front">
                <h3>Sign In</h3>
                <form class="flip-form" onsubmit="event.preventDefault()">
                    <input type="email" placeholder="Email" required />
                    <input type="password" placeholder="Password" required />
                    <button type="submit" class="flip-submit-btn">Login</button>
                </form>
                <p class="flip-toggle-text">Don't have an account? <span onclick="toggleCardFlip(3)">Register</span></p>
            </div>
            <div class="flip-back">
                <h3>Create Account</h3>
                <form class="flip-form" onsubmit="event.preventDefault()">
                    <input type="text" placeholder="Full Name" required />
                    <input type="email" placeholder="Email" required />
                    <input type="password" placeholder="Password" required />
                    <button type="submit" class="flip-submit-btn">Register</button>
                </form>
                <p class="flip-toggle-text">Already registered? <span onclick="toggleCardFlip(3)">Sign In</span></p>
            </div>
        </div>
    </div>
</div>
```

### CSS
```css
.login-flip-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #0a0b12;
    perspective: 1000px;
    padding: 1rem;
}
.flip-card {
    width: 320px;
    height: 310px;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    position: relative;
}
.flip-card.flipped {
    transform: rotateY(180deg);
}
.flip-card-inner {
    width: 100%;
    height: 100%;
    position: relative;
}
.flip-front, .flip-back {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    border-radius: 12px;
    border: 1px solid rgba(255, 255, 255, 0.08);
    background: rgba(18, 22, 35, 0.85);
    backdrop-filter: blur(8px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 1.5rem;
}
.flip-back {
    transform: rotateY(180deg);
}
.flip-front h3, .flip-back h3 {
    color: #fff;
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 1rem;
    text-align: center;
}
.flip-form {
    display: flex;
    flex-direction: column;
    gap: 8px;
}
.flip-form input {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 6px;
    padding: 8px 12px;
    color: #fff;
    font-size: 0.8rem;
    outline: none;
}
.flip-form input:focus {
    border-color: #6366f1;
}
.flip-submit-btn {
    margin-top: 4px;
    background: #6366f1;
    color: #fff;
    border: none;
    border-radius: 6px;
    padding: 8px;
    font-weight: 600;
    font-size: 0.8rem;
    cursor: pointer;
    transition: background 0.3s;
}
.flip-submit-btn:hover {
    background: #4f46e5;
}
.flip-toggle-text {
    margin-top: 10px;
    color: #64748b;
    font-size: 0.7rem;
    text-align: center;
}
.flip-toggle-text span {
    color: #6366f1;
    cursor: pointer;
    font-weight: 600;
    transition: color 0.3s;
}
.flip-toggle-text span:hover {
    color: #a5b4fc;
}
```

### JavaScript
```javascript
window.toggleCardFlip = function(id) {
    const wrap = document.getElementById(`flip-container-${id}`);
    if (wrap) {
        const card = wrap.querySelector('.flip-card');
        card.classList.toggle('flipped');
    }
};
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function FlipLogin() {
  const [isFlipped, setIsFlipped] = useState(false)
  const [email, setEmail] = useState("")
  const [password, setPassword] = useState("")
  const [name, setName] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-[#0a0b12] p-4 [perspective:1000px] font-sans">
      <div
        className={`relative w-full max-w-[320px] transition-transform duration-500 [transform-style:preserve-3d] ${
          isFlipped ? "[transform:rotateY(180deg)]" : ""
        }`}
      >
        {/* Front: Sign In */}
        <div className="absolute inset-0 flex flex-col justify-center rounded-2xl border border-white/10 bg-slate-900/80 p-6 shadow-2xl backdrop-blur-md [backface-visibility:hidden]">
          <h3 className="text-xl font-semibold text-white mb-6 text-center">Sign In</h3>
          <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-4">
            <input
              type="email"
              placeholder="Email"
              required
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
            <input
              type="password"
              placeholder="Password"
              required
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              className="rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
            <button className="mt-2 rounded-lg bg-indigo-600 py-2 text-sm font-semibold text-white transition-all hover:bg-indigo-500">
              Login
            </button>
          </form>
          <p className="mt-4 text-center text-xs text-slate-500">
            Don't have an account?{" "}
            <span
              onClick={() => setIsFlipped(true)}
              className="font-semibold text-indigo-500 cursor-pointer hover:text-indigo-400"
            >
              Register
            </span>
          </p>
        </div>

        {/* Back: Register */}
        <div className="absolute inset-0 flex flex-col justify-center rounded-2xl border border-white/10 bg-slate-900/80 p-6 shadow-2xl backdrop-blur-md [backface-visibility:hidden] [transform:rotateY(180deg)]">
          <h3 className="text-xl font-semibold text-white mb-6 text-center">Create Account</h3>
          <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-4">
            <input
              type="text"
              placeholder="Full Name"
              required
              value={name}
              onChange={(e) => setName(e.target.value)}
              className="rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
            <input
              type="email"
              placeholder="Email"
              required
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
            <input
              type="password"
              placeholder="Password"
              required
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              className="rounded-lg border border-white/10 bg-white/5 px-3 py-2 text-sm text-white outline-none focus:border-indigo-500"
            />
            <button className="mt-2 rounded-lg bg-indigo-600 py-2 text-sm font-semibold text-white transition-all hover:bg-indigo-500">
              Register
            </button>
          </form>
          <p className="mt-4 text-center text-xs text-slate-500">
            Already registered?{" "}
            <span
              onClick={() => setIsFlipped(false)}
              className="font-semibold text-indigo-500 cursor-pointer hover:text-indigo-400"
            >
              Sign In
            </span>
          </p>
        </div>
      </div>
    </div>
  )
}
```

---

## Login #4: Retro Terminal Command-Line Login
*A gorgeous retro terminal CRT command interface login design, styled with dark terminal parameters, system indicators, green monospace lettering, and pure CSS layout elements.*

### HTML
```html
<div class="login-terminal-container">
    <div class="terminal-card">
        <div class="terminal-header">
            <span class="terminal-dot red"></span>
            <span class="terminal-dot yellow"></span>
            <span class="terminal-dot green"></span>
            <span class="terminal-title">nexus_secure_login.sh</span>
        </div>
        <div class="terminal-body">
            <div class="terminal-row"><span class="term-green">visitor@nexus:~$</span> ./init_auth.sh</div>
            <div class="terminal-row">Establishing secure tunnel... DONE</div>
            <form class="terminal-form" onsubmit="event.preventDefault()">
                <div class="terminal-input-row">
                    <span class="term-green">login:</span>
                    <input type="text" value="admin" readonly />
                </div>
                <div class="terminal-input-row">
                    <span class="term-green">password:</span>
                    <input type="password" placeholder="••••••••" required />
                </div>
                <button type="submit" class="terminal-btn">> EXECUTE AUTH</button>
            </form>
        </div>
    </div>
</div>
```

### CSS
```css
.login-terminal-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #020204;
    padding: 1rem;
    font-family: 'JetBrains Mono', monospace;
}
.terminal-card {
    width: 320px;
    background: #050508;
    border: 1px solid #1f2937;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 10px 30px rgba(0,255,0,0.05);
}
.terminal-header {
    background: #111827;
    padding: 8px 12px;
    display: flex;
    align-items: center;
    gap: 6px;
    border-bottom: 1px solid #1f2937;
}
.terminal-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
}
.terminal-dot.red { background: #ef4444; }
.terminal-dot.yellow { background: #eab308; }
.terminal-dot.green { background: #22c55e; }
.terminal-title {
    color: #9ca3af;
    font-size: 0.75rem;
    margin-left: 8px;
}
.terminal-body {
    padding: 1.25rem;
    color: #10b981;
    font-size: 0.8rem;
    line-height: 1.6;
}
.terminal-row {
    margin-bottom: 8px;
}
.term-green {
    color: #34d399;
}
.terminal-form {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 15px;
}
.terminal-input-row {
    display: flex;
    align-items: center;
    gap: 8px;
}
.terminal-input-row input {
    background: transparent;
    border: none;
    outline: none;
    color: #34d399;
    font-family: inherit;
    font-size: inherit;
    width: 100%;
}
.terminal-btn {
    align-self: flex-start;
    background: transparent;
    border: 1px solid #10b981;
    color: #10b981;
    padding: 4px 10px;
    border-radius: 4px;
    cursor: pointer;
    font-family: inherit;
    font-size: 0.75rem;
    transition: all 0.3s;
    margin-top: 6px;
}
.terminal-btn:hover {
    background: rgba(16, 185, 129, 0.1);
    box-shadow: 0 0 10px rgba(16, 185, 129, 0.3);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function TerminalLogin() {
  const [password, setPassword] = useState("")

  return (
    <div className="flex min-h-screen items-center justify-center bg-black p-4 font-mono">
      <div className="w-full max-w-[340px] rounded-lg border border-zinc-800 bg-zinc-950 shadow-2xl">
        <div className="flex items-center gap-1.5 border-b border-zinc-800 bg-zinc-900 px-4 py-2.5">
          <span className="h-2.5 w-2.5 rounded-full bg-red-500" />
          <span className="h-2.5 w-2.5 rounded-full bg-yellow-500" />
          <span className="h-2.5 w-2.5 rounded-full bg-green-500" />
          <span className="ml-2 text-xs text-zinc-500">nexus_secure_login.sh</span>
        </div>
        <div className="p-5 text-emerald-500 text-sm leading-relaxed">
          <div><span className="text-emerald-400">visitor@nexus:~$</span> ./init_auth.sh</div>
          <div>Establishing secure tunnel... DONE</div>
          <form onSubmit={(e) => e.preventDefault()} className="mt-4 flex flex-col gap-3">
            <div className="flex items-center gap-2">
              <span className="text-emerald-400">login:</span>
              <input type="text" value="admin" readOnly className="bg-transparent text-emerald-500 outline-none" />
            </div>
            <div className="flex items-center gap-2">
              <span className="text-emerald-400">password:</span>
              <input
                type="password"
                value={password}
                onChange={(e) => setPassword(e.target.value)}
                placeholder="••••••••"
                required
                className="bg-transparent text-emerald-500 outline-none placeholder-emerald-950"
              />
            </div>
            <button className="mt-2 self-start rounded border border-emerald-500 px-3 py-1 text-xs transition-all hover:bg-emerald-500/10">
              &gt; EXECUTE AUTH
            </button>
          </form>
        </div>
      </div>
    </div>
  )
}
```

---

## Login #5: Interactive Particle Mesh Login
*A premium portal interactive login sheet set against an active mesh background pattern.*

### HTML
```html
<div class="login-particle-container">
    <div class="particle-mesh-canvas"></div>
    <div class="particle-card">
        <h3>Portal Login</h3>
        <form class="particle-form" onsubmit="event.preventDefault()">
            <input type="text" placeholder="Username" required />
            <input type="password" placeholder="Password" required />
            <button type="submit" class="particle-btn">Enter Portal</button>
        </form>
    </div>
</div>
```

### CSS
```css
.login-particle-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #02040a;
    position: relative;
    overflow: hidden;
    padding: 1rem;
}
.particle-mesh-canvas {
    position: absolute;
    inset: 0;
    opacity: 0.15;
    background-image: 
        radial-gradient(circle at 20% 30%, #6366f1 1px, transparent 1px),
        radial-gradient(circle at 75% 60%, #ec4899 1px, transparent 1px);
    background-size: 40px 40px;
    z-index: 0;
}
.particle-card {
    position: relative;
    z-index: 1;
    width: 320px;
    background: rgba(10, 15, 30, 0.7);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 2.25rem 1.5rem;
    box-shadow: 0 20px 40px rgba(0,0,0,0.5);
    backdrop-filter: blur(10px);
}
.particle-card h3 {
    color: #fff;
    font-size: 1.35rem;
    font-weight: 600;
    margin-bottom: 1.5rem;
    text-align: center;
    letter-spacing: 0.5px;
}
.particle-form {
    display: flex;
    flex-direction: column;
    gap: 12px;
}
.particle-form input {
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 6px;
    padding: 10px 12px;
    color: #fff;
    font-size: 0.85rem;
    outline: none;
    transition: all 0.3s;
}
.particle-form input:focus {
    border-color: #6366f1;
    background: rgba(99, 102, 241, 0.03);
}
.particle-btn {
    background: transparent;
    border: 1px solid #6366f1;
    color: #fff;
    border-radius: 6px;
    padding: 10px;
    font-weight: 600;
    font-size: 0.85rem;
    cursor: pointer;
    transition: all 0.3s;
}
.particle-btn:hover {
    background: #6366f1;
    box-shadow: 0 0 15px rgba(99, 102, 241, 0.4);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function ParticleLogin() {
  const [username, setUsername] = useState("")
  const [password, setPassword] = useState("")

  return (
    <div className="relative flex min-h-screen items-center justify-center bg-[#02040a] p-4 font-sans overflow-hidden">
      <div className="absolute inset-0 opacity-15 bg-[radial-gradient(circle_at_20%_30%,_#6366f1_1px,_transparent_1px),_radial-gradient(circle_at_75%_60%,_#ec4899_1px,_transparent_1px)] bg-[size:40px_40px]" />
      
      <div className="relative z-10 w-full max-w-[320px] rounded-xl border border-white/5 bg-[#0a0f1e]/70 p-8 shadow-2xl backdrop-blur-md">
        <h3 className="text-xl font-semibold text-white mb-6 text-center tracking-wide">Portal Login</h3>
        <form onSubmit={(e) => e.preventDefault()} className="flex flex-col gap-4">
          <input
            type="text"
            placeholder="Username"
            required
            value={username}
            onChange={(e) => setUsername(e.target.value)}
            className="rounded-lg border border-white/10 bg-white/2 px-3.5 py-2 text-sm text-white outline-none focus:border-indigo-500 focus:bg-indigo-500/5"
          />
          <input
            type="password"
            placeholder="Password"
            required
            value={password}
            onChange={(e) => setPassword(e.target.value)}
            className="rounded-lg border border-white/10 bg-white/2 px-3.5 py-2 text-sm text-white outline-none focus:border-indigo-500 focus:bg-indigo-500/5"
          />
          <button className="rounded-lg border border-indigo-500 bg-transparent py-2.5 text-sm font-semibold text-white transition-all hover:bg-indigo-500 hover:shadow-[0_0_15px_rgba(99,_102,_241,_0.4)]">
            Enter Portal
          </button>
        </form>
      </div>
    </div>
  )
}
```

---

## Login #6: Futuristic Hologram Circle Login
*A gorgeous circular hologram-styled interface enclosed within rotating outer rings.*

### HTML
```html
<div class="login-holo-container">
    <div class="holo-spinner-ring"></div>
    <div class="holo-card">
        <div class="holo-header">
            <h4>IDENT SHIELD</h4>
            <div class="holo-line"></div>
        </div>
        <form class="holo-form" onsubmit="event.preventDefault()">
            <input type="text" placeholder="SECURE ID" required />
            <button type="submit" class="holo-btn">INITIALIZE</button>
        </form>
    </div>
</div>
```

### CSS
```css
.login-holo-container {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #030611;
    position: relative;
    overflow: hidden;
    padding: 1rem;
}
.holo-spinner-ring {
    position: absolute;
    width: 250px;
    height: 250px;
    border: 2px dashed rgba(6, 182, 212, 0.2);
    border-radius: 50%;
    animation: holo-spin 15s linear infinite;
    z-index: 0;
}
@keyframes holo-spin {
    100% { transform: rotate(360deg); }
}
.holo-card {
    position: relative;
    z-index: 1;
    width: 200px;
    height: 200px;
    background: rgba(10, 20, 40, 0.85);
    border: 1px solid rgba(6, 182, 212, 0.4);
    border-radius: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 1.5rem;
    box-shadow: 0 0 25px rgba(6, 182, 212, 0.25);
    text-align: center;
}
.holo-header h4 {
    color: #22d3ee;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 2px;
}
.holo-line {
    width: 40px;
    height: 1px;
    background: #22d3ee;
    margin: 8px auto 12px;
    opacity: 0.6;
}
.holo-form {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    width: 100%;
}
.holo-form input {
    width: 100%;
    background: rgba(6, 182, 212, 0.05);
    border: 1px solid rgba(6, 182, 212, 0.2);
    border-radius: 4px;
    padding: 6px 10px;
    color: #fff;
    font-size: 0.75rem;
    text-align: center;
    outline: none;
}
.holo-form input:focus {
    border-color: #22d3ee;
    box-shadow: 0 0 8px rgba(34, 211, 238, 0.3);
}
.holo-btn {
    background: rgba(6, 182, 212, 0.2);
    border: 1px solid #22d3ee;
    color: #22d3ee;
    border-radius: 4px;
    padding: 6px 14px;
    font-weight: 600;
    font-size: 0.7rem;
    cursor: pointer;
    transition: all 0.3s;
}
.holo-btn:hover {
    background: #22d3ee;
    color: #000;
    box-shadow: 0 0 12px rgba(34, 211, 238, 0.5);
}
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useState } from "react"

export function HologramLogin() {
  const [secureId, setSecureId] = useState("")

  return (
    <div className="relative flex min-h-screen items-center justify-center bg-[#030611] p-4 font-mono overflow-hidden">
      <div className="absolute h-[280px] w-[280px] rounded-full border border-dashed border-cyan-500/20 animate-[spin_20s_linear_infinite]" />
      
      <div className="relative z-10 flex h-[220px] w-[220px] flex-col items-center justify-center rounded-full border border-cyan-500/40 bg-slate-950/80 p-6 shadow-[0_0_30px_rgba(6,_182,_212,_0.25)] text-center">
        <h4 className="text-xs font-bold tracking-widest text-cyan-400">IDENT SHIELD</h4>
        <div className="my-2.5 h-[1px] w-10 bg-cyan-400/60" />
        <form onSubmit={(e) => e.preventDefault()} className="flex w-full flex-col items-center gap-3">
          <input
            type="text"
            placeholder="SECURE ID"
            required
            value={secureId}
            onChange={(e) => setSecureId(e.target.value)}
            className="w-full rounded border border-cyan-500/20 bg-cyan-500/5 px-2 py-1.5 text-center text-xs text-white outline-none focus:border-cyan-400 focus:shadow-[0_0_8px_rgba(34,_211,_238,_0.3)]"
          />
          <button className="rounded border border-cyan-400 bg-cyan-400/20 px-3.5 py-1.5 text-[10px] font-bold text-cyan-400 transition-all hover:bg-cyan-400 hover:text-black hover:shadow-[0_0_12px_rgba(34,_211,_238,_0.5)]">
            INITIALIZE
          </button>
        </form>
      </div>
    </div>
  )
}
```
