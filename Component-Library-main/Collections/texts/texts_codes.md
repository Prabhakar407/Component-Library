# Premium Custom Text Animation Code Database

This file contains the complete, self-contained HTML, CSS and React code snippets for all Premium Text Animations featured in the interactive showcase.

---

## Text Effect #1: Gradient Shift Text

### HTML
```html
<div class="text-preview-wrapper">
<h2 class="gradient-shift-text">Shifting Visionary Future</h2>
</div>
```

### CSS
```css
#card-1 .text-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #020408;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-1 .gradient-shift-text {
  font-family: 'Outfit', sans-serif;
  font-size: 28px;
  font-weight: 700;
  letter-spacing: -1px;
  background: linear-gradient(120deg, #ff007f, #7f00ff, #00f0ff, #ff007f);
  background-size: 300% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: bgShift 4s linear infinite;
}
@keyframes bgShift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
```

### React
```tsx
import React from 'react';

export default function GradientShiftText() {
  return (
    <h2 className="text-3xl font-bold tracking-tight bg-gradient-to-r from-pink-500 via-purple-600 to-cyan-400 bg-[length:300%_auto] animate-pulse bg-clip-text text-transparent">
      Shifting Visionary Future
    </h2>
  );
}
```

---

## Text Effect #2: Word Reveal Text

### HTML
```html
<div class="text-preview-wrapper">
<div class="word-reveal-box">
  <span class="word-holder"><span>Bespoke</span></span>
  <span class="word-holder"><span>Design</span></span>
  <span class="word-holder"><span>Systems</span></span>
</div>
</div>
```

### CSS
```css
#card-2 .text-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #090e17;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-2 .word-reveal-box {
  display: flex;
  gap: 8px;
  font-family: 'Outfit', sans-serif;
  font-size: 26px;
  font-weight: 600;
}
#card-2 .word-holder {
  overflow: hidden;
  display: inline-block;
}
#card-2 .word-holder > span {
  display: inline-block;
  color: #fff;
  transform: translateY(100%);
  animation: revealWord 0.8s cubic-bezier(0.16, 1, 0.3, 1) both;
}
#card-2 .word-holder:nth-child(2) > span { animation-delay: 0.15s; }
#card-2 .word-holder:nth-child(3) > span { animation-delay: 0.3s; }
@keyframes revealWord {
  to { transform: translateY(0); }
}
```

### React
```tsx
import React from 'react';

export default function WordRevealText() {
  return (
    <div className="flex gap-2 text-2xl font-semibold overflow-hidden">
      <span className="animate-slide-up">Bespoke</span>
      <span className="animate-slide-up [animation-delay:0.15s]">Design</span>
      <span className="animate-slide-up [animation-delay:0.3s]">Systems</span>
    </div>
  );
}
```

---

## Text Effect #3: Chromatic Glitch Text

### HTML
```html
<div class="text-preview-wrapper">
<h2 class="glitch-text" data-text="CHROMATIC">CHROMATIC</h2>
</div>
```

### CSS
```css
#card-3 .text-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #050508;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-3 .glitch-text {
  position: relative;
  font-family: 'JetBrains Mono', monospace;
  font-size: 32px;
  font-weight: 700;
  letter-spacing: 4px;
  color: #fff;
}
#card-3 .glitch-text::before,
#card-3 .glitch-text::after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #050508;
}
#card-3 .glitch-text::before {
  left: 2px;
  text-shadow: -2px 0 #ff00ff;
  clip: rect(44px, 450px, 56px, 0);
  animation: glitch-anim 5s infinite linear alternate-reverse;
}
#card-3 .glitch-text::after {
  left: -2px;
  text-shadow: -2px 0 #00ffff, 0 2px #ff00ff;
  clip: rect(85px, 450px, 140px, 0);
  animation: glitch-anim-2 5s infinite linear alternate-reverse;
}
@keyframes glitch-anim {
  0% { clip: rect(15px, 9999px, 66px, 0); }
  100% { clip: rect(34px, 9999px, 55px, 0); }
}
@keyframes glitch-anim-2 {
  0% { clip: rect(70px, 9999px, 105px, 0); }
  100% { clip: rect(12px, 9999px, 85px, 0); }
}
```

