# Premium Custom Testimonial Code Database

This file contains the complete, self-contained HTML, CSS and React code snippets for all Premium Testimonials featured in the interactive showcase.

---

## Testimonial #1: Bento Grid Testimonials

### HTML
```html
<div class="testimonial-preview-wrapper">
<div class="bento-testimonials">
  <div class="bento-card card-large">
    <div class="rating">★★★★★</div>
    <p class="quote">"This component library completely transformed our workflow. Our development velocity increased by 300%."</p>
    <div class="user">
      <img src="https://polo-pecan-73837341.figma.site/_assets/v11/ca8093996e970200cbcf8bde8744175e52da5a79.png" alt="User">
      <div>
        <h4>Alex Rivera</h4>
        <span>CTO, TechFlow</span>
      </div>
    </div>
  </div>
  <div class="bento-card">
    <p class="quote">"Extremely clean code and outstanding design aesthetics."</p>
    <div class="user">
      <div class="avatar-placeholder">SK</div>
      <div>
        <h4>Sarah K.</h4>
        <span>Lead Designer</span>
      </div>
    </div>
  </div>
  <div class="bento-card">
    <p class="quote">"Highly recommended for modern SaaS products."</p>
    <div class="user">
      <div class="avatar-placeholder">MD</div>
      <div>
        <h4>Marcus D.</h4>
        <span>Product Owner</span>
      </div>
    </div>
  </div>
</div>
</div>
```

### CSS
```css
#card-1 .testimonial-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #090e17;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-1 .bento-testimonials {
  transform: scale(0.68);
  transform-origin: center center;
  width: 850px;
  display: grid;
  grid-template-columns: 2fr 1.2fr;
  grid-template-rows: auto auto;
  gap: 16px;
  font-family: 'Inter', sans-serif;
  color: #fff;
  box-sizing: border-box;
}
#card-1 .bento-card {
  background: #121826;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 16px;
  padding: 24px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 16px;
  transition: all 0.3s ease;
}
#card-1 .bento-card:hover {
  border-color: rgba(255, 255, 255, 0.16);
  transform: translateY(-2px);
}
#card-1 .card-large {
  grid-row: span 2;
}
#card-1 .rating {
  color: #fbbf24;
  font-size: 16px;
}
#card-1 .quote {
  font-size: 16px;
  line-height: 1.5;
  color: rgba(255, 255, 255, 0.9);
  font-weight: 400;
}
#card-1 .user {
  display: flex;
  align-items: center;
  gap: 12px;
}
#card-1 .user img {
  width: 40px;
  height: 40px;
  rounded-full: 9999px;
  border-radius: 50%;
  object-cover: cover;
}
#card-1 .user h4 {
  font-size: 14px;
  font-weight: 600;
  margin: 0;
}
#card-1 .user span {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.5);
}
#card-1 .avatar-placeholder {
  width: 40px;
  height: 40px;
  background: rgba(99, 102, 241, 0.15);
  color: #a5b4fc;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  font-weight: 600;
}
```

### React
```tsx
import React from 'react';

export default function BentoTestimonials() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-[2fr_1.2fr] gap-4 p-6 bg-[#090e17] rounded-2xl text-white">
      <div className="bg-[#121826] border border-white/10 rounded-2xl p-6 flex flex-col justify-between gap-4">
        <span className="text-[#fbbf24]">★★★★★</span>
        <p className="text-lg">"This component library completely transformed our workflow. Our velocity increased by 300%."</p>
        <div className="flex items-center gap-3">
          <img src="/avatar.png" className="w-10 h-10 rounded-full" alt="Alex" />
          <div>
            <h4 className="font-semibold text-sm">Alex Rivera</h4>
            <span className="text-xs text-white/50">CTO, TechFlow</span>
          </div>
        </div>
      </div>
      {/* Additional small cards */}
    </div>
  );
}
```

---

## Testimonial #2: Interactive Slider Testimonial

