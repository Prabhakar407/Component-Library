# Premium Custom Footer Section Code Database

This file contains the complete, self-contained HTML, CSS and React code snippets for all Premium Footers featured in the interactive showcase.

---

## Footer #1: SaaS Multi-Column Footer

### HTML
```html
<div class="footer-preview-wrapper">
<footer class="saas-footer">
  <div class="grid-columns">
    <div class="brand-col">
      <h3>Neuramax</h3>
      <p>Premium UI modules built for elite product interfaces.</p>
    </div>
    <div>
      <h4>Products</h4>
      <a href="#">Showcases</a>
      <a href="#">Pro Assets</a>
      <a href="#">Docs</a>
    </div>
    <div>
      <h4>Newsletter</h4>
      <div class="sub-form">
        <input type="email" placeholder="Enter email...">
        <button>→</button>
      </div>
    </div>
  </div>
  <div class="bottom-bar">
    <span>© 2026 Neuramax Inc. All rights reserved.</span>
  </div>
</footer>
</div>
```

### CSS
```css
#card-1 .footer-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #090e17;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-1 .saas-footer {
  transform: scale(0.6);
  transform-origin: center center;
  width: 900px;
  background: #111827;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 16px;
  padding: 40px;
  display: flex;
  flex-direction: column;
  gap: 32px;
  font-family: 'Inter', sans-serif;
  color: #fff;
  box-sizing: border-box;
}
#card-1 .grid-columns {
  display: grid;
  grid-template-columns: 2fr 1fr 2fr;
  gap: 32px;
}
#card-1 .brand-col h3 {
  font-size: 22px;
  font-weight: 700;
  margin-bottom: 12px;
}
#card-1 .brand-col p {
  color: rgba(255,255,255,0.6);
  font-size: 14px;
  line-height: 1.5;
}
#card-1 h4 {
  font-size: 15px;
  font-weight: 600;
  margin-bottom: 16px;
  color: #a5b4fc;
}
#card-1 a {
  display: block;
  font-size: 14px;
  color: rgba(255,255,255,0.6);
  text-decoration: none;
  margin-bottom: 8px;
  transition: color 0.2s;
}
#card-1 a:hover {
  color: #fff;
}
#card-1 .sub-form {
  display: flex;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 8px;
  padding: 4px;
}
#card-1 .sub-form input {
  background: transparent;
  border: none;
  outline: none;
  color: #fff;
  padding: 8px 12px;
  font-size: 13px;
  flex-1: 1;
}
#card-1 .sub-form button {
  background: #6366f1;
  color: #fff;
  border: none;
  width: 32px;
  height: 32px;
  border-radius: 6px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
}
#card-1 .bottom-bar {
  border-top: 1px solid rgba(255,255,255,0.08);
  padding-top: 20px;
  font-size: 12px;
  color: rgba(255,255,255,0.4);
}
```

### React
```tsx
import React from 'react';

export default function SaasFooter() {
  return (
    <footer className="bg-slate-950 text-white p-12 border-t border-white/10 rounded-2xl">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div>
          <h3 className="text-xl font-bold">Neuramax</h3>
          <p className="text-slate-400 text-sm mt-2">Premium UI modules for elite interfaces.</p>
        </div>
        <div>
          <h4 className="font-semibold text-indigo-400">Products</h4>
          <ul className="space-y-2 mt-4 text-sm text-slate-300">
            <li><a href="#" className="hover:text-white">Showcases</a></li>
            <li><a href="#" className="hover:text-white">Pro Assets</a></li>
          </ul>
        </div>
      </div>
    </footer>
  );
}
```

---

## Footer #2: Minimal Editorial Footer

### HTML
```html
<div class="footer-preview-wrapper">
<footer class="editorial-footer">
  <div class="huge-brand">TERRAELIX</div>
  <div class="line-divider"></div>
  <div class="links-row">
    <span>© 2026 TERRAELIX CORP</span>
    <div class="links">
      <a href="#">COLLECTIONS</a>
      <a href="#">EDITORIAL</a>
      <a href="#">STORES</a>
    </div>
  </div>
</footer>
</div>
```