### React
```tsx
import React from 'react';

export default function GlitchText() {
  return (
    <h2 className="relative font-mono text-4xl font-bold tracking-widest text-white after:content-[attr(data-text)] before:content-[attr(data-text)]" data-text="CHROMATIC">
      CHROMATIC
    </h2>
  );
}
```

---

## Text Effect #4: Morphing Text Animation

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="morph-wrapper">
  <div class="morph-text-container">
    <span id="morph-text-1">Hello</span>
    <span id="morph-text-2">Morphing</span>
  </div>
  
  <svg class="morph-filters" style="position: absolute; width: 0; height: 0;">
    <defs>
      <filter id="morph-threshold">
        <feColorMatrix in="SourceGraphic" type="matrix" values="1 0 0 0 0
                                                             0 1 0 0 0
                                                             0 0 1 0 0
                                                             0 0 0 255 -140" />
      </filter>
    </defs>
  </svg>

  <svg width="0" height="0" style="position:absolute;" onload="(function(el){
    setTimeout(function(){
      const container = el.closest('.hero-preview-wrapper');
      if (!container) return;
      const t1 = container.querySelector('#morph-text-1');
      const t2 = container.querySelector('#morph-text-2');
      if (!t1 || !t2) return;
      
      const texts = [
        'Hello',
        'Morphing',
        'Text',
        'Animation',
        'React',
        'Component',
        'Smooth',
        'Transition',
        'Engaging'
      ];
      
      let textIndex = 0;
      let time = new Date();
      let morph = 0;
      let cooldown = 0.25;
      
      t1.textContent = texts[textIndex % texts.length];
      t2.textContent = texts[(textIndex + 1) % texts.length];
      
      function doMorph() {
        morph -= cooldown;
        cooldown = 0;
        
        let fraction = morph / 1.0;
        if (fraction > 1) {
          cooldown = 0.25;
          fraction = 1;
        }
        
        setMorph(fraction);
      }
      
      function setMorph(fraction) {
        t2.style.filter = 'blur(' + (1 - fraction) * 12 + 'px)';
        t2.style.opacity = '' + Math.pow(fraction, 0.4) * 100 + '%';
        
        t1.style.filter = 'blur(' + fraction * 12 + 'px)';
        t1.style.opacity = '' + Math.pow(1 - fraction, 0.4) * 100 + '%';
        
        t1.textContent = texts[textIndex % texts.length];
        t2.textContent = texts[(textIndex + 1) % texts.length];
      }
      
      function doCooldown() {
        morph = 0;
        t2.style.filter = '';
        t2.style.opacity = '100%';
        t1.style.filter = '';
        t1.style.opacity = '0%';
      }
      
      let animateId;
      function animate() {
        let newTime = new Date();
        let shouldIncrementIndex = false;
        let dt = (newTime - time) / 1000;
        time = newTime;
        
        cooldown -= dt;
        
        if (cooldown <= 0) {
          if (cooldown < -1.0) {
            shouldIncrementIndex = true;
            cooldown = 0.25;
          }
          
          doMorph();
          if (shouldIncrementIndex) {
            textIndex++;
          }
        } else {
          doCooldown();
        }
        animateId = requestAnimationFrame(animate);
      }
      animate();
      
      container._morphCleanup = () => cancelAnimationFrame(animateId);
    }, 500);
  })(this)"></svg>