### HTML
```html
<div class="testimonial-preview-wrapper">
<div class="slider-testimonial-card">
  <button class="arrow-btn left" onclick="(function(el){
    const container = el.closest('.slider-testimonial-card');
    const slides = container.querySelectorAll('.testimonial-slide');
    let idx = parseInt(container.getAttribute('data-index') || '0');
    slides[idx].classList.remove('active');
    idx = (idx - 1 + slides.length) % slides.length;
    slides[idx].classList.add('active');
    container.setAttribute('data-index', idx);
  })(this)">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="19" y1="12" x2="5" y2="12"></line><polyline points="12 19 5 12 12 5"></polyline></svg>
  </button>
  
  <div class="slides-container">
    <!-- Slide 1 -->
    <div class="testimonial-slide active">
      <div class="quote-icon">“</div>
      <p class="quote-text">The level of craftsmanship in this product is rare. Every single micro-interaction is perfectly polished.</p>
      <h4 class="author">- Helena Martinez, Design Lead at Vibe</h4>
    </div>
    <!-- Slide 2 -->
    <div class="testimonial-slide">
      <div class="quote-icon">“</div>
      <p class="quote-text">An absolute game-changer. Saving hours of development time daily, and our users love the visuals.</p>
      <h4 class="author">- Liam O'Connor, Senior Engineer</h4>
    </div>
  </div>

  <button class="arrow-btn right" onclick="(function(el){
    const container = el.closest('.slider-testimonial-card');
    const slides = container.querySelectorAll('.testimonial-slide');
    let idx = parseInt(container.getAttribute('data-index') || '0');
    slides[idx].classList.remove('active');
    idx = (idx + 1) % slides.length;
    slides[idx].classList.add('active');
    container.setAttribute('data-index', idx);
  })(this)">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
  </button>
</div>
</div>
```

### CSS
```css
#card-2 .testimonial-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #0c111d;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-2 .slider-testimonial-card {
  transform: scale(0.8);
  transform-origin: center center;
  width: 480px;
  background: #182235;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 20px;
  padding: 32px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  font-family: 'Outfit', sans-serif;
  color: #fff;
  box-shadow: 0 10px 30px rgba(0,0,0,0.25);
  box-sizing: border-box;
}
#card-2 .slides-container {
  flex-1: 1;
  position: relative;
  height: 160px;
  display: flex;
  align-items: center;
}
#card-2 .testimonial-slide {
  display: none;
  flex-direction: column;
  gap: 12px;
  animation: fadeIn 0.4s ease-out;
}
#card-2 .testimonial-slide.active {
  display: flex;
}
#card-2 .quote-icon {
  font-size: 48px;
  font-family: serif;
  color: #6366f1;
  line-height: 1;
  height: 24px;
}
#card-2 .quote-text {
  font-size: 16px;
  line-height: 1.5;
  color: rgba(255, 255, 255, 0.85);
  margin: 0;
}
#card-2 .author {
  font-size: 13px;
  color: #a5b4fc;
  font-weight: 500;
  margin: 0;
}
#card-2 .arrow-btn {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  color: #fff;
  width: 38px;
  height: 38px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s;
  shrink: 0;
}
#card-2 .arrow-btn:hover {
  background: #6366f1;
  border-color: #6366f1;
}
@keyframes fadeIn {
  from { opacity: 0; transform: scale(0.98); }
  to { opacity: 1; transform: scale(1); }
}
```

