# Premium Miscellaneous Widgets Code Database

This file contains the complete HTML and CSS code snippets for the premium miscellaneous widgets featured in the interactive showcase.

---

## Table of Contents
1. [Widget #1: Interactive Glassmorphic Music Player](#widget-1-interactive-glassmorphic-music-player)
2. [Widget #2: Drag & Drop File Upload Area](#widget-2-drag--drop-file-upload-area)
3. [Widget #3: Expanding Radial Circular Menu](#widget-3-expanding-radial-circular-menu)
4. [Widget #4: Futuristic Command-Line Terminal Simulator](#widget-4-futuristic-command-line-terminal-simulator)
5. [Widget #5: Glassmorphic Weather Dashboard Widget](#widget-5-glassmorphic-weather-dashboard-widget)
6. [Widget #6: Multi-Step Registration Progress Timeline](#widget-6-multi-step-registration-progress-timeline)
7. [Widget #7: Backlight Video Box](#widget-7-backlight-video-box)
8. [Widget #8: Interactive Application Dock](#widget-8-interactive-application-dock)
9. [Widget #9: Magic UI Typing Animation](#widget-9-magic-ui-typing-animation)
10. [Widget #10: MUI Joy UI Basic Table](#widget-10-mui-joy-ui-basic-table)
11. [Widget #11: MUI Joy UI Alert with Decorators](#widget-11-mui-joy-ui-alert-with-decorators)
12. [Widget #12: MUI Joy UI Circular Progress Buttons](#widget-12-mui-joy-ui-circular-progress-buttons)
13. [Widget #13: Controlled Accordion Group](#widget-13-controlled-accordion-group)

---

## Widget #1: Interactive Glassmorphic Music Player

### HTML
```html
<div class="misc-player">
    <div class="player-art">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M9 18V5l12-2v13"></path>
            <circle cx="6" cy="18" r="3"></circle>
            <circle cx="18" cy="16" r="3"></circle>
        </svg>
    </div>
    <div class="player-info">
        <h4>Synthesized Dreams</h4>
        <span class="player-artist">Aether Wave</span>
        <div class="player-progress-bar">
            <div class="player-progress" style="width: 65%;"></div>
        </div>
        <div class="player-controls">
            <button class="player-btn">&#9664;&#9664;</button>
            <button class="player-btn-main">&#9654;</button>
            <button class="player-btn">&#9654;&#9654;</button>
        </div>
    </div>
</div>
```

### CSS
```css
.misc-player {
    display: flex;
    align-items: center;
    gap: 20px;
    width: 320px;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 20px;
    padding: 16px;
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
}

.player-art {
    width: 70px;
    height: 70px;
    background: linear-gradient(135deg, #6366f1, #a855f7);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    box-shadow: 0 5px 15px rgba(99, 102, 241, 0.3);
}

.player-info {
    flex: 1;
    display: flex;
    flex-direction: column;
    text-align: left;
}

.player-info h4 {
    color: #ffffff;
    font-size: 0.95rem;
    font-weight: 600;
    margin-bottom: 2px;
}

.player-artist {
    color: #94a3b8;
    font-size: 0.78rem;
    margin-bottom: 8px;
}

.player-progress-bar {
    width: 100%;
    height: 4px;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 2px;
    margin-bottom: 12px;
    overflow: hidden;
}

.player-progress {
    height: 100%;
    background: #6366f1;
    border-radius: 2px;
}

.player-controls {
    display: flex;
    align-items: center;
    gap: 14px;
}

.player-btn {
    background: transparent;
    border: none;
    color: #cbd5e1;
    cursor: pointer;
    font-size: 0.8rem;
    transition: color 0.2s;
}

.player-btn:hover {
    color: #ffffff;
}

.player-btn-main {
    background: #ffffff;
    color: #0f172a;
    border: none;
    width: 28px;
    height: 28px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.75rem;
    cursor: pointer;
    transition: transform 0.2s;
}

.player-btn-main:hover {
    transform: scale(1.1);
}
```

---

## Widget #2: Drag & Drop File Upload Area

### HTML
```html
<div class="misc-upload">
    <div class="upload-icon">
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
            <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
            <polyline points="17 8 12 3 7 8"></polyline>
            <line x1="12" y1="3" x2="12" y2="15"></line>
        </svg>
    </div>
    <p class="upload-text">Drag and drop file here, or <span class="highlight">browse</span></p>
    <span class="upload-note">Support PDF, PNG, JPEG (Max 10MB)</span>
</div>
```

### CSS
```css
.misc-upload {
    width: 320px;
    background: #0f172a;
    border: 2px dashed rgba(255, 255, 255, 0.1);
    border-radius: 16px;
    padding: 28px 20px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s;
}

.misc-upload:hover {
    border-color: #6366f1;
    background: rgba(99, 102, 241, 0.02);
    box-shadow: 0 0 15px rgba(99, 102, 241, 0.1);
}

.upload-icon {
    color: #94a3b8;
    margin-bottom: 12px;
    transition: color 0.3s, transform 0.3s;
}

.misc-upload:hover .upload-icon {
    color: #6366f1;
    transform: translateY(-2px);
}

.upload-text {
    color: #cbd5e1;
    font-size: 0.88rem;
    margin-bottom: 6px;
}

.upload-text .highlight {
    color: #818cf8;
    font-weight: 600;
}

.upload-note {
    color: #64748b;
    font-size: 0.72rem;
}
```

---

## Widget #3: Expanding Radial Circular Menu

### HTML
```html
<div class="misc-menu-container">
    <div class="misc-radial-menu">
        <button class="radial-center-btn" aria-label="Toggle Menu">+</button>
        <button class="radial-item item-1" aria-label="Home">&#127968;</button>
        <button class="radial-item item-2" aria-label="Settings">&#9881;</button>
        <button class="radial-item item-3" aria-label="Profile">&#128100;</button>
    </div>
</div>
```

### CSS
```css
.misc-menu-container {
    width: 150px;
    height: 150px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.misc-radial-menu {
    position: relative;
    width: 50px;
    height: 50px;
}

.radial-center-btn {
    position: absolute;
    inset: 0;
    width: 50px;
    height: 50px;
    background: #6366f1;
    color: white;
    border: none;
    border-radius: 50%;
    font-size: 1.5rem;
    font-weight: 600;
    cursor: pointer;
    z-index: 10;
    box-shadow: 0 4px 15px rgba(99, 102, 241, 0.4);
    transition: all 0.3s;
}

.misc-radial-menu:hover .radial-center-btn {
    transform: rotate(45deg);
    background: #4f46e5;
}

.radial-item {
    position: absolute;
    top: 5px;
    left: 5px;
    width: 40px;
    height: 40px;
    background: #1e293b;
    border: 1px solid rgba(255, 255, 255, 0.08);
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.95rem;
    cursor: pointer;
    opacity: 0;
    z-index: 1;
    transition: all 0.4s cubic-bezier(0.68, -0.55, 0.27, 1.55);
}

.misc-radial-menu:hover .radial-item {
    opacity: 1;
}

.misc-radial-menu:hover .item-1 {
    transform: translate(-55px, -55px);
}

.misc-radial-menu:hover .item-2 {
    transform: translate(55px, -55px);
}

.misc-radial-menu:hover .item-3 {
    transform: translate(0px, 70px);
}
```

---

## Widget #4: Futuristic Command-Line Terminal Simulator

### HTML
```html
<div class="misc-terminal">
    <div class="terminal-header">
        <div class="terminal-dots">
            <span class="dot close"></span>
            <span class="dot minimize"></span>
            <span class="dot expand"></span>
        </div>
        <span class="terminal-title">antigravity.sh</span>
    </div>
    <div class="terminal-body">
        <div class="terminal-line"><span class="prompt">guest@ag:~$</span> agy system --status</div>
        <div class="terminal-line response">System running with 0 failures. 6 premium modules configured.</div>
        <div class="terminal-line"><span class="prompt">guest@ag:~$</span> <span class="cursor"></span></div>
    </div>
</div>
```

### CSS
```css
.misc-terminal {
    width: 320px;
    background: #090d16;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.45);
    font-family: 'JetBrains Mono', monospace;
    text-align: left;
}

.terminal-header {
    background: #0f1524;
    padding: 8px 14px;
    display: flex;
    align-items: center;
    border-bottom: 1px solid rgba(255, 255, 255, 0.04);
}

.terminal-dots {
    display: flex;
    gap: 6px;
}

.terminal-dots .dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
}

.terminal-dots .dot.close { background: #ef4444; }
.terminal-dots .dot.minimize { background: #f59e0b; }
.terminal-dots .dot.expand { background: #10b981; }

.terminal-title {
    color: #64748b;
    font-size: 0.72rem;
    margin-left: 20px;
}

.terminal-body {
    padding: 16px;
    font-size: 0.8rem;
    color: #cbd5e1;
    min-height: 110px;
}

.terminal-line {
    margin-bottom: 6px;
    display: flex;
    align-items: center;
}

.terminal-line .prompt {
    color: #10b981;
    margin-right: 6px;
}

.terminal-line.response {
    color: #6366f1;
}

.terminal-line .cursor {
    width: 6px;
    height: 14px;
    background: #cbd5e1;
    animation: cursor-blink 1s step-end infinite;
}

@keyframes cursor-blink {
    50% { opacity: 0; }
}
```

---

## Widget #5: Glassmorphic Weather Dashboard Widget

### HTML
```html
<div class="misc-weather">
    <div class="weather-main">
        <span class="weather-temp">72&deg;</span>
        <div class="weather-info">
            <h4>Sunnyvale</h4>
            <span>Clear Skies</span>
        </div>
    </div>
    <div class="weather-details">
        <div class="w-detail">
            <span class="label">Wind</span>
            <span class="value">8 mph</span>
        </div>
        <div class="w-detail">
            <span class="label">Humid</span>
            <span class="value">45%</span>
        </div>
    </div>
</div>
```

### CSS
```css
.misc-weather {
    width: 320px;
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.02));
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 20px;
    padding: 20px;
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
    text-align: left;
}

.weather-main {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 16px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
    padding-bottom: 14px;
}

.weather-temp {
    font-size: 2.5rem;
    font-weight: 700;
    color: #ffffff;
}

.weather-info h4 {
    color: #ffffff;
    font-size: 1rem;
    font-weight: 600;
}

.weather-info span {
    color: #94a3b8;
    font-size: 0.78rem;
}

.weather-details {
    display: flex;
    justify-content: space-between;
}

.w-detail {
    display: flex;
    flex-direction: column;
}

.w-detail .label {
    color: #64748b;
    font-size: 0.75rem;
    margin-bottom: 2px;
}

.w-detail .value {
    color: #cbd5e1;
    font-size: 0.85rem;
    font-weight: 600;
}
```

---

## Widget #6: Multi-Step Registration Progress Timeline

### HTML
```html
<div class="misc-timeline">
    <div class="timeline-step done">
        <span class="step-circle">&#10003;</span>
        <span class="step-label">Account</span>
    </div>
    <div class="timeline-line done"></div>
    <div class="timeline-step active">
        <span class="step-circle">2</span>
        <span class="step-label">Profile</span>
    </div>
    <div class="timeline-line"></div>
    <div class="timeline-step">
        <span class="step-circle">3</span>
        <span class="step-label">Billing</span>
    </div>
</div>
```

### CSS
```css
.misc-timeline {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 320px;
    background: #0f172a;
    border: 1px solid rgba(255, 255, 255, 0.04);
    border-radius: 12px;
    padding: 16px 20px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
}

.timeline-step {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
}

.step-circle {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: #1e293b;
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: #94a3b8;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.75rem;
    font-weight: 600;
    transition: all 0.3s;
}

.step-label {
    color: #64748b;
    font-size: 0.72rem;
    font-weight: 500;
}

.timeline-line {
    flex: 1;
    height: 2px;
    background: rgba(255, 255, 255, 0.1);
    margin: 0 10px;
    transform: translateY(-8px);
}

.timeline-step.done .step-circle {
    background: rgba(16, 185, 129, 0.15);
    border-color: #10b981;
    color: #10b981;
}

.timeline-step.done .step-label {
    color: #10b981;
}

.timeline-line.done {
    background: #10b981;
}

.timeline-step.active .step-circle {
    background: rgba(99, 102, 241, 0.15);
    border-color: #6366f1;
    color: #a5b4fc;
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.25);
}

.timeline-step.active .step-label {
    color: #a5b4fc;
    font-weight: 600;
}
```

---

## Widget #7: Backlight Video Box

### HTML
```html
<div class="backlight-container">
  <div class="backlight-glow"></div>
  <div class="backlight-glow-secondary"></div>
  <iframe
    class="video-frame"
    src="https://www.youtube.com/embed/9CJLtzzUphU"
    title="Gradient Loop Background"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen
  ></iframe>
</div>
```

### CSS
```css
.backlight-container {
  position: relative;
  width: 100%;
  max-width: 320px;
  aspect-ratio: 16/9;
  border-radius: 16px;
  overflow: visible;
  margin: 0 auto;
  transition: transform 0.5s cubic-bezier(0.2, 1, 0.2, 1);
  background: rgba(255, 255, 255, 0.03);
  padding: 3px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
}
.backlight-container:hover {
  transform: scale(1.05) translateY(-5px);
}
.backlight-glow {
  position: absolute;
  inset: -15px;
  background: radial-gradient(circle, rgba(99,102,241,0.6) 0%, rgba(236,72,153,0.3) 50%, transparent 80%);
  filter: blur(35px);
  pointer-events: none;
  z-index: 1;
  border-radius: 20px;
  animation: pulse-glow 6s infinite alternate ease-in-out;
  transition: opacity 0.5s;
}
.backlight-glow-secondary {
  position: absolute;
  inset: -25px;
  background: radial-gradient(circle, rgba(59,130,246,0.4) 0%, transparent 70%);
  filter: blur(50px);
  pointer-events: none;
  z-index: 0;
  animation: float-glow 8s infinite alternate ease-in-out;
}
@keyframes pulse-glow {
  0% { transform: scale(0.95); opacity: 0.7; }
  100% { transform: scale(1.05); opacity: 1.0; }
}
@keyframes float-glow {
  0% { transform: translate(-10px, -10px) scale(0.9); }
  100% { transform: translate(10px, 10px) scale(1.1); }
}
.video-frame {
  position: relative;
  width: 100%;
  height: 100%;
  border-radius: 14px;
  border: 1px solid rgba(255,255,255,0.15);
  z-index: 2;
  box-shadow: inset 0 0 10px rgba(255,255,255,0.1);
}
```

---

## Widget #8: Interactive Application Dock

### HTML
```html
<div class="dock-container">
  <div class="dock">
    <div class="dock-item active" data-label="Home" onclick="triggerDockBounce(this)">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m3 9 9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/></svg>
      <span class="dock-indicator"></span>
    </div>
    <div class="dock-item" data-label="Blog" onclick="triggerDockBounce(this)">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 20h9"/><path d="M16.5 3.5a2.12 2.12 0 0 1 3 3L7 19l-4 1 1-4Z"/></svg>
      <span class="dock-indicator"></span>
    </div>
    <div class="dock-separator"></div>
    <div class="dock-item" data-label="GitHub" onclick="triggerDockBounce(this)">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"/></svg>
      <span class="dock-indicator"></span>
    </div>
    <div class="dock-item" data-label="Email" onclick="triggerDockBounce(this)">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
      <span class="dock-indicator"></span>
    </div>
  </div>
</div>
```

### CSS
```css
.dock-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 120px;
  position: relative;
}
.dock {
  display: inline-flex;
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.1);
  padding: 12px 18px;
  border-radius: 24px;
  gap: 16px;
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  align-items: flex-end;
  box-shadow: 
    0 20px 40px rgba(0, 0, 0, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.2);
  transition: all 0.3s cubic-bezier(0.25, 1, 0.5, 1);
}
.dock-item {
  width: 48px;
  height: 48px;
  background: linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0.03));
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #e2e8f0;
  cursor: pointer;
  transition: all 0.3s cubic-bezier(0.25, 1, 0.5, 1);
  position: relative;
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}
.dock-item:hover {
  transform: scale(1.35) translateY(-10px);
  color: #6366f1;
  border-color: rgba(99,102,241,0.4);
  box-shadow: 0 10px 20px rgba(99,102,241,0.25);
  background: rgba(255,255,255,0.15);
}
.dock-item::before {
  content: attr(data-label);
  position: absolute;
  top: -36px;
  background: rgba(15, 23, 42, 0.9);
  color: white;
  padding: 4px 8px;
  border-radius: 6px;
  font-size: 0.7rem;
  opacity: 0;
  pointer-events: none;
  transform: scale(0.8) translateY(10px);
  transition: all 0.2s cubic-bezier(0.25, 1, 0.5, 1);
  white-space: nowrap;
  box-shadow: 0 4px 10px rgba(0,0,0,0.3);
  border: 1px solid rgba(255,255,255,0.08);
}
.dock-item:hover::before {
  opacity: 1;
  transform: scale(1) translateY(0);
}
.dock-separator {
  width: 1px;
  height: 36px;
  background: rgba(255,255,255,0.15);
  align-self: center;
}
.dock-indicator {
  position: absolute;
  bottom: 3px;
  width: 4px;
  height: 4px;
  background: #6366f1;
  border-radius: 50%;
  opacity: 0;
  transform: scale(0.5);
  transition: all 0.3s;
  box-shadow: 0 0 6px #6366f1;
}
.dock-item.active .dock-indicator {
  opacity: 1;
  transform: scale(1);
}
.dock-item.bounce {
  animation: bounce 0.6s cubic-bezier(0.28, 0.84, 0.42, 1);
}
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  30% { transform: translateY(-24px) scaleY(1.1) scaleX(0.9); }
  50% { transform: translateY(0) scaleY(0.9) scaleX(1.05); }
  70% { transform: translateY(-8px) scaleY(1.02) scaleX(0.98); }
  90% { transform: translateY(0) scaleY(0.98) scaleX(1.01); }
}
```

### JavaScript
```javascript
window.triggerDockBounce = function(el) {
  el.classList.add("bounce");
  el.parentNode.querySelectorAll(".dock-item").forEach(item => item.classList.remove("active"));
  el.classList.add("active");
  setTimeout(() => {
    el.classList.remove("bounce");
  }, 600);
};
```

### React
```tsx
"use client"

import React from "react"
import Link from "next/link"
import { CalendarIcon, HomeIcon, MailIcon, PencilIcon } from "lucide-react"

import { cn } from "@/lib/utils"
import { buttonVariants } from "@/components/ui/button"
import { Separator } from "@/components/ui/separator"
import {
  Tooltip,
  TooltipContent,
  TooltipProvider,
  TooltipTrigger,
} from "@/components/ui/tooltip"
import { Dock, DockIcon } from "@/registry/magicui/dock"

export type IconProps = React.HTMLAttributes<SVGElement>

const Icons = {
  calendar: (props: IconProps) => <CalendarIcon {...props} />,
  email: (props: IconProps) => <MailIcon {...props} />,
  linkedin: (props: IconProps) => (
    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" {...props}>
      <title>LinkedIn</title>
      <path
        fill="currentColor"
        d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
      />
    </svg>
  ),
  x: (props: IconProps) => (
    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" {...props}>
      <title>X</title>
      <path
        fill="currentColor"
        d="M18.901 1.153h3.68l-8.04 9.19L24 22.846h-7.406l-5.8-7.584-6.638 7.584H.474l8.6-9.83L0 1.154h7.594l5.243 6.932ZM17.61 20.644h2.039L6.486 3.24H4.298Z"
      />
    </svg>
  ),
  youtube: (props: IconProps) => (
    <svg
      width="32px"
      height="32px"
      viewBox="0 0 32 32"
      fill="currentColor"
      xmlns="http://www.w3.org/2000/svg"
      {...props}
    >
      <title>youtube</title>
      <path d="M29.41,9.26a3.5,3.5,0,0,0-2.47-2.47C24.76,6.2,16,6.2,16,6.2s-8.76,0-10.94.59A3.5,3.5,0,0,0,2.59,9.26,36.13,36.13,0,0,0,2,16a36.13,36.13,0,0,0,.59,6.74,3.5,3.5,0,0,0,2.47,2.47C7.24,25.8,16,25.8,16,25.8s8.76,0,10.94-.59a3.5,3.5,0,0,0,2.47-2.47A36.13,36.13,0,0,0,30,16,36.13,36.13,0,0,0,29.41,9.26ZM13.2,20.2V11.8L20.47,16Z" />
    </svg>
  ),
  github: (props: IconProps) => (
    <svg viewBox="0 0 438.549 438.549" {...props}>
      <path
        fill="currentColor"
        d="M409.132 114.573c-19.608-33.596-46.205-60.194-79.798-79.8-33.598-19.607-70.277-29.408-110.063-29.408-39.781 0-76.472 9.804-110.063 29.408-39.781 0-76.472 9.804-110.063 29.408-39.781 0-76.472 9.804-110.063 29.408-33.596 19.605-60.192 46.204-79.8 79.8C9.803 148.168 0 184.854 0 224.63c0 47.78 13.94 90.745 41.827 128.906 27.884 38.164 63.906 64.572 108.063 79.227 5.14.954 8.945.283 11.419-1.996 2.475-2.282 3.711-5.14 3.711-8.562 0-.571-.049-5.708-.144-15.417a2549.81 2549.81 0 01-.144-25.406l-6.567 1.136c-4.187.767-9.469 1.092-15.846 1-6.374-.089-12.991-.757-19.842-1.999-6.854-1.231-13.229-4.086-19.13-8.559-5.898-4.473-10.085-10.328-12.56-17.556l-2.855-6.57c-1.903-4.374-4.899-9.233-8.992-14.559-4.093-5.331-8.232-8.945-12.419-10.848l-1.999-1.431c-1.332-.951-2.568-2.098-3.711-3.429-1.142-1.331-1.997-2.663-2.568-3.997-.572-1.335-.098-2.43 1.427-3.289 1.525-.859 4.281-1.276 8.28-1.276l5.708.853c3.807.763 8.516 3.042 14.133 6.851 5.614 3.806 10.229 8.754 13.846 14.842 4.38 7.806 9.657 13.754 15.846 17.847 6.184 4.093 12.419 6.136 18.699 6.136 6.28 0 11.704-.476 16.274-1.423 4.565-.952 8.848-2.383 12.847-4.285 1.713-12.758 6.377-22.559 13.988-29.41-10.848-1.14-20.601-2.857-29.264-5.14-8.658-2.286-17.605-5.996-26.835-11.14-9.235-5.137-16.896-11.516-22.985-19.126-6.09-7.614-11.088-17.61-14.987-29.979-3.901-12.374-5.852-26.648-5.852-42.826 0-23.035 7.52-42.637 22.557-58.817-7.044-17.318-6.379-36.732 1.997-58.24 5.52-1.715 13.706-.428 24.554 3.853 10.85 4.283 18.794 7.952 23.84 10.994 5.046 3.041 9.089 5.618 12.135 7.708 17.705-4.947 35.976-7.421 54.818-7.421s37.117 2.474 54.823 7.421l10.849-6.849c7.419-4.57 16.18-8.758 26.262-12.565 10.088-3.805 17.802-4.853 23.134-3.138 8.562 21.509 9.325 40.922 2.279 58.24 15.036 16.18 22.559 35.787 22.559 58.817 0 16.178-1.958 30.497-5.853 42.966-3.9 12.471-8.941 22.457-15.125 29.979-6.191 7.521-13.901 13.85-23.131 18.986-9.232 5.14-18.182 8.85-26.84 11.136-8.662 2.286-18.415 4.004-29.263 5.146 9.894 8.562 14.842 22.077 14.842 40.539v60.237c0 3.422 1.19 6.279 3.572 8.562 2.379 2.279 6.136 2.95 11.276 1.995 44.163-14.653 80.185-41.062 108.068-79.226 27.88-38.161 41.825-81.126 41.825-128.906-.01-39.771-9.818-76.454-29.414-110.049z"
      ></path>
    </svg>
  ),
}

const DATA = {
  navbar: [
    { href: "#", icon: HomeIcon, label: "Home" },
    { href: "#", icon: PencilIcon, label: "Blog" },
  ],
  contact: {
    social: {
      GitHub: {
        name: "GitHub",
        url: "#",
        icon: Icons.github,
      },
      LinkedIn: {
        name: "LinkedIn",
        url: "#",
        icon: Icons.linkedin,
      },
      X: {
        name: "X",
        url: "#",
        icon: Icons.x,
      },
      email: {
        name: "Send Email",
        url: "#",
        icon: Icons.email,
      },
    },
  },
}

export function DockDemo() {
  return (
    <div className="flex flex-col items-center justify-center">
      <span className="pointer-events-none bg-gradient-to-b from-black to-gray-300/80 bg-clip-text text-center text-8xl leading-none font-semibold whitespace-pre-wrap text-transparent dark:from-white dark:to-slate-900/10">
        Dock
      </span>
      <TooltipProvider>
        <Dock direction="middle">
          {DATA.navbar.map((item) => (
            <DockIcon key={item.label}>
              <Tooltip>
                <TooltipTrigger asChild>
                  <Link
                    href={item.href}
                    aria-label={item.label}
                    className={cn(
                      buttonVariants({ variant: "ghost", size: "icon" }),
                      "size-12 rounded-full"
                    )}
                  >
                    <item.icon className="size-4" />
                  </Link>
                </TooltipTrigger>
                <TooltipContent>
                  <p>{item.label}</p>
                </TooltipContent>
              </Tooltip>
            </DockIcon>
          ))}
          <Separator orientation="vertical" className="h-full" />
          {Object.entries(DATA.contact.social).map(([name, social]) => (
            <DockIcon key={name}>
              <Tooltip>
                <TooltipTrigger asChild>
                  <Link
                    href={social.url}
                    aria-label={social.name}
                    className={cn(
                      buttonVariants({ variant: "ghost", size: "icon" }),
                      "size-12 rounded-full"
                    )}
                  >
                    <social.icon className="size-4" />
                  </Link>
                </TooltipTrigger>
                <TooltipContent>
                  <p>{name}</p>
                </TooltipContent>
              </Tooltip>
            </DockIcon>
          ))}
        </Dock>
      </TooltipProvider>
    </div>
  )
}
```

---

## Widget #9: Magic UI Typing Animation

### HTML
```html
<div class="typing-animation-container">
  <span class="typing-animation-text" id="typing-text-9"></span>
</div>
```

### CSS
```css
.typing-animation-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 80px;
  font-family: var(--font-main);
  padding: 10px;
}
.typing-animation-text {
  font-size: 2.2rem;
  font-weight: 800;
  background: linear-gradient(135deg, #a855f7 0%, #6366f1 50%, #06b6d4 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  letter-spacing: -0.03em;
  position: relative;
  display: inline-block;
  filter: drop-shadow(0 4px 12px rgba(168, 85, 247, 0.25));
}
.typing-animation-text::after {
  content: '';
  position: absolute;
  right: -8px;
  top: 10%;
  height: 80%;
  width: 3px;
  background: linear-gradient(to bottom, #a855f7, #06b6d4);
  animation: blink-caret 0.8s infinite step-end;
  box-shadow: 0 0 8px rgba(6, 182, 212, 0.8);
}
@keyframes blink-caret {
  from, to { background: transparent; box-shadow: none; }
  50% { background: linear-gradient(to bottom, #a855f7, #06b6d4); box-shadow: 0 0 8px rgba(6, 182, 212, 0.8); }
}
```

### JavaScript
```javascript
(() => {
  const textElement = document.getElementById("typing-text-9");
  if (textElement) {
    const text = "Hello World! 👋";
    let i = 0;
    textElement.textContent = "";
    const typing = setInterval(() => {
      if (i < text.length) {
        textElement.textContent += text.charAt(i);
        i++;
      } else {
        clearInterval(typing);
      }
    }, 100);
  }
})();
```

### React/Next.js
```tsx
import { TypingAnimation } from "@/registry/magicui/typing-animation"

export function Component() {
  return <TypingAnimation>Hello World! 👋</TypingAnimation>
}
```