</div>
</div>
```

### CSS
```css
#card-4 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #020408;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-4 .morph-wrapper {
  filter: url(#morph-threshold);
  position: relative;
  width: 100%;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-4 .morph-text-container {
  position: relative;
  width: 100%;
  text-align: center;
}
#card-4 .morph-text-container span {
  position: absolute;
  display: inline-block;
  width: 100%;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  font-family: 'Outfit', sans-serif;
  font-size: 38px;
  font-weight: 700;
  color: #fff;
  user-select: none;
}
```

### React
```tsx
import { MorphingText } from "@/registry/magicui/morphing-text"

const texts = [
  "Hello",
  "Morphing",
  "Text",
  "Animation",
  "React",
  "Component",
  "Smooth",
  "Transition",
  "Engaging",
]

export function MorphingTextDemo() {
  return <MorphingText texts={texts} />
}
```

---

## Text Effect #5: Video Text Mask

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="video-text-container">
  <video autoplay muted loop playsinline class="mask-video">
    <source src="https://cdn.magicui.design/ocean-small.webm" type="video/webm">
  </video>
  <div class="video-text-headline">OCEAN</div>
</div>
</div>
```

### CSS
```css
#card-5 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #000;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-5 .video-text-container {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background: #000;
}
#card-5 .mask-video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
#card-5 .video-text-headline {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  margin: 0;
  background: #000;
  color: #fff;
  mix-blend-mode: multiply;
  font-family: 'Outfit', sans-serif;
  font-weight: 900;
  font-size: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  letter-spacing: -2px;
}
```

### React
```tsx
import { VideoText } from "@/registry/magicui/video-text"

export function VideoTextDemo() {
  return (
    <div className="relative h-[200px] w-full overflow-hidden">
      <VideoText src="https://cdn.magicui.design/ocean-small.webm">
        OCEAN
      </VideoText>
    </div>
  )
}
```

---

## Text Effect #6: Video Text Mask Light

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="video-text-container-light">
  <video autoplay muted loop playsinline class="mask-video-light">
    <source src="https://cdn.magicui.design/ocean-small.webm" type="video/webm">
  </video>
  <div class="video-text-headline-light">WAVES</div>
</div>
</div>
```

### CSS
```css
#card-6 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-6 .video-text-container-light {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background: #fff;
}
#card-6 .mask-video-light {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
#card-6 .video-text-headline-light {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  margin: 0;
  background: #fff;
  color: #000;
  mix-blend-mode: screen;
  font-family: 'Outfit', sans-serif;
  font-weight: 900;
  font-size: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  letter-spacing: -2px;
}
```

### React
```tsx
import { VideoText } from "@/registry/magicui/video-text"

export function VideoTextOutlineDemo() {
  return (
    <div className="relative h-[200px] w-full overflow-hidden bg-white">
      <VideoText src="https://cdn.magicui.design/ocean-small.webm" variant="light">
        WAVES
      </VideoText>
    </div>
  )
}
```

---

## Text Effect #7: Bottom-Up Letters

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="bottom-up-container" id="bottom-up-stage-7">
</div>

<svg width="0" height="0" style="position:absolute;" onload="(function(el){
  setTimeout(function(){
    const container = el.closest('.hero-preview-wrapper');
    if (!container) return;
    const stage = container.querySelector('#bottom-up-stage-7');
    if (!stage) return;
    
    const words = ['Climb', 'Lift', 'Stack'];
    let currentWordIdx = 0;
    let isActive = true;
    
    function showWord(word) {
      if (!isActive) return;
      stage.innerHTML = '';
      const letters = [...word];
      letters.forEach((char, i) => {
        const span = document.createElement('span');
        span.className = 'bottom-up-letter';
        span.textContent = char === ' ' ? '\u00A0' : char;
        span.style.animationDelay = (i * 88) + 'ms';
        span.classList.add('enter');
        stage.appendChild(span);
      });
      
      const totalEnterTime = (letters.length * 88) + 400;
      const timeout1 = setTimeout(() => {
        if (!isActive) return;
        const spanElements = stage.querySelectorAll('.bottom-up-letter');
        spanElements.forEach((span, i) => {
          span.classList.remove('enter');
          span.style.animationDelay = (i * 28) + 'ms';
          span.classList.add('exit');
        });
        
        const totalExitTime = (letters.length * 28) + 280;
        const timeout2 = setTimeout(() => {
          if (!isActive) return;
          currentWordIdx = (currentWordIdx + 1) % words.length;
          showWord(words[currentWordIdx]);
        }, totalExitTime + 320);
        
        container._btn7Timeout2 = timeout2;
      }, totalEnterTime + 550);
      
      container._btn7Timeout1 = timeout1;
    }
    
    showWord(words[currentWordIdx]);
    
    container._btn7Cleanup = () => {
      isActive = false;
      clearTimeout(container._btn7Timeout1);
      clearTimeout(container._btn7Timeout2);
    };
  }, 500);
})(this)"></svg>
</div>
```