### React
```tsx
import React, { useState } from 'react';
import { ChevronLeft, ChevronRight } from 'lucide-react';

export default function TestimonialSlider() {
  const [active, setActive] = useState(0);
  const quotes = [
    { text: "The level of craftsmanship in this product is rare. Every single micro-interaction is perfectly polished.", author: "Helena Martinez" },
    { text: "An absolute game-changer. Saving hours of development time daily.", author: "Liam O'Connor" }
  ];

  return (
    <div className="flex items-center gap-4 bg-slate-900 border border-white/10 p-8 rounded-2xl max-w-md text-white">
      <button onClick={() => setActive(prev => (prev - 1 + quotes.length) % quotes.length)}>
        <ChevronLeft />
      </button>
      <div className="flex-1 min-h-[120px]">
        <p className="text-lg">"{quotes[active].text}"</p>
        <span className="text-indigo-400 text-sm">{quotes[active].author}</span>
      </div>
      <button onClick={() => setActive(prev => (prev + 1) % quotes.length)}>
        <ChevronRight />
      </button>
    </div>
  );
}
```

---

## Testimonial #3: Glowing Card Testimonial

### HTML
```html
<div class="testimonial-preview-wrapper">
<div class="glow-testimonial-card" style="--mouse-x: 50%; --mouse-y: 50%;" onmousemove="(function(e, el){
  const rect = el.getBoundingClientRect();
  const x = e.clientX - rect.left;
  const y = e.clientY - rect.top;
  el.style.setProperty('--mouse-x', x + 'px');
  el.style.setProperty('--mouse-y', y + 'px');
})(event, this)">
  <div class="card-glow-bg"></div>
  <div class="card-content">
    <div class="user-badge">
      <img src="https://polo-pecan-73837341.figma.site/_assets/v11/ca8093996e970200cbcf8bde8744175e52da5a79.png" alt="Avatar">
      <div>
        <h4>Sophia Laurent</h4>
        <span>Director of Creative, Neon Studio</span>
      </div>
    </div>
    <p class="quote">"Stunning interactive glow effects, clean code, and premium UI assets. The best design system workspace I have used."</p>
  </div>
</div>
</div>
```

### CSS
```css
#card-3 .testimonial-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #07090e;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-3 .glow-testimonial-card {
  transform: scale(0.8);
  transform-origin: center center;
  width: 440px;
  background: rgba(24, 32, 50, 0.45);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 20px;
  padding: 30px;
  position: relative;
  overflow: hidden;
  font-family: 'Inter', sans-serif;
  color: #fff;
  box-sizing: border-box;
}
#card-3 .card-glow-bg {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(
    400px circle at var(--mouse-x) var(--mouse-y),
    rgba(99, 102, 241, 0.15),
    transparent 80%
  );
  z-index: 1;
  pointer-events: none;
}
#card-3 .card-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
#card-3 .user-badge {
  display: flex;
  align-items: center;
  gap: 12px;
}
#card-3 .user-badge img {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0.15);
}
#card-3 .user-badge h4 {
  font-size: 14px;
  font-weight: 600;
  margin: 0;
}
#card-3 .user-badge span {
  font-size: 11px;
  color: rgba(255, 255, 255, 0.5);
}
#card-3 .quote {
  font-size: 15px;
  line-height: 1.5;
  color: rgba(255,255,255,0.85);
  font-style: italic;
}
```

### React
```tsx
import React, { useRef } from 'react';

export default function GlowTestimonial() {
  const cardRef = useRef(null);

  const handleMouseMove = (e) => {
    const card = cardRef.current;
    if (!card) return;
    const rect = card.getBoundingClientRect();
    card.style.setProperty('--mouse-x', `${e.clientX - rect.left}px`);
    card.style.setProperty('--mouse-y', `${e.clientY - rect.top}px`);
  };

  return (
    <div
      ref={cardRef}
      onMouseMove={handleMouseMove}
      className="relative w-full max-w-sm bg-slate-900 border border-white/10 p-6 rounded-2xl overflow-hidden text-white"
    >
      <div className="absolute inset-0 bg-[radial-gradient(400px_circle_at_var(--mouse-x)_var(--mouse-y),rgba(99,102,241,0.15),transparent_80%)] pointer-events-none" />
      <div className="relative z-10 flex flex-col gap-4">
        {/* Profile and quote */}
      </div>
    </div>
  );
}
```

---

---

## Testimonial #4: Circular Testimonials

