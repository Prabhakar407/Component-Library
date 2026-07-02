# Premium Custom Announcements Code Database

This file contains the complete, self-contained HTML, CSS, JavaScript, and React code snippets for all **8 Premium Announcement Displays** featured in the interactive showcase. Each display is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Effect #1: Neon Sticky Banner](#effect-1-neon-sticky-banner)
2. [Effect #2: Glassmorphic Floating Toast](#effect-2-glassmorphic-floating-toast)
3. [Effect #3: Cosmic Modal Alert](#effect-3-cosmic-modal-alert)
4. [Effect #4: Pulsing Feature Badge](#effect-4-pulsing-feature-badge)
5. [Effect #5: Sliding News Ticker](#effect-5-sliding-news-ticker)
6. [Effect #6: Expandable Info Drawer](#effect-6-expandable-info-drawer)
7. [Effect #7: Premium Launch Countdown](#effect-7-premium-launch-countdown)
8. [Effect #8: Aggregated Feed Card](#effect-8-aggregated-feed-card)

---

## Effect #1: Neon Sticky Banner
*Sticky top bar notification banner with a glowing border, floating text, and a smooth close trigger.*

### HTML
```html
<div class="announcement-banner-1" id="banner-1">
    <span class="pulse-dot-1"></span>
    <p class="banner-text-1"><strong>Update:</strong> We have released Component Library v2.4. Check it out!</p>
    <button class="banner-close-1" onclick="dismissBanner1()">✕</button>
</div>
<button class="banner-trigger-1 hidden" id="trigger-1" onclick="showBanner1()">Reset Banner</button>
```

### CSS
```css
.announcement-banner-1 {
    position: absolute;
    top: 15px;
    left: 15px;
    right: 15px;
    background: rgba(10, 14, 23, 0.85);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(99, 102, 241, 0.4);
    box-shadow: 0 4px 20px rgba(99, 102, 241, 0.15), inset 0 0 15px rgba(99, 102, 241, 0.1);
    border-radius: 8px;
    padding: 12px 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
    z-index: 100;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.announcement-banner-1.dismissed {
    opacity: 0;
    transform: translateY(-20px) scale(0.95);
    pointer-events: none;
}

.pulse-dot-1 {
    width: 8px;
    height: 8px;
    background-color: #6366f1;
    border-radius: 50%;
    box-shadow: 0 0 0 0 rgba(99, 102, 241, 0.7);
    animation: pulse-1 1.5s infinite;
    flex-shrink: 0;
}

@keyframes pulse-1 {
    0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(99, 102, 241, 0.7); }
    70% { transform: scale(1); box-shadow: 0 0 0 8px rgba(99, 102, 241, 0); }
    100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(99, 102, 241, 0); }
}

.banner-text-1 {
    font-size: 0.85rem;
    color: #f8fafc;
    margin: 0;
    flex-grow: 1;
    line-height: 1.4;
    text-align: left;
}

.banner-text-1 strong {
    color: #818cf8;
}

.banner-close-1 {
    background: transparent;
    border: none;
    color: #94a3b8;
    cursor: pointer;
    font-size: 0.95rem;
    transition: color 0.2s;
    padding: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.banner-close-1:hover {
    color: #f8fafc;
}

.banner-trigger-1 {
    background: rgba(99, 102, 241, 0.15);
    border: 1px solid #6366f1;
    color: #a5b4fc;
    padding: 10px 20px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 0.85rem;
    font-weight: 600;
    transition: all 0.3s;
}

.banner-trigger-1:hover {
    background: rgba(99, 102, 241, 0.25);
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.2);
}

.banner-trigger-1.hidden {
    display: none;
}
```

### JavaScript
```javascript
function dismissBanner1() {
    document.getElementById('banner-1').classList.add('dismissed');
    setTimeout(() => {
        document.getElementById('trigger-1').classList.remove('hidden');
    }, 300);
}

function showBanner1() {
    document.getElementById('banner-1').classList.remove('dismissed');
    document.getElementById('trigger-1').classList.add('hidden');
}
```

### React
```tsx
import React, { useState } from 'react';

export function NeonStickyBanner() {
  const [visible, setVisible] = useState(true);

  return (
    <div style={{ position: 'relative', width: '100%', minHeight: '60px', padding: '15px' }}>
      {visible ? (
        <div className="announcement-banner-1">
          <span className="pulse-dot-1"></span>
          <p className="banner-text-1">
            <strong>Update:</strong> We have released Component Library v2.4. Check it out!
          </p>
          <button className="banner-close-1" onClick={() => setVisible(false)}>✕</button>
        </div>
      ) : (
        <button className="banner-trigger-1" onClick={() => setVisible(true)}>
          Reset Banner
        </button>
      )}
    </div>
  );
}
```

---

## Effect #2: Glassmorphic Floating Toast
*Translucent, blurred bottom-right floating pop-up card containing an illustrative icon, brief content, and call to action.*

### HTML
```html
<div class="toast-card-2" id="toast-2">
    <div class="toast-header-2">
        <div class="toast-icon-2">🚀</div>
        <div class="toast-title-2">New Feature Available</div>
        <button class="toast-close-2" onclick="dismissToast2()">✕</button>
    </div>
    <div class="toast-body-2">
        We've integrated AI Code Generation in your development console. Start drafting now.
    </div>
    <div class="toast-footer-2">
        <button class="toast-btn-2">Explore</button>
    </div>
</div>
<button class="toast-trigger-2 hidden" id="trigger-2" onclick="showToast2()">Trigger Toast</button>
```

### CSS
```css
.toast-card-2 {
    position: absolute;
    bottom: 15px;
    right: 15px;
    width: 320px;
    background: rgba(24, 32, 50, 0.7);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    padding: 16px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
    z-index: 100;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    transform: scale(1);
    opacity: 1;
}

.toast-card-2.dismissed {
    transform: translateY(20px) scale(0.9);
    opacity: 0;
    pointer-events: none;
}

.toast-header-2 {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
    position: relative;
}

.toast-icon-2 {
    font-size: 1.2rem;
}

.toast-title-2 {
    font-size: 0.9rem;
    font-weight: 600;
    color: #f8fafc;
}

.toast-close-2 {
    position: absolute;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
    background: transparent;
    border: none;
    color: #94a3b8;
    cursor: pointer;
    font-size: 0.85rem;
    transition: color 0.2s;
}

.toast-close-2:hover {
    color: #f8fafc;
}

.toast-body-2 {
    font-size: 0.8rem;
    color: #cbd5e1;
    line-height: 1.4;
    margin-bottom: 12px;
    text-align: left;
}

.toast-footer-2 {
    display: flex;
    justify-content: flex-end;
}

.toast-btn-2 {
    background: linear-gradient(135deg, #6366f1 0%, #4f46e5 100%);
    color: #ffffff;
    border: none;
    padding: 6px 14px;
    border-radius: 6px;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
}

.toast-btn-2:hover {
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.4);
    transform: translateY(-1px);
}

.toast-trigger-2 {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: #cbd5e1;
    padding: 10px 20px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 0.85rem;
    font-weight: 600;
    transition: all 0.3s;
}

.toast-trigger-2:hover {
    background: rgba(255, 255, 255, 0.1);
    border-color: rgba(255, 255, 255, 0.2);
}

.toast-trigger-2.hidden {
    display: none;
}
```

### JavaScript
```javascript
function dismissToast2() {
    document.getElementById('toast-2').classList.add('dismissed');
    setTimeout(() => {
        document.getElementById('trigger-2').classList.remove('hidden');
    }, 400);
}

function showToast2() {
    document.getElementById('toast-2').classList.remove('dismissed');
    document.getElementById('trigger-2').classList.add('hidden');
}
```

### React
```tsx
import React, { useState } from 'react';

export function GlassmorphicToast() {
  const [visible, setVisible] = useState(true);

  return (
    <div style={{ position: 'relative', width: '100%', minHeight: '180px', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
      {visible ? (
        <div className="toast-card-2">
          <div className="toast-header-2">
            <span className="toast-icon-2">🚀</span>
            <span className="toast-title-2">New Feature Available</span>
            <button className="toast-close-2" onClick={() => setVisible(false)}>✕</button>
          </div>
          <div className="toast-body-2">
            We've integrated AI Code Generation in your development console. Start drafting now.
          </div>
          <div className="toast-footer-2">
            <button className="toast-btn-2">Explore</button>
          </div>
        </div>
      ) : (
        <button className="toast-trigger-2" onClick={() => setVisible(true)}>
          Trigger Toast
        </button>
      )}
    </div>
  );
}
```

---

## Effect #3: Cosmic Modal Alert
*Centered modal dialog with overlay, gradient glass backdrop, custom status illustration, and double action buttons.*

### HTML
```html
<div class="modal-box-3">
    <button class="open-btn-3" onclick="openModal3()">View Announcement</button>
    
    <div class="modal-overlay-3" id="modal-overlay-3" onclick="closeModal3(event)">
        <div class="modal-card-3" onclick="event.stopPropagation()">
            <div class="cosmic-header-3">
                <div class="orb-3"></div>
                <div class="cosmic-title-3">System Scheduled Maintenance</div>
            </div>
            <div class="cosmic-body-3">
                Our servers will undergo scheduled upgrades on <strong class="highlight-3">July 4th at 02:00 UTC</strong>. The library console will experience 15 minutes of intermittent downtime.
            </div>
            <div class="cosmic-footer-3">
                <button class="btn-sec-3" onclick="dismissModal3()">Dismiss</button>
                <button class="btn-pri-3" onclick="dismissModal3()">Acknowledge</button>
            </div>
        </div>
    </div>
</div>
```

### CSS
```css
.modal-box-3 {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.open-btn-3 {
    background: rgba(236, 72, 153, 0.15);
    border: 1px solid #ec4899;
    color: #f472b6;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.open-btn-3:hover {
    background: rgba(236, 72, 153, 0.25);
    box-shadow: 0 0 15px rgba(236, 72, 153, 0.3);
}

.modal-overlay-3 {
    position: absolute;
    inset: 0;
    background: rgba(10, 14, 23, 0.85);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s ease;
}

.modal-overlay-3.active {
    opacity: 1;
    pointer-events: auto;
}

.modal-card-3 {
    background: #121826;
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 16px;
    width: 90%;
    max-width: 380px;
    padding: 24px;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5), 0 0 25px rgba(236, 72, 153, 0.1);
    transform: scale(0.9);
    transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.modal-overlay-3.active .modal-card-3 {
    transform: scale(1);
}

.cosmic-header-3 {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
    margin-bottom: 16px;
}

.orb-3 {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background: radial-gradient(circle at 30% 30%, #f472b6, #ec4899);
    box-shadow: 0 0 20px rgba(236, 72, 153, 0.6);
    position: relative;
}

.orb-3::after {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    border: 1px solid rgba(236, 72, 153, 0.5);
    animation: orb-spin-3 4s linear infinite;
}

@keyframes orb-spin-3 {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

.cosmic-title-3 {
    font-size: 1rem;
    font-weight: 700;
    color: #f8fafc;
    text-align: center;
}

.cosmic-body-3 {
    font-size: 0.8rem;
    color: #cbd5e1;
    line-height: 1.5;
    text-align: center;
    margin-bottom: 20px;
}

.highlight-3 {
    color: #f472b6;
}

.cosmic-footer-3 {
    display: flex;
    gap: 12px;
}

.btn-sec-3, .btn-pri-3 {
    flex: 1;
    border: none;
    padding: 8px 16px;
    border-radius: 6px;
    font-size: 0.8rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
}

.btn-sec-3 {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.08);
    color: #cbd5e1;
}

.btn-sec-3:hover {
    background: rgba(255, 255, 255, 0.1);
    color: #f8fafc;
}

.btn-pri-3 {
    background: linear-gradient(135deg, #ec4899 0%, #db2777 100%);
    color: #ffffff;
}

.btn-pri-3:hover {
    box-shadow: 0 0 10px rgba(236, 72, 153, 0.4);
    transform: translateY(-1px);
}
```

### JavaScript
```javascript
function openModal3() {
    document.getElementById('modal-overlay-3').classList.add('active');
}

function closeModal3(event) {
    document.getElementById('modal-overlay-3').classList.remove('active');
}

function dismissModal3() {
    document.getElementById('modal-overlay-3').classList.remove('active');
}
```

### React
```tsx
import React, { useState } from 'react';

export function CosmicModal() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div>
      <button className="open-btn-3" onClick={() => setIsOpen(true)}>
        View Announcement
      </button>

      {isOpen && (
        <div className="modal-overlay-3 active" onClick={() => setIsOpen(false)}>
          <div className="modal-card-3" onClick={(e) => e.stopPropagation()}>
            <div className="cosmic-header-3">
              <div className="orb-3"></div>
              <div className="cosmic-title-3">System Scheduled Maintenance</div>
            </div>
            <div className="cosmic-body-3">
              Our servers will undergo scheduled upgrades on{' '}
              <strong className="highlight-3">July 4th at 02:00 UTC</strong>. The library
              console will experience 15 minutes of intermittent downtime.
            </div>
            <div className="cosmic-footer-3">
              <button className="btn-sec-3" onClick={() => setIsOpen(false)}>
                Dismiss
              </button>
              <button className="btn-pri-3" onClick={() => setIsOpen(false)}>
                Acknowledge
              </button>
            </div>
          </div>
        </div>
      )}
    </div>
  );
}
```

---

## Effect #4: Pulsing Feature Badge
*High-impact inline tag with nested keyframe glow circles indicating new version releases or live announcements.*

### HTML
```html
<div class="badge-wrapper-4">
    <div class="glow-ring-4">
        <div class="ring-4 ring-inner-4"></div>
        <div class="ring-4 ring-outer-4"></div>
        <span class="badge-core-4">NEW VERSION</span>
    </div>
</div>
```

### CSS
```css
.badge-wrapper-4 {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.glow-ring-4 {
    position: relative;
    display: inline-flex;
    align-items: center;
    justify-content: center;
}

.badge-core-4 {
    background: linear-gradient(135deg, #10b981 0%, #059669 100%);
    color: #ffffff;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 6px 14px;
    border-radius: 20px;
    letter-spacing: 0.5px;
    position: relative;
    z-index: 10;
    box-shadow: 0 4px 12px rgba(16, 185, 129, 0.4);
    border: 1px solid rgba(255, 255, 255, 0.15);
}

.ring-4 {
    position: absolute;
    border-radius: 50%;
    background: transparent;
    border: 2px solid #10b981;
    pointer-events: none;
    z-index: 1;
    width: 100%;
    height: 100%;
    opacity: 0;
}

.ring-inner-4 {
    animation: ring-pulse-4 2s cubic-bezier(0.25, 0, 0, 1) infinite;
}

.ring-outer-4 {
    animation: ring-pulse-4 2s cubic-bezier(0.25, 0, 0, 1) infinite;
    animation-delay: 0.6s;
}

@keyframes ring-pulse-4 {
    0% {
        transform: scale(0.95);
        opacity: 0.8;
    }
    100% {
        transform: scale(1.4, 1.8);
        opacity: 0;
    }
}
```

### React
```tsx
import React from 'react';

export function PulsingFeatureBadge() {
  return (
    <div className="badge-wrapper-4">
      <div className="glow-ring-4">
        <div className="ring-4 ring-inner-4"></div>
        <div className="ring-4 ring-outer-4"></div>
        <span className="badge-core-4">NEW VERSION</span>
      </div>
    </div>
  );
}
```

---

## Effect #5: Sliding News Ticker
*Horizontal continuous text ticker with side navigation triggers, allowing mouse hover pause control.*

### HTML
```html
<div class="ticker-box-5">
    <button class="ticker-nav-btn-5 btn-left-5" onclick="prevTickerItem5()">◀</button>
    <div class="ticker-content-5" id="ticker-content-5">
        <div class="ticker-scroll-5" id="ticker-scroll-5">
            <span class="ticker-item-5"><strong class="label-5 red-5">ALERT</strong> Server migration starting soon.</span>
            <span class="ticker-item-5"><strong class="label-5 blue-5">EVENT</strong> Join our Live Hackathon next Thursday!</span>
            <span class="ticker-item-5"><strong class="label-5 green-5">TIP</strong> Optimize assets directly from our CDN.</span>
        </div>
    </div>
    <button class="ticker-nav-btn-5 btn-right-5" onclick="nextTickerItem5()">▶</button>
</div>
```

### CSS
```css
.ticker-box-5 {
    width: 100%;
    max-width: 450px;
    background: #0f172a;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 10px;
    display: flex;
    align-items: center;
    padding: 8px 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
}

.ticker-nav-btn-5 {
    background: transparent;
    border: none;
    color: #94a3b8;
    cursor: pointer;
    font-size: 0.75rem;
    padding: 6px;
    transition: color 0.2s, transform 0.1s;
}

.ticker-nav-btn-5:hover {
    color: #f8fafc;
}

.ticker-nav-btn-5:active {
    transform: scale(0.9);
}

.ticker-content-5 {
    flex-grow: 1;
    overflow: hidden;
    height: 24px;
    position: relative;
}

.ticker-scroll-5 {
    display: flex;
    flex-direction: column;
    transition: transform 0.4s cubic-bezier(0.25, 1, 0.5, 1);
    height: 100%;
}

.ticker-item-5 {
    height: 24px;
    display: flex;
    align-items: center;
    font-size: 0.8rem;
    color: #cbd5e1;
    gap: 8px;
    white-space: nowrap;
    text-align: left;
}

.label-5 {
    font-size: 0.65rem;
    font-weight: 700;
    padding: 2px 6px;
    border-radius: 4px;
    letter-spacing: 0.5px;
}

.red-5 {
    background: rgba(239, 68, 68, 0.15);
    color: #f87171;
    border: 1px solid rgba(239, 68, 68, 0.3);
}

.blue-5 {
    background: rgba(59, 130, 246, 0.15);
    color: #60a5fa;
    border: 1px solid rgba(59, 130, 246, 0.3);
}

.green-5 {
    background: rgba(16, 185, 129, 0.15);
    color: #34d399;
    border: 1px solid rgba(16, 185, 129, 0.3);
}
```

### JavaScript
```javascript
let currentTickerIndex = 0;
const tickerScroll = document.getElementById('ticker-scroll-5');
const totalItems = 3;

function updateTickerPosition() {
    tickerScroll.style.transform = `translateY(-${currentTickerIndex * 24}px)`;
}

function nextTickerItem5() {
    currentTickerIndex = (currentTickerIndex + 1) % totalItems;
    updateTickerPosition();
}

function prevTickerItem5() {
    currentTickerIndex = (currentTickerIndex - 1 + totalItems) % totalItems;
    updateTickerPosition();
}
```

### React
```tsx
import React, { useState } from 'react';

export function SlidingNewsTicker() {
  const [index, setIndex] = useState(0);
  const items = [
    { type: 'ALERT', text: 'Server migration starting soon.', theme: 'red-5' },
    { type: 'EVENT', text: 'Join our Live Hackathon next Thursday!', theme: 'blue-5' },
    { type: 'TIP', text: 'Optimize assets directly from our CDN.', theme: 'green-5' }
  ];

  const handleNext = () => setIndex((prev) => (prev + 1) % items.length);
  const handlePrev = () => setIndex((prev) => (prev - 1 + items.length) % items.length);

  return (
    <div className="ticker-box-5">
      <button className="ticker-nav-btn-5" onClick={handlePrev}>◀</button>
      <div className="ticker-content-5">
        <div className="ticker-scroll-5" style={{ transform: `translateY(-${index * 24}px)` }}>
          {items.map((item, i) => (
            <div key={i} className="ticker-item-5">
              <span className={`label-5 ${item.theme}`}>{item.type}</span>
              <span>{item.text}</span>
            </div>
          ))}
        </div>
      </div>
      <button className="ticker-nav-btn-5" onClick={handleNext}>▶</button>
    </div>
  );
}
```

---

## Effect #6: Expandable Info Drawer
*Compact visual banner that expands on hover or click to display secondary rich text panels.*

### HTML
```html
<div class="expandable-drawer-6" id="drawer-6" onclick="toggleDrawer6()">
    <div class="drawer-summary-6">
        <div class="drawer-indicator-6">💡</div>
        <span class="drawer-title-6">New UI Design Tokens Released</span>
        <span class="drawer-chevron-6" id="chevron-6">▼</span>
    </div>
    <div class="drawer-details-6" id="details-6">
        <p>We've added 32 brand new gradient options, glassmorphic layout tokens, and updated CSS variables. Read the documentation to start importing them into your modules.</p>
        <button class="drawer-action-6" onclick="event.stopPropagation()">View Tokens</button>
    </div>
</div>
```

### CSS
```css
.expandable-drawer-6 {
    width: 100%;
    max-width: 420px;
    background: #182032;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.25);
    transition: border-color 0.3s, box-shadow 0.3s;
}

.expandable-drawer-6:hover {
    border-color: rgba(99, 102, 241, 0.4);
    box-shadow: 0 6px 20px rgba(99, 102, 241, 0.1);
}

.drawer-summary-6 {
    padding: 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
}

.drawer-indicator-6 {
    font-size: 1.1rem;
}

.drawer-title-6 {
    font-size: 0.85rem;
    font-weight: 600;
    color: #f8fafc;
    flex-grow: 1;
    text-align: left;
}

.drawer-chevron-6 {
    font-size: 0.7rem;
    color: #94a3b8;
    transition: transform 0.3s ease;
}

.expandable-drawer-6.open .drawer-chevron-6 {
    transform: rotate(180deg);
}

.drawer-details-6 {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s cubic-bezier(0.4, 0, 0.2, 1), padding 0.3s;
    padding: 0 16px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}

.expandable-drawer-6.open .drawer-details-6 {
    max-height: 150px;
    padding: 0 16px 16px 16px;
}

.drawer-details-6 p {
    font-size: 0.8rem;
    color: #cbd5e1;
    line-height: 1.45;
    margin: 0 0 12px 0;
    text-align: left;
}

.drawer-action-6 {
    background: transparent;
    border: 1px solid rgba(99, 102, 241, 0.5);
    color: #a5b4fc;
    padding: 6px 14px;
    border-radius: 6px;
    font-size: 0.75rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
}

.drawer-action-6:hover {
    background: rgba(99, 102, 241, 0.15);
    border-color: #6366f1;
}
```

### JavaScript
```javascript
function toggleDrawer6() {
    const drawer = document.getElementById('drawer-6');
    drawer.classList.toggle('open');
}
```

### React
```tsx
import React, { useState } from 'react';

export function ExpandableInfoDrawer() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div className={`expandable-drawer-6 ${isOpen ? 'open' : ''}`} onClick={() => setIsOpen(!isOpen)}>
      <div className="drawer-summary-6">
        <span className="drawer-indicator-6">💡</span>
        <span className="drawer-title-6">New UI Design Tokens Released</span>
        <span className="drawer-chevron-6">▼</span>
      </div>
      <div className="drawer-details-6">
        <p>
          We've added 32 brand new gradient options, glassmorphic layout tokens, and updated CSS variables. Read the documentation to start importing them into your modules.
        </p>
        <button className="drawer-action-6" onClick={(e) => e.stopPropagation()}>
          View Tokens
        </button>
      </div>
    </div>
  );
}
```

---

## Effect #7: Premium Launch Countdown
*Dynamic timer widget displaying countdown slots alongside premium action items for launch dates.*

### HTML
```html
<div class="countdown-card-7">
    <div class="countdown-tag-7">UPCOMING RELEASE</div>
    <div class="countdown-title-7">Component Engine v3.0</div>
    <div class="countdown-grid-7">
        <div class="slot-7">
            <span class="num-7" id="cd-days-7">05</span>
            <span class="label-7">DAYS</span>
        </div>
        <div class="slot-7">
            <span class="num-7" id="cd-hours-7">00</span>
            <span class="label-7">HRS</span>
        </div>
        <div class="slot-7">
            <span class="num-7" id="cd-mins-7">00</span>
            <span class="label-7">MINS</span>
        </div>
        <div class="slot-7">
            <span class="num-7" id="cd-secs-7">00</span>
            <span class="label-7">SECS</span>
        </div>
    </div>
    <button class="countdown-btn-7">Join Waitlist</button>
</div>
```

### CSS
```css
.countdown-card-7 {
    width: 100%;
    max-width: 380px;
    background: linear-gradient(135deg, #121826 0%, #0d121f 100%);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 16px;
    padding: 20px;
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
    text-align: center;
    position: relative;
    overflow: hidden;
}

.countdown-card-7::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 4px;
    background: linear-gradient(90deg, #6366f1, #3b82f6);
}

.countdown-tag-7 {
    display: inline-block;
    background: rgba(99, 102, 241, 0.12);
    border: 1px solid rgba(99, 102, 241, 0.25);
    color: #a5b4fc;
    font-size: 0.65rem;
    font-weight: 700;
    padding: 4px 10px;
    border-radius: 4px;
    letter-spacing: 1px;
    margin-bottom: 12px;
}

.countdown-title-7 {
    font-size: 1.1rem;
    font-weight: 700;
    color: #f8fafc;
    margin-bottom: 20px;
}

.countdown-grid-7 {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 8px;
    margin-bottom: 20px;
}

.slot-7 {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 8px;
    padding: 8px 4px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.num-7 {
    font-family: monospace;
    font-size: 1.25rem;
    font-weight: 700;
    color: #ffffff;
}

.label-7 {
    font-size: 0.55rem;
    color: #94a3b8;
    margin-top: 4px;
    letter-spacing: 0.5px;
}

.countdown-btn-7 {
    width: 100%;
    background: #ffffff;
    color: #0f172a;
    border: none;
    padding: 10px;
    border-radius: 8px;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.countdown-btn-7:hover {
    background: #6366f1;
    color: #ffffff;
    box-shadow: 0 5px 15px rgba(99, 102, 241, 0.4);
}
```

### JavaScript
```javascript
// Simple Countdown initializer
(function startCountdown() {
    const targetDate = new Date();
    targetDate.setDate(targetDate.getDate() + 5);
    
    function update() {
        const now = new Date();
        const diff = targetDate - now;
        
        if (diff <= 0) return;
        
        const days = Math.floor(diff / (1000 * 60 * 60 * 24));
        const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
        const mins = Math.floor((diff / 1000 / 60) % 60);
        const secs = Math.floor((diff / 1000) % 60);
        
        const dEl = document.getElementById('cd-days-7');
        const hEl = document.getElementById('cd-hours-7');
        const mEl = document.getElementById('cd-mins-7');
        const sEl = document.getElementById('cd-secs-7');
        
        if (dEl) dEl.innerText = days.toString().padStart(2, '0');
        if (hEl) hEl.innerText = hours.toString().padStart(2, '0');
        if (mEl) mEl.innerText = mins.toString().padStart(2, '0');
        if (sEl) sEl.innerText = secs.toString().padStart(2, '0');
    }
    
    setInterval(update, 1000);
    update();
})();
```

### React
```tsx
import React, { useState, useEffect } from 'react';

export function ReleaseCountdown() {
  const [timeLeft, setTimeLeft] = useState({ days: 5, hours: 0, minutes: 0, seconds: 0 });

  useEffect(() => {
    const targetDate = new Date();
    targetDate.setDate(targetDate.getDate() + 5);

    const interval = setInterval(() => {
      const now = new Date();
      const diff = targetDate.getTime() - now.getTime();

      if (diff <= 0) {
        clearInterval(interval);
      } else {
        const days = Math.floor(diff / (1000 * 60 * 60 * 24));
        const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
        const minutes = Math.floor((diff / 1000 / 60) % 60);
        const seconds = Math.floor((diff / 1000) % 60);
        setTimeLeft({ days, hours, minutes, seconds });
      }
    }, 1000);

    return () => clearInterval(interval);
  }, []);

  const format = (num: number) => num.toString().padStart(2, '0');

  return (
    <div className="countdown-card-7">
      <div className="countdown-tag-7">UPCOMING RELEASE</div>
      <div className="countdown-title-7">Component Engine v3.0</div>
      <div className="countdown-grid-7">
        <div className="slot-7">
          <span className="num-7">{format(timeLeft.days)}</span>
          <span className="label-7">DAYS</span>
        </div>
        <div className="slot-7">
          <span className="num-7">{format(timeLeft.hours)}</span>
          <span className="label-7">HRS</span>
        </div>
        <div className="slot-7">
          <span className="num-7">{format(timeLeft.minutes)}</span>
          <span className="label-7">MINS</span>
        </div>
        <div className="slot-7">
          <span className="num-7">{format(timeLeft.seconds)}</span>
          <span className="label-7">SECS</span>
        </div>
      </div>
      <button className="countdown-btn-7">Join Waitlist</button>
    </div>
  );
}
```

---

## Effect #8: Aggregated Feed Card
*Mini system dashboard aggregating historical announcement lists with read-status selectors.*

### HTML
```html
<div class="feed-card-8">
    <div class="feed-header-8">
        <span class="feed-title-8">Updates & Alerts</span>
        <span class="feed-count-8" id="unread-count-8">3 Unread</span>
    </div>
    <div class="feed-list-8">
        <div class="feed-item-8" onclick="toggleFeedItem8(this)">
            <span class="feed-dot-8"></span>
            <div class="feed-info-8">
                <span class="feed-item-title-8">API Deprecation Reminder</span>
                <span class="feed-item-desc-8">v1 API endpoints will be removed on Dec 31. Please upgrade.</span>
            </div>
        </div>
        <div class="feed-item-8" onclick="toggleFeedItem8(this)">
            <span class="feed-dot-8"></span>
            <div class="feed-info-8">
                <span class="feed-item-title-8">Weekly Dev Sync</span>
                <span class="feed-item-desc-8">Our online sync is tomorrow. Check the Slack channel for invite links.</span>
            </div>
        </div>
        <div class="feed-item-8" onclick="toggleFeedItem8(this)">
            <span class="feed-dot-8"></span>
            <div class="feed-info-8">
                <span class="feed-item-title-8">Performance Boost</span>
                <span class="feed-item-desc-8">Bundle sizes reduced by 18% with new dynamic treeshaking algorithm.</span>
            </div>
        </div>
    </div>
</div>
```

### CSS
```css
.feed-card-8 {
    width: 100%;
    max-width: 420px;
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    padding: 16px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.35);
}

.feed-header-8 {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid rgba(255, 255, 255, 0.06);
    padding-bottom: 12px;
    margin-bottom: 12px;
}

.feed-title-8 {
    font-size: 0.9rem;
    font-weight: 600;
    color: #f8fafc;
}

.feed-count-8 {
    background: rgba(99, 102, 241, 0.15);
    color: #a5b4fc;
    font-size: 0.7rem;
    font-weight: 700;
    padding: 2px 8px;
    border-radius: 20px;
}

.feed-list-8 {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.feed-item-8 {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 8px;
    border-radius: 8px;
    cursor: pointer;
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid transparent;
    transition: all 0.2s;
}

.feed-item-8:hover {
    background: rgba(255, 255, 255, 0.05);
    border-color: rgba(255, 255, 255, 0.05);
}

.feed-item-8.read {
    opacity: 0.55;
}

.feed-dot-8 {
    width: 6px;
    height: 6px;
    background-color: #6366f1;
    border-radius: 50%;
    margin-top: 5px;
    flex-shrink: 0;
    transition: background-color 0.2s;
}

.feed-item-8.read .feed-dot-8 {
    background-color: transparent;
    border: 1px solid #94a3b8;
}

.feed-info-8 {
    display: flex;
    flex-direction: column;
    gap: 2px;
    text-align: left;
}

.feed-item-title-8 {
    font-size: 0.8rem;
    font-weight: 600;
    color: #f8fafc;
}

.feed-item-desc-8 {
    font-size: 0.7rem;
    color: #94a3b8;
    line-height: 1.3;
}
```

### JavaScript
```javascript
function toggleFeedItem8(element) {
    element.classList.toggle('read');
    const totalItems = element.parentNode.querySelectorAll('.feed-item-8').length;
    const readItems = element.parentNode.querySelectorAll('.feed-item-8.read').length;
    const unreadCount = totalItems - readItems;
    element.parentNode.parentNode.querySelector('.feed-count-8').innerText = `${unreadCount} Unread`;
}
```

### React
```tsx
import React, { useState } from 'react';

export function AggregatedFeedCard() {
  const [items, setItems] = useState([
    {
      id: 1,
      title: 'API Deprecation Reminder',
      desc: 'v1 API endpoints will be removed on Dec 31. Please upgrade.',
      read: false,
    },
    {
      id: 2,
      title: 'Weekly Dev Sync',
      desc: 'Our online sync is tomorrow. Check the Slack channel for invite links.',
      read: false,
    },
    {
      id: 3,
      title: 'Performance Boost',
      desc: 'Bundle sizes reduced by 18% with new dynamic treeshaking algorithm.',
      read: false,
    },
  ]);

  const toggleRead = (id: number) => {
    setItems(items.map(item => (item.id === id ? { ...item, read: !item.read } : item)));
  };

  const unreadCount = items.filter(item => !item.read).length;

  return (
    <div className="feed-card-8">
      <div className="feed-header-8">
        <span className="feed-title-8">Updates & Alerts</span>
        <span className="feed-count-8">{unreadCount} Unread</span>
      </div>
      <div className="feed-list-8">
        {items.map(item => (
          <div
            key={item.id}
            className={`feed-item-8 ${item.read ? 'read' : ''}`}
            onClick={() => toggleRead(item.id)}
          >
            <span className="feed-dot-8"></span>
            <div className="feed-info-8">
              <span className="feed-item-title-8">{item.title}</span>
              <span className="feed-item-desc-8">{item.desc}</span>
            </div>
          </div>
        ))}
      </div>
    </div>
  );
}
```