### CSS
```css
#card-7 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #0b0f19;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-7 .bottom-up-container {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Outfit', sans-serif;
  font-size: 38px;
  font-weight: 700;
  color: #fff;
  height: 80px;
}
#card-7 .bottom-up-letter {
  display: inline-block;
  opacity: 0;
  transform: translateY(46px);
  will-change: transform, opacity;
  white-space: pre;
}

@keyframes riseUpEnter {
  from {
    opacity: 0;
    transform: translateY(46px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes riseUpExit {
  from {
    opacity: 1;
    transform: translateY(0);
  }
  to {
    opacity: 0;
    transform: translateY(-14px);
  }
}

#card-7 .bottom-up-letter.enter {
  animation: riseUpEnter 400ms cubic-bezier(0.18, 1, 0.32, 1) both;
}
#card-7 .bottom-up-letter.exit {
  animation: riseUpExit 280ms cubic-bezier(0.7, 0, 0.84, 0) both;
}
```

### React
```tsx
// bottom-up-letters.tsx
import React, { useMemo } from 'react';
import TextAnimator from './text-animator';

const BASE_SPEC = {
  id: "bottom-up-letters",
  target: "per-character",
  enter: {
    durationMs: 400,
    staggerMs: 88,
    easing: "cubic-bezier(0.18, 1, 0.32, 1)",
    from: { opacity: 0, yPx: 46 },
    to: { opacity: 1, yPx: 0 }
  },
  exit: {
    durationMs: 280,
    staggerMs: 28,
    easing: "cubic-bezier(0.7, 0, 0.84, 0)",
    from: { opacity: 1, yPx: 0 },
    to: { opacity: 0, yPx: -14 }
  }
};

export default function BottomUpLetters({ text = ["Climb", "Lift", "Stack"] }) {
  const samples = Array.isArray(text) ? text : [text];
  return (
    <TextAnimator
      spec={BASE_SPEC}
      samples={samples}
    />
  );
}
```

---

## Text Effect #8: Kinetic Center Build

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="kinetic-container" id="kinetic-stage-8">
</div>