### HTML
```html
<div class="testimonial-preview-wrapper select-none">
<div class="circular-testimonial-card" id="circular-stage-4">
  <div class="circular-testimonial-grid">
    <div class="circular-image-container" id="circular-images-4">
    </div>
    <div class="circular-content-container">
      <div class="circular-text-panel" id="circular-text-panel-4">
      </div>
      <div class="circular-nav-buttons">
        <button class="circ-nav-btn prev-btn" id="circ-prev-4" aria-label="Previous">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="19" y1="12" x2="5" y2="12"></line><polyline points="12 19 5 12 12 5"></polyline></svg>
        </button>
        <button class="circ-nav-btn next-btn" id="circ-next-4" aria-label="Next">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
        </button>
      </div>
    </div>
  </div>
</div>

<svg width="0" height="0" style="position:absolute;" onload="(function(el){
  setTimeout(function(){
    const container = el.closest('.testimonial-preview-wrapper');
    if (!container) return;
    const imageContainer = container.querySelector('#circular-images-4');
    const textPanel = container.querySelector('#circular-text-panel-4');
    if (!imageContainer || !textPanel) return;
    
    const testimonials = [
      {
        name: "Alex Rivera",
        designation: "CTO, TechFlow",
        quote: "This component library completely transformed our workflow. Our development velocity increased by 300%.",
        src: "https://polo-pecan-73837341.figma.site/_assets/v11/ca8093996e970200cbcf8bde8744175e52da5a79.png"
      },
      {
        name: "Sarah K.",
        designation: "Lead Designer",
        quote: "Extremely clean code and outstanding design aesthetics. The customizability is truly top tier.",
        src: "https://polo-pecan-73837341.figma.site/_assets/v11/d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/avatar_2.png"
      },
      {
        name: "Michael Chen",
        designation: "Software Architect",
        quote: "Framer Motion integration is stellar. Performance is smooth even on mobile devices.",
        src: "https://polo-pecan-73837341.figma.site/_assets/v11/d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/avatar_3.png"
      }
    ];
    let activeIndex = 0;
    let isActive = true;
    
    function updateUI() {
      if (!isActive) return;
      imageContainer.innerHTML = '';
      testimonials.forEach((t, i) => {
        const img = document.createElement('img');
        img.src = t.src;
        img.className = 'circular-img';
        
        const len = testimonials.length;
        const offset = (i - activeIndex + len) % len;
        const active = i === activeIndex;
        const isLeft = (activeIndex - 1 + len) % len === i;
        const isRight = (activeIndex + 1) % len === i;
        
        if (active) {
          img.style.zIndex = '3';
          img.style.opacity = '1';
          img.style.transform = 'translateX(0px) translateY(0px) scale(1.1) rotateY(0deg)';
        } else if (isLeft) {
          img.style.zIndex = '2';
          img.style.opacity = '0.6';
          img.style.transform = 'translateX(-40px) translateY(-8px) scale(0.85) rotateY(25deg)';
        } else if (isRight) {
          img.style.zIndex = '2';
          img.style.opacity = '0.6';
          img.style.transform = 'translateX(40px) translateY(-8px) scale(0.85) rotateY(-25deg)';
        } else {
          img.style.zIndex = '1';
          img.style.opacity = '0';
          img.style.transform = 'scale(0.5)';
        }
        img.style.transition = 'all 0.6s cubic-bezier(0.4, 1.4, 0.3, 1)';
        imageContainer.appendChild(img);
      });
      
      const active = testimonials[activeIndex];
      textPanel.innerHTML = '';
      
      const name = document.createElement('h3');
      name.className = 'circ-name';
      name.textContent = active.name;
      textPanel.appendChild(name);
      
      const title = document.createElement('p');
      title.className = 'circ-title';
      title.textContent = active.designation;
      textPanel.appendChild(title);
      
      const quote = document.createElement('p');
      quote.className = 'circ-quote';
      textPanel.appendChild(quote);
      
      const words = active.quote.split(' ');
      words.forEach((word, idx) => {
        const span = document.createElement('span');
        span.textContent = word + ' ';
        span.style.animationDelay = (idx * 25) + 'ms';
        quote.appendChild(span);
      });
    }
    
    updateUI();
    
    container.querySelector('#circ-prev-4').onclick = () => {
      activeIndex = (activeIndex - 1 + testimonials.length) % testimonials.length;
      updateUI();
    };
    container.querySelector('#circ-next-4').onclick = () => {
      activeIndex = (activeIndex + 1) % testimonials.length;
      updateUI();
    };
    
    container._btn4Cleanup = () => {
      isActive = false;
    };
  }, 500);
})(this)"></svg>
</div>
```