### CSS
```css
#card-2 .footer-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #fbfbfb;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-2 .editorial-footer {
  transform: scale(0.6);
  transform-origin: center center;
  width: 900px;
  background: #fbfbfb;
  border: 1px solid rgba(0, 0, 0, 0.08);
  border-radius: 16px;
  padding: 40px;
  font-family: 'DM Sans', sans-serif;
  color: #111;
  box-sizing: border-box;
}
#card-2 .huge-brand {
  font-size: 72px;
  font-weight: 500;
  letter-spacing: -2px;
  text-align: center;
  color: #111;
  margin-bottom: 24px;
}
#card-2 .line-divider {
  height: 1px;
  background: rgba(0, 0, 0, 0.08);
  margin-bottom: 24px;
}
#card-2 .links-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 13px;
  color: rgba(0, 0, 0, 0.6);
}
#card-2 .links {
  display: flex;
  gap: 24px;
}
#card-2 .links a {
  color: rgba(0, 0, 0, 0.6);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.2s;
}
#card-2 .links a:hover {
  color: #000;
}
```

### React
```tsx
import React from 'react';

export default function EditorialFooter() {
  return (
    <footer className="bg-[#fbfbfb] text-neutral-900 p-12 border-t border-neutral-200 rounded-2xl text-center">
      <h2 className="text-6xl font-bold tracking-tighter">TERRAELIX</h2>
      <div className="border-t border-neutral-200 my-6" />
      <div className="flex justify-between text-sm text-neutral-500">
        <span>© 2026 TERRAELIX CORP</span>
        <div className="flex gap-6">
          <a href="#" className="hover:text-black">COLLECTIONS</a>
          <a href="#" className="hover:text-black">EDITORIAL</a>
        </div>
      </div>
    </footer>
  );
}
```

---

## Footer #3: Creative Agency Glow Footer

### HTML
```html
<div class="footer-preview-wrapper">
<footer class="agency-footer">
  <div class="cta-top">
    <h2>Let's create something extraordinary together.</h2>
    <button class="cta-btn">GET IN TOUCH</button>
  </div>
  <div class="bottom-bar">
    <div class="socials">
      <a href="#">TWITTER</a>
      <a href="#">DRIBBBLE</a>
      <a href="#">LINKEDIN</a>
    </div>
    <span>MADE BY NEURAMAX AGENCY</span>
  </div>
</footer>
</div>
```

### CSS
```css
#card-3 .footer-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #020203;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-3 .agency-footer {
  transform: scale(0.6);
  transform-origin: center center;
  width: 900px;
  background: #08080a;
  border: 1px solid rgba(255, 255, 255, 0.05);
  border-radius: 20px;
  padding: 48px;
  display: flex;
  flex-direction: column;
  gap: 48px;
  font-family: 'Outfit', sans-serif;
  color: #fff;
  box-sizing: border-box;
}
#card-3 .cta-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 32px;
}
#card-3 .cta-top h2 {
  font-size: 28px;
  font-weight: 600;
  line-height: 1.25;
  max-width: 480px;
}
#card-3 .cta-btn {
  background: #6366f1;
  color: #fff;
  border: none;
  padding: 16px 32px;
  font-size: 13px;
  font-weight: 600;
  border-radius: 9999px;
  cursor: pointer;
  letter-spacing: 1px;
  transition: all 0.3s;
}
#card-3 .cta-btn:hover {
  background: #5053e3;
  box-shadow: 0 0 20px rgba(99, 102, 241, 0.4);
}
#card-3 .bottom-bar {
  border-top: 1px solid rgba(255,255,255,0.06);
  padding-top: 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 12px;
  color: rgba(255, 255, 255, 0.4);
}
#card-3 .socials {
  display: flex;
  gap: 20px;
}
#card-3 .socials a {
  color: rgba(255, 255, 255, 0.4);
  text-decoration: none;
  font-weight: 600;
  letter-spacing: 0.5px;
  transition: color 0.2s;
}
#card-3 .socials a:hover {
  color: #6366f1;
}
```

### React
```tsx
import React from 'react';

export default function AgencyFooter() {
  return (
    <footer className="bg-neutral-950 text-white p-12 rounded-2xl">
      <div className="flex justify-between items-center">
        <h2 className="text-3xl font-semibold max-w-lg">Let's create something extraordinary together.</h2>
        <button className="bg-indigo-600 hover:bg-indigo-700 text-white px-8 py-4 rounded-full text-sm font-semibold tracking-wider">
          GET IN TOUCH
        </button>
      </div>
    </footer>
  );
}
```