<svg width="0" height="0" style="position:absolute;" onload="(function(el){
  setTimeout(function(){
    const container = el.closest('.hero-preview-wrapper');
    if (!container) return;
    const stage = container.querySelector('#kinetic-stage-8');
    if (!stage) return;
    
    const phrases = [
      ['Each', 'word', 'arrives'],
      ['Center', 'holds', 'still'],
      ['Builds', 'one', 'line']
    ];
    
    let phraseIdx = 0;
    let isActive = true;
    
    function showPhrase(phrase) {
      if (!isActive) return;
      stage.innerHTML = '';
      
      let wordIdx = 0;
      function addNextWord() {
        if (!isActive) return;
        if (wordIdx < phrase.length) {
          const span = document.createElement('span');
          span.className = 'kinetic-word';
          span.textContent = phrase[wordIdx];
          stage.appendChild(span);
          
          wordIdx++;
          const timeout = setTimeout(addNextWord, 430 + 100);
          container._btn8TimeoutWord = timeout;
        } else {
          // All words added, hold and exit
          const timeoutHold = setTimeout(() => {
            if (!isActive) return;
            const words = stage.querySelectorAll('.kinetic-word');
            words.forEach(w => w.classList.add('exit'));
            
            const timeoutExit = setTimeout(() => {
              if (!isActive) return;
              phraseIdx = (phraseIdx + 1) % phrases.length;
              showPhrase(phrases[phraseIdx]);
            }, 260 + 50);
            container._btn8TimeoutExit = timeoutExit;
          }, 980);
          container._btn8TimeoutHold = timeoutHold;
        }
      }
      
      addNextWord();
    }
    
    showPhrase(phrases[phraseIdx]);
    
    container._btn8Cleanup = () => {
      isActive = false;
      clearTimeout(container._btn8TimeoutWord);
      clearTimeout(container._btn8TimeoutHold);
      clearTimeout(container._btn8TimeoutExit);
    };
  }, 500);
})(this)"></svg>
</div>
```

### CSS
```css
#card-8 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #020204;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-8 .kinetic-container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  width: 100%;
  height: 80px;
}
#card-8 .kinetic-word {
  display: inline-block;
  font-family: 'Outfit', sans-serif;
  font-size: 32px;
  font-weight: 700;
  color: #fff;
  will-change: transform, opacity, filter;
  animation: wordEnter 430ms cubic-bezier(0.2, 0.8, 0.2, 1) both;
}

@keyframes wordEnter {
  from {
    opacity: 0;
    transform: translateX(88px) scale(0.992) translateY(6px);
    filter: blur(3.5px);
  }
  to {
    opacity: 1;
    transform: translateX(0) scale(1) translateY(0);
    filter: blur(0);
  }
}

#card-8 .kinetic-word.exit {
  animation: wordExit 260ms cubic-bezier(0.4, 0, 0.2, 1) both;
}

@keyframes wordExit {
  from {
    opacity: 1;
    transform: translateY(0);
    filter: blur(0);
  }
  to {
    opacity: 0;
    transform: translateY(-6px);
    filter: blur(2.5px);
  }
}
```

### React
```tsx
// kinetic-center-build.tsx
import React, { useMemo } from 'react';
import TextAnimator from './text-animator';

const BASE_SPEC = {
  id: "kinetic-center-build",
  target: "per-word",
  enter: {
    durationMs: 360,
    staggerMs: 0,
    easing: "cubic-bezier(0.2, 0.8, 0.2, 1)",
    from: { opacity: 0, yPx: 6, scale: 0.992, blurPx: 3.5 },
    to: { opacity: 1, yPx: 0, scale: 1, blurPx: 0 }
  },
  exit: {
    durationMs: 260,
    staggerMs: 0,
    easing: "cubic-bezier(0.4, 0, 0.2, 1)",
    from: { opacity: 1, yPx: 0, blurPx: 0 },
    to: { opacity: 0, yPx: -6, blurPx: 2.5 }
  },
  customRenderer: "kinetic-center-build",
  build: {
    firstWordDurationMs: 340,
    pushDurationMs: 430,
    entryOffsetPx: 88,
    wordGapPx: 10,
    firstWordYPx: 6,
    entryScale: 0.992,
    entryBlurPx: 3.5,
    reflowBlurPx: 0.8,
    exitYPx: -6,
    exitBlurPx: 2.5,
    easing: "cubic-bezier(0.2, 0.8, 0.2, 1)",
    exitEasing: "cubic-bezier(0.4, 0, 0.2, 1)"
  }
};