### CSS
```css
#card-4 .testimonial-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #090e17;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-4 .circular-testimonial-card {
  width: 100%;
  max-width: 620px;
  padding: 14px 18px;
  background: #111827;
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.08);
}
#card-4 .circular-testimonial-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
  align-items: center;
}
@media (min-width: 640px) {
  #card-4 .circular-testimonial-grid {
    grid-template-columns: 1fr 1.6fr;
  }
}
#card-4 .circular-image-container {
  position: relative;
  width: 100%;
  height: 120px;
  perspective: 1000px;
}
#card-4 .circular-img {
  position: absolute;
  width: 70px;
  height: 95px;
  top: 10px;
  left: 50%;
  margin-left: -35px;
  object-fit: cover;
  border-radius: 10px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.4);
  transform-style: preserve-3d;
  will-change: transform, opacity;
}
#card-4 .circular-content-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
#card-4 .circ-name {
  font-size: 15px;
  font-weight: 700;
  color: #fff;
  margin-bottom: 2px;
}
#card-4 .circ-title {
  font-size: 11px;
  color: #9ca3af;
  margin-bottom: 8px;
}
#card-4 .circ-quote {
  font-size: 12px;
  line-height: 1.5;
  color: #d1d5db;
  min-height: 50px;
}
#card-4 .circ-quote span {
  display: inline-block;
  opacity: 0;
  filter: blur(8px);
  transform: translateY(6px);
  animation: circWordReveal 0.4s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
}
@keyframes circWordReveal {
  to {
    opacity: 1;
    filter: blur(0);
    transform: translateY(0);
  }
}
#card-4 .circular-nav-buttons {
  display: flex;
  gap: 8px;
  margin-top: 10px;
}
#card-4 .circ-nav-btn {
  width: 28px;
  height: 28px;
  border-radius: 50%;
  background: #1f2937;
  border: 1px solid rgba(255, 255, 255, 0.1);
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background 0.3s, border-color 0.3s;
}
#card-4 .circ-nav-btn:hover {
  background: #6366f1;
  border-color: #6366f1;
}
```

### React
```tsx
\
```

---

## Testimonial #5: PageFlip Testimonial

