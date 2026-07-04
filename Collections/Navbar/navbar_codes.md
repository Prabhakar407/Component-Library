# Premium Custom Navbar Code Database

This file contains the complete, self-contained HTML, CSS, and React code snippets for all **7 Premium Navbars** featured in the interactive showcase. Each navbar is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Effect #1: Neon Underline Sliding Tab](#effect-1-neon-underline-sliding-tab)
2. [Effect #2: Aurora Glow Border Topbar](#effect-2-aurora-glow-border-topbar)
3. [Effect #3: Liquid Indicator Pill Navigation](#effect-3-liquid-indicator-pill-navigation)
4. [Effect #4: Responsive Glow Lamp Topbar/Dock](#effect-4-responsive-glow-lamp-topbardock)
5. [Effect #5: Sticky Announcement Ribbon](#effect-5-sticky-announcement-ribbon)
6. [Effect #6: Glassmorphism Floating Nav](#effect-6-glassmorphism-floating-nav)
7. [Effect #7: Aura Floating Pill Nav](#effect-7-aura-floating-pill-nav)

---

## Effect #1: Neon Underline Sliding Tab
*A modern capsule tab navigation featuring a sliding gradient background underline that moves smoothly behind the active tab.*

### HTML
```html
<div class="navbar-preview-wrap np-sliding" id="sliding-wrap-1">
    <nav class="sliding-tab-nav">
        <div class="nav-links-wrap">
            <a href="#" class="tab-link active" data-index="0">Home</a>
            <a href="#" class="tab-link" data-index="1">Products</a>
            <a href="#" class="tab-link" data-index="2">Services</a>
            <a href="#" class="tab-link" data-index="3">About</a>
            <div class="sliding-indicator"></div>
        </div>
    </nav>
</div>
```

### CSS
```css
.sliding-tab-nav {
    background: rgba(20, 27, 42, 0.6);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    padding: 6px;
    display: inline-block;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
}
.nav-links-wrap {
    display: flex;
    position: relative;
    gap: 4px;
}
.tab-link {
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 500;
    padding: 8px 18px;
    border-radius: 8px;
    transition: color 0.3s ease;
    position: relative;
    z-index: 2;
}
.tab-link:hover {
    color: #fff;
}
.tab-link.active {
    color: #fff;
}
.sliding-indicator {
    position: absolute;
    bottom: 0;
    top: 0;
    left: 0;
    width: 0;
    background: linear-gradient(135deg, rgba(99, 102, 241, 0.15), rgba(236, 72, 153, 0.15));
    border: 1px solid rgba(99, 102, 241, 0.3);
    border-radius: 8px;
    z-index: 1;
    transition: all 0.35s cubic-bezier(0.25, 1, 0.5, 1);
    box-shadow: 0 0 15px rgba(99, 102, 241, 0.2);
    pointer-events: none;
}
```

### JavaScript
```javascript
const wrap = document.getElementById('sliding-wrap-1');
const links = wrap.querySelectorAll('.tab-link');
const indicator = wrap.querySelector('.sliding-indicator');

const updateIndicator = (el) => {
    indicator.style.left = el.offsetLeft + 'px';
    indicator.style.width = el.offsetWidth + 'px';
};

links.forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        links.forEach(l => l.classList.remove('active'));
        link.classList.add('active');
        updateIndicator(link);
    });
});

// Run once to set initial position
updateIndicator(wrap.querySelector('.tab-link.active'));
```

---

## Effect #2: Aurora Glow Border Topbar
*A topbar layout featuring a thin bottom border that tracks the active link and transitions colors using aurora style gradients.*

### HTML
```html
<div class="navbar-preview-wrap np-aurora" id="aurora-wrap-2">
    <nav class="aurora-nav">
        <a href="#" class="aurora-link active" data-color="indigo">Home</a>
        <a href="#" class="aurora-link" data-color="pink">Campaigns</a>
        <a href="#" class="aurora-link" data-color="cyan">Analytics</a>
        <a href="#" class="aurora-link" data-color="purple">Settings</a>
        <div class="aurora-glow-line"></div>
    </nav>
</div>
```

### CSS
```css
.aurora-nav {
    display: flex;
    position: relative;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
    padding: 0 10px;
    gap: 16px;
}
.aurora-link {
    color: #64748b;
    text-decoration: none;
    font-size: 0.95rem;
    font-weight: 500;
    padding: 14px 8px;
    transition: color 0.3s;
    position: relative;
}
.aurora-link:hover {
    color: #cbd5e1;
}
.aurora-link.active {
    color: #fff;
}
.aurora-glow-line {
    position: absolute;
    bottom: -1px;
    left: 0;
    width: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, #6366f1, transparent);
    transition: all 0.35s cubic-bezier(0.25, 1, 0.5, 1);
    box-shadow: 0 0 8px rgba(99, 102, 241, 0.5);
}
```

### JavaScript
```javascript
const wrap = document.getElementById('aurora-wrap-2');
const links = wrap.querySelectorAll('.aurora-link');
const glow = wrap.querySelector('.aurora-glow-line');

const updateGlow = (el) => {
    glow.style.opacity = '1';
    glow.style.left = el.offsetLeft + 'px';
    glow.style.width = el.offsetWidth + 'px';
    
    const color = el.getAttribute('data-color');
    let colorHex = '#6366f1';
    if (color === 'pink') colorHex = '#ec4899';
    else if (color === 'cyan') colorHex = '#06b6d4';
    else if (color === 'purple') colorHex = '#8b5cf6';
    
    glow.style.background = `linear-gradient(90deg, transparent, ${colorHex}, transparent)`;
    glow.style.boxShadow = `0 0 10px ${colorHex}`;
};

links.forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        links.forEach(l => l.classList.remove('active'));
        link.classList.add('active');
        updateGlow(link);
    });
});

// Run once to set initial position
updateGlow(wrap.querySelector('.aurora-link.active'));
```

---

## Effect #3: Liquid Indicator Pill Navigation
*An indicator capsule navigation that stretches and morphs fluidly between states when navigated.*

### HTML
```html
<div class="navbar-preview-wrap np-pills" id="pills-wrap-3">
    <nav class="pills-nav">
        <a href="#" class="pill-link active">Home</a>
        <a href="#" class="pill-link">Profile</a>
        <a href="#" class="pill-link">Projects</a>
        <a href="#" class="pill-link">Team</a>
        <div class="pill-indicator"></div>
    </nav>
</div>
```

### CSS
```css
.pills-nav {
    display: flex;
    background: #0f172a;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 9999px;
    padding: 6px;
    position: relative;
}
.pill-link {
    color: #64748b;
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 500;
    padding: 8px 20px;
    border-radius: 9999px;
    position: relative;
    z-index: 2;
    transition: color 0.3s;
}
.pill-link:hover {
    color: #e2e8f0;
}
.pill-link.active {
    color: #fff;
}
.pill-indicator {
    position: absolute;
    top: 6px;
    bottom: 6px;
    left: 6px;
    width: 0;
    background: #1e293b;
    border-radius: 9999px;
    z-index: 1;
    transition: all 0.3s cubic-bezier(0.68, -0.6, 0.32, 1.6);
}
```

### JavaScript
```javascript
const wrap = document.getElementById('pills-wrap-3');
const links = wrap.querySelectorAll('.pill-link');
const indicator = wrap.querySelector('.pill-indicator');

const updatePill = (el) => {
    indicator.style.left = el.offsetLeft + 'px';
    indicator.style.width = el.offsetWidth + 'px';
};

links.forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        links.forEach(l => l.classList.remove('active'));
        link.classList.add('active');
        updatePill(link);
    });
});

// Run once to set initial position
updatePill(wrap.querySelector('.pill-link.active'));
```

---

## Effect #4: Responsive Glow Lamp Topbar/Dock
*A docked menu that projects a volumetric lamp/glow onto active icons, featuring elastic transitions.*

### HTML
```html
<div class="navbar-preview-wrap np-lamp" id="lamp-wrap-4">
    <div class="lamp-nav-container">
        <a href="#" class="lamp-link active">
            <span class="link-text">Home</span>
            <span class="link-icon">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="m3 9 9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
            </span>
        </a>
        <a href="#" class="lamp-link">
            <span class="link-text">Projects</span>
            <span class="link-icon">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><rect width="7" height="9" x="3" y="3" rx="1"/><rect width="7" height="5" x="14" y="3" rx="1"/><rect width="7" height="9" x="14" y="12" rx="1"/><rect width="7" height="5" x="3" y="16" rx="1"/></svg>
            </span>
        </a>
        <a href="#" class="lamp-link">
            <span class="link-text">Analytics</span>
            <span class="link-icon">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="20" x2="18" y2="10"/><line x1="12" y1="20" x2="12" y2="4"/><line x1="6" y1="20" x2="6" y2="14"/></svg>
            </span>
        </a>
        <div class="lamp-indicator">
            <div class="lamp-glow-bar">
                <div class="lamp-glow-dot"></div>
            </div>
        </div>
    </div>
</div>
```

### CSS
```css
.lamp-nav-container {
    background: rgba(20, 27, 42, 0.45);
    border: 1px solid rgba(255, 255, 255, 0.08);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    padding: 4px;
    border-radius: 9999px;
    display: flex;
    align-items: center;
    position: relative;
}
.lamp-link {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 10px 24px;
    color: #64748b;
    text-decoration: none;
    transition: color 0.3s;
    font-size: 0.85rem;
}
.lamp-link.active {
    color: #6366f1;
}
.lamp-indicator {
    position: absolute;
    top: 0;
    height: 100%;
    transition: all 0.35s cubic-bezier(0.25, 1, 0.5, 1);
}
.lamp-glow-bar {
    position: absolute;
    top: -1px;
    left: 50%;
    transform: translateX(-50%);
    width: 32px;
    height: 2px;
    background: #6366f1;
    border-radius: 9999px;
    box-shadow: 0 0 10px #6366f1;
}
.lamp-glow-dot {
    position: absolute;
    left: 50%;
    top: 0;
    transform: translate(-50%, -100%);
    width: 24px;
    height: 12px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.3) 0%, transparent 70%);
    border-radius: 50%;
    filter: blur(2px);
}
```

### React
```tsx
import React, { useState } from "react"
import { motion } from "framer-motion"

export function GlowLampNavbar() {
  const [active, setActive] = useState("Home")
  const tabs = ["Home", "Projects", "Analytics"]

  return (
    <div className="relative flex bg-slate-900/50 backdrop-blur-md border border-white/10 rounded-full p-1">
      {tabs.map((tab) => {
        const isActive = active === tab
        return (
          <button
            key={tab}
            onClick={() => setActive(tab)}
            className={`relative px-6 py-2.5 text-sm font-semibold transition-colors duration-300 ${isActive ? "text-indigo-400" : "text-slate-400"}`}
          >
            <span className="relative z-10">{tab}</span>
            {isActive && (
              <motion.div
                layoutId="lamp"
                className="absolute inset-x-0 top-0 h-0.5 bg-indigo-500 shadow-[0_0_8px_#6366f1]"
                transition={{ type: "spring", stiffness: 300, damping: 30 }}
              />
            )}
          </button>
        )
      })}
    </div>
  )
}
```

---

## Effect #5: Sticky Announcement Ribbon
*A sticky marquee-based announcement ribbon bar featured in the top of navigation wrappers, ideal for sliding news updates, promotions, and status changes.*

### HTML
```html
<div class="announcement-ribbon-container">
    <!-- Badge -->
    <div class="announcement-badge">
        <span>NEW</span>
    </div>
    
    <!-- Marquee Container -->
    <div class="announcement-marquee-track">
        <div class="marquee-container">
            <!-- Repeat track 5 times for a seamless loop -->
            <div class="marquee-track">
                <span class="marquee-text">New components and live demos</span>
                <span class="marquee-dot">&middot;</span>
            </div>
            <div class="marquee-track">
                <span class="marquee-text">New components and live demos</span>
                <span class="marquee-dot">&middot;</span>
            </div>
            <div class="marquee-track">
                <span class="marquee-text">New components and live demos</span>
                <span class="marquee-dot">&middot;</span>
            </div>
            <div class="marquee-track">
                <span class="marquee-text">New components and live demos</span>
                <span class="marquee-dot">&middot;</span>
            </div>
            <div class="marquee-track">
                <span class="marquee-text">New components and live demos</span>
                <span class="marquee-dot">&middot;</span>
            </div>
        </div>
    </div>
    
    <!-- CTA -->
    <a href="#" class="announcement-cta">
        Learn more
        <svg class="cta-arrow" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
        </svg>
    </a>
</div>
```

### CSS
```css
.announcement-ribbon-container {
    position: relative;
    display: flex;
    height: 44px;
    width: 100%;
    max-width: 480px;
    align-items: center;
    overflow: hidden;
    background-color: #ffcc00;
    border-bottom: 1px solid rgba(0, 0, 0, 0.08);
    font-family: 'Outfit', sans-serif;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}
.announcement-badge {
    position: relative;
    z-index: 30;
    display: flex;
    flex-shrink: 0;
    align-items: center;
    align-self: stretch;
    background-color: #ffcc00;
    border-right: 1px solid rgba(0, 0, 0, 0.08);
    padding: 0 16px;
}
.announcement-badge span {
    border-radius: 9999px;
    background-color: rgba(0, 0, 0, 0.1);
    padding: 2px 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: #171717;
}
.announcement-marquee-track {
    flex: 1;
    overflow: hidden;
    display: flex;
    align-items: center;
    height: 100%;
}
.marquee-container {
    position: relative;
    display: flex;
    width: 100%;
    height: 100%;
    align-items: center;
    gap: 12px;
    --duration: 10s;
    --gap: 12px;
    overflow: hidden;
}
.marquee-track {
    display: flex;
    flex-shrink: 0;
    gap: var(--gap);
    align-items: center;
    animation: marquee-x-announcement 10s infinite linear;
}
.marquee-container:hover .marquee-track {
    animation-play-state: paused;
}
.marquee-text {
    white-space: nowrap;
    font-family: 'Outfit', sans-serif;
    font-weight: 300;
    color: #171717;
    font-size: 13px;
}
.marquee-dot {
    font-family: 'Outfit', sans-serif;
    color: #171717;
    font-size: 14px;
}
@keyframes marquee-x-announcement {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(calc(-100% - var(--gap)));
    }
}
.announcement-cta {
    position: relative;
    z-index: 30;
    display: flex;
    flex-shrink: 0;
    align-items: center;
    gap: 6px;
    align-self: stretch;
    background-color: #ffcc00;
    border-left: 1px solid rgba(0, 0, 0, 0.08);
    padding: 0 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: rgba(23, 23, 23, 0.6);
    text-decoration: none;
    transition: color 0.2s;
}
.announcement-cta:hover {
    color: #171717;
}
.cta-arrow {
    height: 12px;
    width: 12px;
    transition: transform 0.2s;
}
.announcement-cta:hover .cta-arrow {
    transform: translateX(2px);
}
```

### React
```tsx
"use client";

import React from "react";
import Link from "next/link";
import { cn } from "@/lib/utils";

// --- Custom Marquee Sub-Component ---
interface MarqueeProps extends React.HTMLAttributes<HTMLDivElement> {
  vertical?: boolean;
  repeat?: number;
  reverse?: boolean;
  pauseOnHover?: boolean;
  applyMask?: boolean;
}

export function Marquee({
  children,
  vertical = false,
  repeat = 5,
  pauseOnHover = false,
  reverse = false,
  className,
  applyMask = true,
  ...props
}: MarqueeProps) {
  return (
    <div
      {...props}
      className={cn(
        "group/marquee relative flex h-full w-full p-2 [--duration:10s] [--gap:12px] [gap:var(--gap)] overflow-hidden",
        {
          "flex-col": vertical,
          "flex-row": !vertical,
        },
        className,
      )}
    >
      <style>{`
        @keyframes marquee-x {
          from { transform: translateX(0); }
          to { transform: translateX(calc(-100% - var(--gap))); }
        }
        @keyframes marquee-y {
          from { transform: translateY(0); }
          to { transform: translateY(calc(-100% - var(--gap))); }
        }
        .marquee-horizontal {
          animation: marquee-x var(--duration) infinite linear;
        }
        .marquee-vertical {
          animation: marquee-y var(--duration) infinite linear;
        }
        .group\\/marquee:hover .marquee-pause-on-hover {
          animation-play-state: paused;
        }
      `}</style>
      {Array.from({ length: repeat }).map((_, index) => (
        <div
          key={`item-${index}`}
          className={cn("flex shrink-0 [gap:var(--gap)]", {
            "marquee-pause-on-hover": pauseOnHover,
            "marquee-horizontal flex-row": !vertical,
            "marquee-vertical flex-col": vertical,
          })}
          style={reverse ? { animationDirection: "reverse" } : undefined}
        >
          {children}
        </div>
      ))}
      {applyMask && (
        <div
          className={cn(
            "pointer-events-none absolute inset-0 z-10 h-full w-full from-white/50 from-5% via-transparent via-50% to-white/50 to-95% dark:from-gray-800/50 dark:via-transparent dark:to-gray-800/50",
            {
              "bg-gradient-to-b": vertical,
              "bg-gradient-to-r": !vertical,
            },
          )}
        />
      )}
    </div>
  );
}

// --- Main Announcement Ribbon Component ---
interface AnnouncementRibbonProps extends React.HTMLAttributes<HTMLDivElement> {
  message?: React.ReactNode;
  badge?: string | null;
  ctaText?: string | null;
  ctaHref?: string;
  repeat?: number;
  pauseOnHover?: boolean;
}

function DefaultMessage() {
  return (
    <span>
      <span className="whitespace-nowrap px-12 font-sans font-light text-neutral-900">
        New components and live demos
      </span>
      <span className="text-neutral-900">&middot;</span>
    </span>
  );
}

export default function AnnouncementRibbon({
  message,
  badge = "NEW",
  ctaText = "Learn more",
  ctaHref = "/docs/changelog/2026-05",
  repeat = 5,
  pauseOnHover = true,
  className,
  ...props
}: AnnouncementRibbonProps) {
  const content = message ?? <DefaultMessage />;

  return (
    <div
      className={cn(
        "relative flex h-11 w-full items-center overflow-hidden",
        "bg-[#ffcc00]",
        "border-b border-black/8",
        className,
      )}
      {...props}
    >
      {/* Badge */}
      {badge && (
        <div className="relative z-30 flex bg-[#ffcc00] shrink-0 items-center self-stretch border-r border-black/8 px-4">
          <span className="rounded-full bg-black/10 px-2.5 py-px font-mono text-[10px] font-semibold uppercase tracking-widest text-neutral-900">
            {badge}
          </span>
        </div>
      )}

      <div className="flex-1 overflow-hidden">
        <Marquee repeat={repeat} pauseOnHover={pauseOnHover} applyMask={false}>
          {content}
        </Marquee>
      </div>

      {/* CTA */}
      {ctaText && ctaHref && (
        <Link
          href={ctaHref}
          className="group/cta relative bg-[#ffcc00] z-30 flex shrink-0 items-center gap-1.5 self-stretch border-l border-black/8 px-4 font-mono text-[10px] font-semibold uppercase tracking-widest text-neutral-800/60 transition-colors hover:text-neutral-900 no-underline"
        >
          {ctaText}
          <svg
            className="h-3 w-3 transition-transform group-hover/cta:translate-x-0.5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            strokeWidth={2}
          >
            <path strokeLinecap="round" strokeLinejoin="round" d="M9 5l7 7-7 7" />
          </svg>
        </Link>
      )}
    </div>
  );
}
```

---

## Effect #6: Glassmorphism Floating Nav
*A glassmorphic floating nav container with responsive item anchors, a subtle frosted overlay, and high contrast border highlights.*

### HTML
```html
<div class="max-w-4xl border rounded-full mr-auto ml-auto pt-3 pr-6 pb-3 pl-6 border-white/10"
  style="background: linear-gradient(180deg, rgba(14,16,26,0.55), rgba(14,16,26,0.35)) padding-box, linear-gradient(120deg, rgba(255,255,255,0.35), rgba(255,255,255,0.08)) border-box; border: 1px solid transparent; backdrop-filter: blur(16px) saturate(120%); -webkit-backdrop-filter: blur(16px) saturate(120%); box-shadow: 0 10px 30px rgba(0,0,0,0.25), inset 0 1px 0 rgba(255,255,255,0.04); width: 100%;">
  <div class="flex items-center justify-between">
    <div class="flex items-center">
      <span class="text-lg font-semibold tracking-tight text-white/90">Rulz&amp;Co.</span>
    </div>
    <ul class="hidden md:flex items-center gap-1 text-sm font-medium text-white/60">
      <li class="">
        <a href="#"
          class="transition-colors duration-300 rounded-full pt-2 pr-4 pb-2 pl-4 hover:text-white hover:bg-white/5">Home</a>
      </li>
      <li class="">
        <a href="/services"
          class="transition-colors duration-300 hover:text-white hover:bg-white/5 rounded-full pt-2 pr-4 pb-2 pl-4">Services</a>
      </li>
      <li class="">
        <a href="#"
          class="transition-colors duration-300 rounded-full pt-2 pr-4 pb-2 pl-4 hover:text-white hover:bg-white/5">Works</a>
      </li>
      <li class="">
        <a href="#"
          class="transition-colors duration-300 rounded-full pt-2 pr-4 pb-2 pl-4 hover:text-white hover:bg-white/5">Contact</a>
      </li>
      <li class="">
        <a href="#"
          class="transition-colors duration-300 rounded-full pt-2 pr-4 pb-2 pl-4 hover:text-white hover:bg-white/5">FAQ</a>
      </li>
    </ul>
    <div class="flex items-center gap-1.5 md:gap-2">
      <button class="inline-flex md:hidden p-2 rounded-full transition-all duration-300 border hover:bg-white/5 border-white/5" style="background: rgba(255, 255, 255, 0.02);" aria-label="Menu">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 stroke-[1.5] text-white/70">
          <line x1="4" y1="6" x2="20" y2="6"></line>
          <line x1="4" y1="12" x2="20" y2="12"></line>
          <line x1="4" y1="18" x2="20" y2="18"></line>
        </svg>
      </button>
      <button class="hidden md:inline-flex p-2 rounded-full transition-all duration-300 border hover:bg-white/5 border-white/5" style="background: rgba(255, 255, 255, 0.02);" aria-label="Account">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4 stroke-[1.5] text-white/60">
          <path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"></path>
          <circle cx="12" cy="7" r="4"></circle>
        </svg>
      </button>
    </div>
  </div>
</div>
```

### CSS
```css
/* Requires Tailwind CSS configuration */
```

### React
```tsx
import React from "react"
import { Menu, User } from "lucide-react"

export function GlassFloatingNav() {
  return (
    <div 
      className="max-w-4xl border rounded-full mx-auto py-3 px-6 border-white/10 text-white"
      style={{
        background: "linear-gradient(180deg, rgba(14,16,26,0.55), rgba(14,16,26,0.35)) padding-box, linear-gradient(120deg, rgba(255,255,255,0.35), rgba(255,255,255,0.08)) border-box",
        border: "1px solid transparent",
        backdropFilter: "blur(16px) saturate(120%)",
        WebkitBackdropFilter: "blur(16px) saturate(120%)",
        boxShadow: "0 10px 30px rgba(0,0,0,0.25), inset 0 1px 0 rgba(255,255,255,0.04)"
      }}
    >
      <div className="flex items-center justify-between">
        <div className="flex items-center">
          <span className="text-lg font-semibold tracking-tight text-white/90">Rulz&Co.</span>
        </div>
        <ul className="hidden md:flex items-center gap-1 text-sm font-medium text-white/60 list-none m-0 p-0">
          <li><a href="#" className="transition-colors duration-300 rounded-full py-2 px-4 hover:text-white hover:bg-white/5 no-underline text-white/60">Home</a></li>
          <li><a href="/services" className="transition-colors duration-300 hover:text-white hover:bg-white/5 rounded-full py-2 px-4 no-underline text-white/60">Services</a></li>
          <li><a href="#" className="transition-colors duration-300 rounded-full py-2 px-4 hover:text-white hover:bg-white/5 no-underline text-white/60">Works</a></li>
          <li><a href="#" className="transition-colors duration-300 rounded-full py-2 px-4 hover:text-white hover:bg-white/5 no-underline text-white/60">Contact</a></li>
          <li><a href="#" className="transition-colors duration-300 rounded-full py-2 px-4 hover:text-white hover:bg-white/5 no-underline text-white/60">FAQ</a></li>
        </ul>
        <div className="flex items-center gap-1.5 md:gap-2">
          <button className="inline-flex md:hidden p-2 rounded-full transition-all duration-300 border border-white/5 hover:bg-white/5 bg-white/[0.02] cursor-pointer text-white/70">
            <Menu size={20} strokeWidth={1.5} />
          </button>
          <button className="hidden md:inline-flex p-2 rounded-full transition-all duration-300 border border-white/5 hover:bg-white/5 bg-white/[0.02] cursor-pointer text-white/60">
            <User size={16} strokeWidth={1.5} />
          </button>
        </div>
      </div>
    </div>
  )
}
```

---

## Effect #7: Aura Floating Pill Nav
*A floating pill shaped top navigation bar with a subtle layers icon glow, hover scaling parameters, and a prominent call-to-action button.*

### HTML
```html
<!-- Background Effects -->
<div class="fixed inset-0 grid-bg pointer-events-none z-0"></div>

<!-- Navigation: Pill Shaped & Floating -->
<nav
  class="fixed -translate-x-1/2 flex shadow-black/50 transition-all duration-300 hover:border-white/20 hover:shadow-brand-sky/5 lg:w-fit bg-gradient-to-br from-white/10 to-white/0 w-full max-w-[90vw] z-50 rounded-full ring-white/10 ring-1 pt-1.5 pr-1.5 pb-1.5 pl-4 top-6 left-1/2 shadow-[0_2.8px_2.2px_rgba(0,_0,_0,_0.034),_0_6.7px_5.3px_rgba(0,_0,_0,_0.048),_0_12.5px_10px_rgba(0,_0,_0,_0.06),_0_22.3px_17.9px_rgba(0,_0,_0,_0.072),_0_41.8px_33.4px_rgba(0,_0,_0,_0.086),_0_100px_80px_rgba(0,_0,_0,_0.12)] backdrop-blur-xl items-center justify-between">

  <!-- Logo Area -->
  <div class="flex mr-8 gap-x-2.5 gap-y-2.5 items-center" onclick="window.location.href='/home'" role="button">
    <div class="relative flex items-center justify-center">

      <!-- Subtle glow behind logo -->
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
        style="width: 24px; height: 24px; color: rgb(56, 189, 248);" class="iconify iconify--solar w-[24px] h-[24px]"
        aria-hidden="true" role="img" data-icon="solar:layers-minimalistic-bold-duotone"
        data-solar="forbidden-circle-bold-duotone" data-icon-set="solar" data-icon-replaced="true" stroke-width="2">
        <path fill="#38bdf8"
          d="M4.929 4.929c-3.905 3.905-3.905 10.237 0 14.142s10.237 3.905 14.142 0s3.905-10.237 0-14.142s-10.237-3.905-14.142 0"
          opacity=".5"></path>
        <path fill="#38bdf8" d="M18.521 4.418L4.418 18.521a10 10 0 0 0 1.06 1.061L19.583 5.479a10 10 0 0 0-1.06-1.06-10 10 0 0 0-1.06-1.06">
        </path>
      </svg>
    </div>
    <span class="font-sans font-medium text-base tracking-tight text-white">Aura</span>
  </div>

  <!-- Links (Hidden on small screens) -->
  <div class="hidden md:flex items-center gap-6 mr-8">
    <a href="/features" class="hover:text-white transition-colors text-xs font-medium text-white/50">Features</a>
    <a href="/about" class="hover:text-white transition-colors text-xs font-medium text-white/50">About</a>
    <a href="/pricing" class="hover:text-white transition-colors text-xs font-medium text-white/50">Pricing</a>
  </div>

  <!-- Action Button -->
  <button class="flex hover:bg-brand-sky transition-colors group flex-none text-xs font-semibold text-black bg-white rounded-full pt-2 pr-4 pb-2 pl-4 gap-x-2 gap-y-2 items-center" onclick="window.location.href='/login'" role="button">
            Start Engine
            <svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="img" width="1em" height="1em" viewBox="0 0 24 24" data-icon="solar:arrow-right-bold-duotone" class="iconify group-hover:translate-x-0.5 transition-transform"><path fill="currentColor" d="M13.25 12.75V18a.75.75 0 0 0 1.28.53l6-6a.75.75 0 0 0 0-1.06l-6-6a.75.75 0 0 0-1.28.53z"></path></svg>
        </button>
</nav>
```

### CSS
```css
/* Requires Tailwind CSS configuration */
```

### React
```tsx
import React from "react"
import Link from "next/link"

export function AuraFloatingNav() {
  return (
    <nav
      className="flex shadow-black/50 transition-all duration-300 hover:border-white/20 hover:shadow-sky-400/5 lg:w-fit bg-gradient-to-br from-white/10 to-white/0 w-full max-w-md rounded-full ring-white/10 ring-1 p-1.5 pl-4 items-center justify-between backdrop-blur-xl border border-transparent"
      style={{
        boxShadow: "0 10px 30px rgba(0,0,0,0.25)"
      }}
    >
      {/* Logo Area */}
      <div className="flex mr-8 gap-2.5 items-center cursor-pointer">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          strokeWidth="2"
          className="text-sky-400"
        >
          <path fill="currentColor" d="M4.929 4.929c-3.905 3.905-3.905 10.237 0 14.142s10.237 3.905 14.142 0s3.905-10.237 0-14.142s-10.237-3.905-14.142 0" opacity=".5" />
          <path fill="currentColor" d="M18.521 4.418L4.418 18.521a10 10 0 0 0 1.06 1.061L19.583 5.479a10 10 0 0 0-1.06-1.06" />
        </svg>
        <span className="font-sans font-medium text-base tracking-tight text-white">Aura</span>
      </div>

      {/* Links */}
      <div className="hidden md:flex items-center gap-6 mr-8">
        <Link href="/features" className="hover:text-white transition-colors text-xs font-medium text-white/50 no-underline">Features</Link>
        <Link href="/about" className="hover:text-white transition-colors text-xs font-medium text-white/50 no-underline">About</Link>
        <Link href="/pricing" className="hover:text-white transition-colors text-xs font-medium text-white/50 no-underline">Pricing</Link>
      </div>

      {/* Action Button */}
      <button className="flex hover:bg-sky-400 transition-colors group flex-none text-xs font-semibold text-black bg-white rounded-full py-2 px-4 gap-2 items-center border-none cursor-pointer">
        Start Engine
        <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24" className="group-hover:translate-x-0.5 transition-transform">
          <path fill="currentColor" d="M13.25 12.75V18a.75.75 0 0 0 1.28.53l6-6a.75.75 0 0 0 0-1.06l-6-6a.75.75 0 0 0-1.28.53z" />
        </svg>
      </button>
    </nav>
  )
}
```