export default function KineticCenterBuild({ phrases = [["Each", "word", "arrives"], ["Center", "holds", "still"]] }) {
  return (
    <TextAnimator
      spec={BASE_SPEC}
      phrases={phrases}
    />
  );
}
```

---

## Text Effect #9: Line-by-Line Slide

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="line-slide-container" id="line-stage-9">
</div>

<svg width="0" height="0" style="position:absolute;" onload="(function(el){
  setTimeout(function(){
    const container = el.closest('.hero-preview-wrapper');
    if (!container) return;
    const stage = container.querySelector('#line-stage-9');
    if (!stage) return;
    
    const samples = [
      'Each line\nslides in turn.',
      'Top arrives,\nthen the next.',
      'Reads top down,\nleft to right.'
    ];
    
    let sampleIdx = 0;
    let isActive = true;
    
    function showSample(text) {
      if (!isActive) return;
      stage.innerHTML = '';
      const lines = text.split('\n');
      lines.forEach((line, i) => {
        const div = document.createElement('div');
        div.className = 'slide-line';
        div.textContent = line;
        div.style.animationDelay = (i * 120) + 'ms';
        div.classList.add('enter');
        stage.appendChild(div);
      });
      
      const totalEnterTime = (lines.length * 120) + 900;
      const timeoutHold = setTimeout(() => {
        if (!isActive) return;
        const lineElements = stage.querySelectorAll('.slide-line');
        lineElements.forEach((div, i) => {
          div.classList.remove('enter');
          div.style.animationDelay = (i * 80) + 'ms';
          div.classList.add('exit');
        });
        
        const totalExitTime = (lines.length * 80) + 600;
        const timeoutNext = setTimeout(() => {
          if (!isActive) return;
          sampleIdx = (sampleIdx + 1) % samples.length;
          showSample(samples[sampleIdx]);
        }, totalExitTime + 320);
        
        container._btn9TimeoutNext = timeoutNext;
      }, totalEnterTime + 550);
      
      container._btn9TimeoutHold = timeoutHold;
    }
    
    showSample(samples[sampleIdx]);
    
    container._btn9Cleanup = () => {
      isActive = false;
      clearTimeout(container._btn9TimeoutHold);
      clearTimeout(container._btn9TimeoutNext);
    };
  }, 500);
})(this)"></svg>
</div>
```

### CSS
```css
#card-9 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #060913;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-9 .line-slide-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 8px;
  width: 100%;
  height: 120px;
  text-align: center;
}
#card-9 .slide-line {
  font-family: 'Outfit', sans-serif;
  font-size: 26px;
  font-weight: 600;
  color: #fff;
  opacity: 0;
  transform: translateX(-48px);
  will-change: transform, opacity;
  display: block;
}

@keyframes lineSlideEnter {
  from {
    opacity: 0;
    transform: translateX(-48px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
@keyframes lineSlideExit {
  from {
    opacity: 1;
    transform: translateX(0);
  }
  to {
    opacity: 0;
    transform: translateX(48px);
  }
}

#card-9 .slide-line.enter {
  animation: lineSlideEnter 900ms cubic-bezier(0.22, 1, 0.36, 1) both;
}
#card-9 .slide-line.exit {
  animation: lineSlideExit 600ms cubic-bezier(0.64, 0, 0.78, 0) both;
}
```

### React
```tsx
// line-by-line-slide.tsx
import React, { useMemo } from 'react';
import TextAnimator from './text-animator';

const BASE_SPEC = {
  id: "line-by-line-slide",
  target: "per-line",
  enter: {
    durationMs: 900,
    staggerMs: 120,
    easing: "cubic-bezier(0.22, 1, 0.36, 1)",
    from: { opacity: 0, xPx: -48 },
    to: { opacity: 1, xPx: 0 }
  },
  exit: {
    durationMs: 600,
    staggerMs: 80,
    easing: "cubic-bezier(0.64, 0, 0.78, 0)",
    from: { opacity: 1, xPx: 0 },
    to: { opacity: 0, xPx: 48 }
  }
};

export default function LineByLineSlide({ text = ["Each line\nslides in turn.", "Top arrives,\nthen the next."] }) {
  const samples = Array.isArray(text) ? text : [text];
  return (
    <TextAnimator
      spec={BASE_SPEC}
      samples={samples}
    />
  );
}
```

---

## Text Effect #10: Per-Character Rise

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="char-rise-container" id="char-stage-10">
</div>