### HTML
```html
<div class="testimonial-preview-wrapper select-none">
<div class="flipbook-container" id="flipbook-5">
  <div class="book" id="book-element-5">
    <!-- Cover -->
    <div class="page cover" id="page-cover-5">
      <div class="cover-content">
        <div class="logo-wrapper">
          <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path></svg>
        </div>
        <h2>Serenity UI</h2>
        <div class="line"></div>
        <p>Read what virtual people are saying about us</p>
        <span class="tap-hint">Click Cover to Open</span>
      </div>
    </div>
    
    <!-- Index / Left Page -->
    <div class="page inside left" id="page-index-5">
      <div class="page-content">
        <h3 class="page-heading">Virtual Voices</h3>
        <ul class="index-list">
          <li class="index-item active" data-idx="0">
            <img src="https://polo-pecan-73837341.figma.site/_assets/v11/ca8093996e970200cbcf8bde8744175e52da5a79.png" alt="Avatar">
            <span>Alex Rivera</span>
          </li>
          <li class="index-item" data-idx="1">
            <img src="https://polo-pecan-73837341.figma.site/_assets/v11/d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/avatar_2.png" alt="Avatar">
            <span>Sarah K.</span>
          </li>
          <li class="index-item" data-idx="2">
            <img src="https://polo-pecan-73837341.figma.site/_assets/v11/d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/avatar_3.png" alt="Avatar">
            <span>Michael Chen</span>
          </li>
        </ul>
        <button class="close-book-btn">Close Book</button>
      </div>
    </div>
    
    <!-- Right Page (Details) -->
    <div class="page inside right" id="page-details-5">
      <div class="page-content" id="details-target-5">
      </div>
    </div>
  </div>
</div>

<svg width="0" height="0" style="position:absolute;" onload="(function(el){
  setTimeout(function(){
    const container = el.closest('.testimonial-preview-wrapper');
    if (!container) return;
    const cover = container.querySelector('#page-cover-5');
    const book = container.querySelector('#book-element-5');
    const detailsTarget = container.querySelector('#details-target-5');
    const indexItems = container.querySelectorAll('.index-item');
    const closeBtn = container.querySelector('.close-book-btn');
    
    const testimonials = [
      {
        name: "Alex Rivera",
        jobtitle: "CTO, TechFlow",
        text: "This component library completely transformed our workflow. Our development velocity increased by 300%.",
        rating: 5,
        image: "https://polo-pecan-73837341.figma.site/_assets/v11/ca8093996e970200cbcf8bde8744175e52da5a79.png"
      },
      {
        name: "Sarah K.",
        jobtitle: "Lead Designer",
        text: "Extremely clean code and outstanding design aesthetics. The customizability is truly top tier.",
        rating: 5,
        image: "https://polo-pecan-73837341.figma.site/_assets/v11/d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/avatar_2.png"
      },
      {
        name: "Michael Chen",
        jobtitle: "Software Architect",
        text: "Framer Motion integration is stellar. Performance is smooth even on mobile devices.",
        rating: 4,
        image: "https://polo-pecan-73837341.figma.site/_assets/v11/d8j0ntlcm91z4.cloudfront.net/user_38xzZboKViGWJOttwIXH07lWA1P/avatar_3.png"
      }
    ];
    
    function showTestimonial(idx) {
      const t = testimonials[idx];
      let stars = '';
      for (let i = 0; i < 5; i++) {
        stars += `<span class="star ${i < t.rating ? 'fill' : ''}">★</span>`;
      }
      
      detailsTarget.style.opacity = '0';
      detailsTarget.style.transform = 'translateY(10px)';
      
      setTimeout(() => {
        detailsTarget.innerHTML = `
          <div class="details-avatar">
            <img src="${t.image}" alt="${t.name}">
          </div>
          <h4 class="details-name">${t.name}</h4>
          <span class="details-job">${t.jobtitle}</span>
          <div class="details-rating">${stars}</div>
          <p class="details-quote">"${t.text}"</p>
        `;
        detailsTarget.style.opacity = '1';
        detailsTarget.style.transform = 'translateY(0)';
      }, 150);
    }
    
    // Initial load
    showTestimonial(0);
    
    cover.onclick = (e) => {
      cover.classList.add('flipped');
      book.style.transform = 'translateX(140px)';
    };
    
    closeBtn.onclick = (e) => {
      e.stopPropagation();
      cover.classList.remove('flipped');
      book.style.transform = 'translateX(0)';
    };
    
    indexItems.forEach((item) => {
      item.onclick = (e) => {
        e.stopPropagation();
        indexItems.forEach(i => i.classList.remove('active'));
        item.classList.add('active');
        showTestimonial(parseInt(item.getAttribute('data-idx')));
      };
    });
    
  }, 500);
})(this)"></svg>
</div>
```

