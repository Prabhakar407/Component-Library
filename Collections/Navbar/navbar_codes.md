# Premium Custom Navbar Code Database

This file contains the complete, self-contained HTML, CSS, and JavaScript code snippets for all **4 Premium Navbars** featured in the interactive showcase. Each navbar is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Effect #1: Neon Underline Sliding Tab](#effect-1-neon-underline-sliding-tab)
2. [Effect #2: Aurora Glow Border Topbar](#effect-2-aurora-glow-border-topbar)
3. [Effect #3: Liquid Indicator Pill Navigation](#effect-3-liquid-indicator-pill-navigation)
4. [Effect #4: Responsive Glow Lamp Topbar/Dock](#effect-4-responsive-glow-lamp-topbardock)

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

// Run once to set initial alignment
updateIndicator(wrap.querySelector('.tab-link.active'));
```

---

## Effect #2: Aurora Glow Border Topbar
*A top navigation bar with branding, whose hover states slide a glowing aurora color-accent indicator dynamically under the selected tab.*

### HTML
```html
<div class="navbar-preview-wrap np-aurora" id="aurora-wrap-2">
    <div class="aurora-navbar">
        <div class="aurora-brand">
            <div class="brand-logo"></div>
            <span>AURA</span>
        </div>
        <div class="aurora-links">
            <a href="#" class="aurora-link active" data-color="indigo">Home</a>
            <a href="#" class="aurora-link" data-color="pink">Gallery</a>
            <a href="#" class="aurora-link" data-color="cyan">Pricing</a>
            <a href="#" class="aurora-link" data-color="purple">Contact</a>
        </div>
        <div class="aurora-glow-line"></div>
    </div>
</div>
```

### CSS
```css
.aurora-navbar {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 60px;
    background: rgba(8, 11, 17, 0.85);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 20px;
    z-index: 10;
}
.aurora-brand {
    display: flex;
    align-items: center;
    gap: 8px;
    color: #fff;
    font-weight: 700;
    letter-spacing: 2px;
    font-size: 0.95rem;
}
.brand-logo {
    width: 20px;
    height: 20px;
    background: linear-gradient(135deg, #6366f1, #ec4899);
    border-radius: 6px;
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.5);
}
.aurora-links {
    display: flex;
    gap: 20px;
}
.aurora-link {
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.5px;
    transition: color 0.3s ease;
    position: relative;
    padding: 8px 0;
}
.aurora-link:hover {
    color: #fff;
}
.aurora-link.active {
    color: #fff;
}
.aurora-glow-line {
    position: absolute;
    bottom: -1px;
    left: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, #6366f1, transparent);
    box-shadow: 0 0 10px #6366f1;
    width: 0;
    opacity: 0;
    transition: all 0.35s cubic-bezier(0.25, 1, 0.5, 1);
    pointer-events: none;
}
```

### JavaScript
```javascript
const wrap = document.getElementById('aurora-wrap-3');
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

// Run once to set initial alignment
updateGlow(wrap.querySelector('.aurora-link.active'));
```

---

## Effect #3: Liquid Indicator Pill Navigation
*An elegant pill-shaped inline navbar featuring a liquid white indicator that slides dynamically behind the active text pill with elastic physics.*

### HTML
```html
<div class="navbar-preview-wrap np-pills" id="pills-wrap-3">
    <div class="pill-nav">
        <a href="#" class="pill-link active">Overview</a>
        <a href="#" class="pill-link">Analytics</a>
        <a href="#" class="pill-link">Campaigns</a>
        <a href="#" class="pill-link">Reports</a>
        <div class="pill-indicator"></div>
    </div>
</div>
```

### CSS
```css
.pill-nav {
    position: relative;
    background: #0d0f17;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 30px;
    padding: 4px;
    display: flex;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
}
.pill-link {
    position: relative;
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 500;
    padding: 10px 24px;
    border-radius: 26px;
    transition: color 0.3s ease;
    z-index: 2;
}
.pill-link:hover {
    color: #fff;
}
.pill-link.active {
    color: #000;
    font-weight: 600;
}
.pill-indicator {
    position: absolute;
    top: 4px;
    bottom: 4px;
    left: 4px;
    width: 0;
    background: #fff;
    border-radius: 26px;
    z-index: 1;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.15);
    box-shadow: 0 4px 10px rgba(255, 255, 255, 0.25);
    pointer-events: none;
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

// Run once to set initial alignment
updatePill(wrap.querySelector('.pill-link.active'));
```

---

## Effect #4: Responsive Glow Lamp Topbar/Dock
*A client-side reactive topbar/dock featuring responsive viewport layouts (full text on desktop, compact icons on mobile) and a sliding background indicator container carrying a custom top-docked neon glow-lamp spotlight effect.*

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
        <a href="#" class="lamp-link">
            <span class="link-text">Messages</span>
            <span class="link-icon">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
            </span>
        </a>
        <a href="#" class="lamp-link">
            <span class="link-text">Settings</span>
            <span class="link-icon">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/></svg>
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
    gap: 8px;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
    position: relative;
}
.lamp-link {
    position: relative;
    color: #94a3b8;
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 600;
    padding: 8px 20px;
    border-radius: 9999px;
    transition: color 0.3s ease;
    cursor: pointer;
    z-index: 2;
    display: flex;
    align-items: center;
    justify-content: center;
}
.lamp-link:hover {
    color: #fff;
}
.lamp-link.active {
    color: #fff;
}
.lamp-indicator {
    position: absolute;
    top: 4px;
    bottom: 4px;
    left: 4px;
    width: 0;
    background: rgba(99, 102, 241, 0.05);
    border-radius: 9999px;
    z-index: 1;
    transition: all 0.35s cubic-bezier(0.25, 1, 0.5, 1);
    pointer-events: none;
}
.lamp-glow-bar {
    position: absolute;
    top: -6px;
    left: 50%;
    transform: translateX(-50%);
    width: 32px;
    height: 2px;
    background: #6366f1;
    border-radius: 4px 4px 0 0;
}
.lamp-glow-bar::before {
    content: '';
    position: absolute;
    width: 48px;
    height: 24px;
    background: rgba(99, 102, 241, 0.2);
    border-radius: 50%;
    filter: blur(8px);
    top: -8px;
    left: -8px;
}
.lamp-glow-bar::after {
    content: '';
    position: absolute;
    width: 32px;
    height: 24px;
    background: rgba(99, 102, 241, 0.2);
    border-radius: 50%;
    filter: blur(8px);
    top: -4px;
    left: 0;
}
.lamp-glow-dot {
    position: absolute;
    width: 16px;
    height: 16px;
    background: rgba(99, 102, 241, 0.2);
    border-radius: 50%;
    filter: blur(4px);
    top: 0;
    left: 8px;
}
.lamp-link .link-text {
    display: inline;
}
.lamp-link .link-icon {
    display: none;
}
@media (max-width: 767px) {
    .lamp-link .link-text {
        display: none;
    }
    .lamp-link .link-icon {
        display: inline-flex;
    }
    .lamp-link {
        padding: 8px 16px;
    }
}
```

### JavaScript
```javascript
const wrap = document.getElementById('lamp-wrap-4');
const links = wrap.querySelectorAll('.lamp-link');
const indicator = wrap.querySelector('.lamp-indicator');

const updateLamp = (el) => {
    indicator.style.left = el.offsetLeft + 'px';
    indicator.style.width = el.offsetWidth + 'px';
};

links.forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        links.forEach(l => l.classList.remove('active'));
        link.classList.add('active');
        updateLamp(link);
    });
});

// Run once to set initial alignment
updateLamp(wrap.querySelector('.lamp-link.active'));

// Align indicator on resize
window.addEventListener('resize', () => {
    const active = wrap.querySelector('.lamp-link.active');
    if (active) updateLamp(active);
});
```

### React/Next.js (Source Component)
```tsx
"use client"

import React, { useEffect, useState } from "react"
import { motion } from "framer-motion"
import Link from "next/link"
import { LucideIcon } from "lucide-react"
import { cn } from "@/lib/utils"

interface NavItem {
  name: string
  url: string
  icon: LucideIcon
}

interface NavBarProps {
  items: NavItem[]
  className?: string
}

export function NavBar({ items, className }: NavBarProps) {
  const [activeTab, setActiveTab] = useState(items[0].name)
  const [isMobile, setIsMobile] = useState(false)

  useEffect(() => {
    const handleResize = () => {
      setIsMobile(window.innerWidth < 768)
    }

    handleResize()
    window.addEventListener("resize", handleResize)
    return () => window.removeEventListener("resize", handleResize)
  }, [])

  return (
    <div
      className={cn(
        "fixed bottom-0 sm:top-0 left-1/2 -translate-x-1/2 z-50 mb-6 sm:pt-6",
        className,
      )}
    >
      <div className="flex items-center gap-3 bg-background/5 border border-border backdrop-blur-lg py-1 px-1 rounded-full shadow-lg">
        {items.map((item) => {
          const Icon = item.icon
          const isActive = activeTab === item.name

          return (
            <Link
              key={item.name}
              href={item.url}
              onClick={() => setActiveTab(item.name)}
              className={cn(
                "relative cursor-pointer text-sm font-semibold px-6 py-2 rounded-full transition-colors",
                "text-foreground/80 hover:text-primary",
                isActive && "bg-muted text-primary",
              )}
            >
              <span className="hidden md:inline">{item.name}</span>
              <span className="md:hidden">
                <Icon size={18} strokeWidth={2.5} />
              </span>
              {isActive && (
                <motion.div
                  layoutId="lamp"
                  className="absolute inset-0 w-full bg-primary/5 rounded-full -z-10"
                  initial={false}
                  transition={{
                    type: "spring",
                    stiffness: 300,
                    damping: 30,
                  }}
                >
                  <div className="absolute -top-2 left-1/2 -translate-x-1/2 w-8 h-1 bg-primary rounded-t-full">
                    <div className="absolute w-12 h-6 bg-primary/20 rounded-full blur-md -top-2 -left-2" />
                    <div className="absolute w-8 h-6 bg-primary/20 rounded-full blur-md -top-1" />
                    <div className="absolute w-4 h-4 bg-primary/20 rounded-full blur-sm top-0 left-2" />
                  </div>
                </motion.div>
              )}
            </Link>
          )
        })}
      </div>
    </div>
  )
}
```
```