<svg width="0" height="0" style="position:absolute;" onload="(function(el){
  setTimeout(function(){
    const container = el.closest('.hero-preview-wrapper');
    if (!container) return;
    const stage = container.querySelector('#char-stage-10');
    if (!stage) return;
    
    const samples = [
      'Each letter rises in.',
      'Rises into place.',
      'Crisp on every beat.'
    ];
    
    let sampleIdx = 0;
    let isActive = true;
    
    function showSample(text) {
      if (!isActive) return;
      stage.innerHTML = '';
      const letters = [...text];
      letters.forEach((char, i) => {
        const span = document.createElement('span');
        span.className = 'char-rise-letter';
        span.textContent = char === ' ' ? '\u00A0' : char;
        span.style.animationDelay = (i * 24) + 'ms';
        span.classList.add('enter');
        stage.appendChild(span);
      });
      
      const totalEnterTime = (letters.length * 24) + 700;
      const timeoutHold = setTimeout(() => {
        if (!isActive) return;
        const spanElements = stage.querySelectorAll('.char-rise-letter');
        spanElements.forEach((span, i) => {
          span.classList.remove('enter');
          span.style.animationDelay = (i * 14) + 'ms';
          span.classList.add('exit');
        });
        
        const totalExitTime = (letters.length * 14) + 420;
        const timeoutNext = setTimeout(() => {
          if (!isActive) return;
          sampleIdx = (sampleIdx + 1) % samples.length;
          showSample(samples[sampleIdx]);
        }, totalExitTime + 320);
        
        container._btn10TimeoutNext = timeoutNext;
      }, totalEnterTime + 550);
      
      container._btn10TimeoutHold = timeoutHold;
    }
    
    showSample(samples[sampleIdx]);
    
    container._btn10Cleanup = () => {
      isActive = false;
      clearTimeout(container._btn10TimeoutHold);
      clearTimeout(container._btn10TimeoutNext);
    };
  }, 500);
})(this)"></svg>
</div>
```

### CSS
```css
#card-10 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #03080f;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-10 .char-rise-container {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Outfit', sans-serif;
  font-size: 32px;
  font-weight: 600;
  color: #fff;
  height: 80px;
}
#card-10 .char-rise-letter {
  display: inline-block;
  opacity: 0;
  transform: translateY(32px);
  will-change: transform, opacity;
  white-space: pre;
}

@keyframes charRiseEnter {
  from {
    opacity: 0;
    transform: translateY(32px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes charRiseExit {
  from {
    opacity: 1;
    transform: translateY(0);
  }
  to {
    opacity: 0;
    transform: translateY(-24px);
  }
}

#card-10 .char-rise-letter.enter {
  animation: charRiseEnter 700ms cubic-bezier(0.2, 0.8, 0.2, 1) both;
}
#card-10 .char-rise-letter.exit {
  animation: charRiseExit 420ms cubic-bezier(0.7, 0, 0.84, 0) both;
}
```

### React
```tsx
// per-character-rise.tsx
import React, { useMemo } from 'react';
import TextAnimator from './text-animator';

const BASE_SPEC = {
  id: "per-character-rise",
  target: "per-character",
  enter: {
    durationMs: 700,
    staggerMs: 24,
    easing: "cubic-bezier(0.2, 0.8, 0.2, 1)",
    from: { opacity: 0, yPx: 32 },
    to: { opacity: 1, yPx: 0 }
  },
  exit: {
    durationMs: 420,
    staggerMs: 14,
    easing: "cubic-bezier(0.7, 0, 0.84, 0)",
    from: { opacity: 1, yPx: 0 },
    to: { opacity: 0, yPx: -24 }
  }
};

export default function PerCharacterRise({ text = ["Each letter rises in.", "Rises into place."] }) {
  const samples = Array.isArray(text) ? text : [text];
  return (
    <TextAnimator
      spec={BASE_SPEC}
      samples={samples}
    />
  );
}
```

---

## Text Effect #11: Kinetic Text

### HTML
```html
<div class="hero-preview-wrapper select-none">
<div class="kinetic-text-demo-container">
  <h1 class="kinetic-text-headline">
    <span>N</span><span>o</span><span>s</span><span>t</span><span>a</span><span>l</span><span>g</span><span>i</span><span>a</span>
  </h1>
</div>
</div>
```

### CSS
```css
#card-11 .hero-preview-wrapper {
  width: 100%;
  height: 100%;
  background: #000;
  display: flex;
  align-items: center;
  justify-content: center;
}
#card-11 .kinetic-text-demo-container {
  display: flex;
  justify-content: center;
  align-items: center;
}
#card-11 .kinetic-text-headline {
  display: flex;
  flex-wrap: wrap;
  font-family: 'Outfit', sans-serif;
  font-weight: 300;
  color: #fff;
  font-size: 6rem;
  letter-spacing: -0.05em;
  --hover-padding: calc(1rem / 12);
  --text-stroke-width: calc(1rem * 125 / 6000);
  box-sizing: border-box;
}
#card-11 .kinetic-text-headline span {
  display: inline-block;
  will-change: font-weight, -webkit-text-stroke-width, padding;
  -webkit-text-stroke-color: transparent;
  -webkit-text-stroke-width: var(--text-stroke-width);
  transition: font-weight 0.4s, -webkit-text-stroke-color 0.4s, padding 0.4s;
  cursor: default;
}