### CSS
```css
#card-5 .testimonial-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #090b11;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-5 .flipbook-container {
  transform: scale(0.68);
  -webkit-transform: scale(0.68);
  transform-origin: center center;
  -webkit-transform-origin: center center;
  perspective: 1200px;
  -webkit-perspective: 1200px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 280px;
}
#card-5 .book {
  position: relative;
  width: 260px;
  height: 320px;
  transform-style: preserve-3d;
  -webkit-transform-style: preserve-3d;
  transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
}
#card-5 .page {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  transform-style: preserve-3d;
  -webkit-transform-style: preserve-3d;
  transform-origin: left center;
  -webkit-transform-origin: left center;
  transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
  border-radius: 12px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  background: #111827;
  color: #fff;
  cursor: pointer;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.08);
}
#card-5 .page.cover {
  background: #020617;
  z-index: 5;
  border: 1px solid rgba(255, 255, 255, 0.12);
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-5 .page.cover.flipped {
  transform: rotateY(-180deg);
  z-index: 1;
}
#card-5 .page.inside.left {
  z-index: 3;
  transform: rotateY(-180deg);
  background: #1f2937;
  border-right: 1px solid rgba(255, 255, 255, 0.1);
  cursor: default;
}
#card-5 .page.inside.right {
  z-index: 2;
  background: #111827;
  cursor: default;
}
#card-5 .cover-content {
  text-align: center;
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#card-5 .logo-wrapper {
  color: #6366f1;
  margin-bottom: 12px;
}
#card-5 .cover-content h2 {
  font-size: 24px;
  font-weight: 800;
  letter-spacing: -0.5px;
}
#card-5 .cover-content .line {
  width: 40px;
  height: 2px;
  background: #6366f1;
  margin: 12px 0;
}
#card-5 .cover-content p {
  font-size: 13px;
  color: #9ca3af;
  line-height: 1.4;
}
#card-5 .tap-hint {
  font-size: 11px;
  color: #6366f1;
  margin-top: 24px;
  font-weight: 500;
  letter-spacing: 0.5px;
  text-transform: uppercase;
}
#card-5 .page-content {
  padding: 20px;
  height: 100%;
  display: flex;
  flex-direction: column;
}
#card-5 .page-heading {
  font-size: 16px;
  font-weight: 700;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  padding-bottom: 8px;
  margin-bottom: 16px;
  color: #a5b4fc;
}
#card-5 .index-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 12px;
}
#card-5 .index-item {
  display: flex;
  align-items: center;
  gap: 10px;
  cursor: pointer;
  padding: 6px;
  border-radius: 8px;
  transition: background 0.2s;
}
#card-5 .index-item:hover, #card-5 .index-item.active {
  background: rgba(255,255,255,0.08);
}
#card-5 .index-item img {
  width: 24px;
  height: 24px;
  border-radius: 50%;
  object-fit: cover;
}
#card-5 .index-item span {
  font-size: 12px;
  font-weight: 500;
}
#card-5 .close-book-btn {
  margin-top: auto;
  padding: 8px;
  border-radius: 6px;
  border: 1px solid rgba(255,255,255,0.1);
  background: transparent;
  color: #9ca3af;
  font-size: 11px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s;
}
#card-5 .close-book-btn:hover {
  background: rgba(255,255,255,0.05);
  color: #fff;
}
#card-5 #details-target-5 {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  transition: all 0.25s ease;
}
#card-5 .details-avatar img {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #6366f1;
  margin-bottom: 12px;
}
#card-5 .details-name {
  font-size: 16px;
  font-weight: 700;
}
#card-5 .details-job {
  font-size: 12px;
  color: #9ca3af;
  margin-bottom: 8px;
}
#card-5 .details-rating {
  margin-bottom: 12px;
}
#card-5 .star {
  color: #cbd5e1;
  font-size: 14px;
}
#card-5 .star.fill {
  color: #f59e0b;
}
#card-5 .details-quote {
  font-size: 13px;
  line-height: 1.5;
  color: #d1d5db;
  font-style: italic;
}
```

### React
```tsx
\
```