/* Hover styles using sibling and :has selectors */
#card-11 .kinetic-text-headline span:hover {
  padding-left: var(--hover-padding);
  padding-right: var(--hover-padding);
  font-weight: 900;
  -webkit-text-stroke-color: currentColor;
  -webkit-text-stroke-width: calc(var(--text-stroke-width) * 2);
}

/* Sibling immediately after hover */
#card-11 .kinetic-text-headline span:hover + span {
  padding-left: var(--hover-padding);
  padding-right: var(--hover-padding);
  font-weight: 600;
}

/* Sibling two places after hover */
#card-11 .kinetic-text-headline span:hover + span + span {
  font-weight: 400;
}

/* Sibling immediately before hover */
#card-11 .kinetic-text-headline span:has(+ span:hover) {
  padding-left: var(--hover-padding);
  padding-right: var(--hover-padding);
  font-weight: 600;
}

/* Sibling two places before hover */
#card-11 .kinetic-text-headline span:has(+ span + span:hover) {
  font-weight: 400;
}
```

### React
```tsx
import React from "react"
import { cn } from "@/lib/utils"

export function KineticText({
  text = "Nostalgia",
  className = "",
}) {
  const mergedStyle = {
    "--hover-padding": "calc(1em / 12)",
    "--text-stroke-width": "calc(1em * 125 / 6000)",
  };

  return (
    <h1
      className={cn("flex flex-wrap font-[300]", className)}
      style={mergedStyle}
    >
      {text.split("").map((letter, i) => (
        <span
          key={i}
          className="[will-change:font-weight,-webkit-text-stroke-width,padding] [-webkit-text-stroke-color:transparent] [-webkit-text-stroke-width:var(--text-stroke-width)] [transition:font-weight_0.4s,_-webkit-text-stroke-color_0.4s,_padding_0.4s] hover:[padding-inline:var(--hover-padding)] hover:font-[900] hover:[-webkit-text-stroke-color:currentcolor] hover:[-webkit-text-stroke-width:calc(var(--text-stroke-width)*2)] has-[+span+span:hover]:font-[400] has-[+span:hover]:[padding-inline:var(--hover-padding)] has-[+span:hover]:font-[600] [:hover+&]:[padding-inline:var(--hover-padding)] [:hover+&]:font-[600] [:hover+span+&]:font-[400]"
        >
          {letter === " " ? "\u00A0" : letter}
        </span>
      ))}
    </h1>
  );
}
```

---