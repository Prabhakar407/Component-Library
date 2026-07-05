# Premium Custom AI Chats Code Database

This file contains the complete, self-contained HTML, CSS, JavaScript, and React code snippets for all **8 Premium AI Chat Components** featured in the interactive showcase. Each display is numbered to match the UI labels in the application.

---

## Table of Contents
1. [Effect #1: Glassmorphic Chat Container](#effect-1-glassmorphic-chat-container)
2. [Effect #2: Dynamic Message Bubbles](#effect-2-dynamic-message-bubbles)
3. [Effect #3: Pulsing AI Typing Indicator](#effect-3-pulsing-ai-typing-indicator)
4. [Effect #4: Prompt Suggestion Cards](#effect-4-prompt-suggestion-cards)
5. [Effect #5: Interactive Slash Commands Menu](#effect-5-interactive-slash-commands-menu)
6. [Effect #6: Streaming Text Response](#effect-6-streaming-text-response)
7. [Effect #7: Floating Assistant Toggle](#effect-7-floating-assistant-toggle)
8. [Effect #8: Rich Input Controller Bar](#effect-8-rich-input-controller-bar)

---

## Effect #1: Glassmorphic Chat Container
*Interactive dark chat window box containing top headers, messaging logs with scrolling, and messaging submission hooks.*

### HTML
```html
<div class="chat-container-1">
    <div class="chat-header-1">
        <div class="chat-avatar-1">🤖</div>
        <div class="chat-status-info-1">
            <span class="chat-name-1">Antigravity AI</span>
            <span class="chat-status-1">Online</span>
        </div>
    </div>
    <div class="chat-body-1" id="chat-body-1">
        <div class="chat-bubble-ai-1">Hello! How can I help you build your application today?</div>
        <div class="chat-bubble-user-1">Show me some cool buttons!</div>
    </div>
    <div class="chat-input-wrapper-1">
        <input type="text" class="chat-input-1" placeholder="Type a message..." id="chat-input-1" onkeydown="handleChatInput1(event)">
        <button class="chat-send-1" onclick="sendChatMessage1()">Send</button>
    </div>
</div>
```

### CSS
```css
.chat-container-1 {
    width: 100%;
    max-width: 380px;
    height: 220px;
    background: rgba(18, 24, 38, 0.7);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    display: flex;
    flex-direction: column;
    overflow: hidden;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
}

.chat-header-1 {
    padding: 10px 14px;
    background: rgba(0, 0, 0, 0.2);
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
    display: flex;
    align-items: center;
    gap: 10px;
}

.chat-avatar-1 {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    background: rgba(99, 102, 241, 0.15);
    border: 1px solid rgba(99, 102, 241, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.95rem;
}

.chat-status-info-1 {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}

.chat-name-1 {
    font-size: 0.8rem;
    font-weight: 600;
    color: #f8fafc;
}

.chat-status-1 {
    font-size: 0.65rem;
    color: #10b981;
    font-weight: 500;
}

.chat-body-1 {
    flex-grow: 1;
    padding: 12px;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    gap: 8px;
    scroll-behavior: smooth;
}

/* Scrollbars */
.chat-body-1::-webkit-scrollbar {
    width: 4px;
}
.chat-body-1::-webkit-scrollbar-track {
    background: transparent;
}
.chat-body-1::-webkit-scrollbar-thumb {
    background: rgba(255, 255, 255, 0.1);
    border-radius: 2px;
}

.chat-bubble-ai-1, .chat-bubble-user-1 {
    max-width: 80%;
    padding: 8px 12px;
    font-size: 0.75rem;
    line-height: 1.4;
    text-align: left;
}

.chat-bubble-ai-1 {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.05);
    color: #cbd5e1;
    border-radius: 12px 12px 12px 2px;
    align-self: flex-start;
}

.chat-bubble-user-1 {
    background: linear-gradient(135deg, #6366f1 0%, #4f46e5 100%);
    color: #ffffff;
    border-radius: 12px 12px 2px 12px;
    align-self: flex-end;
}

.chat-input-wrapper-1 {
    padding: 8px 10px;
    background: rgba(0, 0, 0, 0.15);
    border-top: 1px solid rgba(255, 255, 255, 0.05);
    display: flex;
    gap: 8px;
}

.chat-input-1 {
    flex-grow: 1;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 6px;
    padding: 6px 10px;
    color: #ffffff;
    font-size: 0.75rem;
    font-family: inherit;
}

.chat-input-1:focus {
    outline: none;
    border-color: rgba(99, 102, 241, 0.5);
    box-shadow: 0 0 6px rgba(99, 102, 241, 0.2);
}

.chat-send-1 {
    background: #6366f1;
    color: #ffffff;
    border: none;
    padding: 6px 12px;
    border-radius: 6px;
    font-size: 0.75rem;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.2s;
}

.chat-send-1:hover {
    background: #4f46e5;
}
```

### JavaScript
```javascript
function sendChatMessage1() {
    const input = document.getElementById('chat-input-1');
    const body = document.getElementById('chat-body-1');
    if (!input || !input.value.trim()) return;

    // Append User message
    const userMsg = document.createElement('div');
    userMsg.className = 'chat-bubble-user-1';
    userMsg.innerText = input.value;
    body.appendChild(userMsg);
    
    const textVal = input.value;
    input.value = '';
    body.scrollTop = body.scrollHeight;

    // Simulate AI response delay
    setTimeout(() => {
        const aiMsg = document.createElement('div');
        aiMsg.className = 'chat-bubble-ai-1';
        aiMsg.innerText = `You typed: "${textVal}". I can process your design request.`;
        body.appendChild(aiMsg);
        body.scrollTop = body.scrollHeight;
    }, 1000);
}

function handleChatInput1(event) {
    if (event.key === 'Enter') {
        sendChatMessage1();
    }
}
```

### React
```tsx
import React, { useState, useRef, useEffect } from 'react';

export function GlassmorphicChat() {
  const [messages, setMessages] = useState([
    { sender: 'ai', text: 'Hello! How can I help you build your application today?' },
    { sender: 'user', text: 'Show me some cool buttons!' }
  ]);
  const [input, setInput] = useState('');
  const bodyRef = useRef<HTMLDivElement>(null);

  useEffect(() => {
    if (bodyRef.current) {
      bodyRef.current.scrollTop = bodyRef.current.scrollHeight;
    }
  }, [messages]);

  const handleSend = () => {
    if (!input.trim()) return;
    const userText = input;
    setMessages((prev) => [...prev, { sender: 'user', text: userText }]);
    setInput('');

    setTimeout(() => {
      setMessages((prev) => [
        ...prev,
        { sender: 'ai', text: `You typed: "${userText}". I can process your design request.` }
      ]);
    }, 1000);
  };

  return (
    <div className="chat-container-1">
      <div className="chat-header-1">
        <div className="chat-avatar-1">🤖</div>
        <div className="chat-status-info-1">
          <span className="chat-name-1">Antigravity AI</span>
          <span className="chat-status-1">Online</span>
        </div>
      </div>
      <div className="chat-body-1" ref={bodyRef}>
        {messages.map((m, idx) => (
          <div key={idx} className={m.sender === 'user' ? 'chat-bubble-user-1' : 'chat-bubble-ai-1'}>
            {m.text}
          </div>
        ))}
      </div>
      <div className="chat-input-wrapper-1">
        <input
          type="text"
          className="chat-input-1"
          placeholder="Type a message..."
          value={input}
          onChange={(e) => setInput(e.target.value)}
          onKeyDown={(e) => e.key === 'Enter' && handleSend()}
        />
        <button className="chat-send-1" onClick={handleSend}>
          Send
        </button>
      </div>
    </div>
  );
}
```

---

## Effect #2: Dynamic Message Bubbles
*Detailed conversational bubbles distinguishing AI and User text panels with avatars and timestamp metadata.*

### HTML
```html
<div class="bubble-stack-2">
    <div class="msg-row-ai-2">
        <div class="avatar-2">🤖</div>
        <div class="bubble-ai-2">
            I've optimized your webpack configurations. The bundle size went from 4.2MB to 1.1MB.
            <span class="time-2">10:42 AM</span>
        </div>
    </div>
    <div class="msg-row-user-2">
        <div class="bubble-user-2">
            Amazing work! Let's deploy it.
            <span class="time-2 user-time-2">10:43 AM</span>
        </div>
        <div class="avatar-2 user-avatar-2">👨‍💻</div>
    </div>
</div>
```

### CSS
```css
.bubble-stack-2 {
    display: flex;
    flex-direction: column;
    gap: 16px;
    width: 100%;
    max-width: 400px;
    padding: 10px;
}

.msg-row-ai-2, .msg-row-user-2 {
    display: flex;
    gap: 10px;
    align-items: flex-end;
    width: 100%;
}

.msg-row-user-2 {
    justify-content: flex-end;
}

.avatar-2 {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8rem;
    flex-shrink: 0;
}

.user-avatar-2 {
    background: rgba(99, 102, 241, 0.15);
    border-color: rgba(99, 102, 241, 0.3);
}

.bubble-ai-2, .bubble-user-2 {
    max-width: 75%;
    padding: 10px 14px;
    font-size: 0.78rem;
    line-height: 1.45;
    position: relative;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    text-align: left;
}

.bubble-ai-2 {
    background: #182032;
    border: 1px solid rgba(255, 255, 255, 0.06);
    color: #f1f5f9;
    border-radius: 12px 12px 12px 3px;
}

.bubble-user-2 {
    background: linear-gradient(135deg, #a855f7 0%, #7c3aed 100%);
    color: #ffffff;
    border-radius: 12px 12px 3px 12px;
}

.time-2 {
    display: block;
    font-size: 0.6rem;
    color: #64748b;
    margin-top: 6px;
    text-align: right;
}

.user-time-2 {
    color: #c084fc;
}
```

### React
```tsx
import React from 'react';

export function MessageBubbles() {
  return (
    <div className="bubble-stack-2">
      <div className="msg-row-ai-2">
        <div className="avatar-2">🤖</div>
        <div className="bubble-ai-2">
          I've optimized your webpack configurations. The bundle size went from 4.2MB to 1.1MB.
          <span className="time-2">10:42 AM</span>
        </div>
      </div>
      <div className="msg-row-user-2">
        <div className="bubble-user-2">
          Amazing work! Let's deploy it.
          <span className="time-2 user-time-2">10:43 AM</span>
        </div>
        <div className="avatar-2 user-avatar-2">👨‍💻</div>
      </div>
    </div>
  );
}
```

---

## Effect #3: Pulsing AI Typing Indicator
*Soft bouncing dots loading indicator showing assistant typing states.*

### HTML
```html
<div class="typing-container-3">
    <div class="typing-avatar-3">🤖</div>
    <div class="typing-bubble-3">
        <div class="typing-dot-3 dot-a-3"></div>
        <div class="typing-dot-3 dot-b-3"></div>
        <div class="typing-dot-3 dot-c-3"></div>
    </div>
    <span class="typing-text-3">AI is thinking...</span>
</div>
```

### CSS
```css
.typing-container-3 {
    display: flex;
    align-items: center;
    gap: 10px;
    background: rgba(18, 24, 38, 0.4);
    border: 1px solid rgba(255, 255, 255, 0.05);
    padding: 10px 16px;
    border-radius: 30px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.typing-avatar-3 {
    font-size: 1rem;
}

.typing-bubble-3 {
    display: flex;
    gap: 4px;
    background: rgba(255, 255, 255, 0.05);
    padding: 8px 12px;
    border-radius: 15px;
    border: 1px solid rgba(255, 255, 255, 0.05);
}

.typing-dot-3 {
    width: 6px;
    height: 6px;
    background-color: #6366f1;
    border-radius: 50%;
    animation: typing-bounce-3 1.4s infinite ease-in-out both;
}

.dot-a-3 { animation-delay: -0.32s; }
.dot-b-3 { animation-delay: -0.16s; }

@keyframes typing-bounce-3 {
    0%, 80%, 100% { transform: scale(0); }
    40% { transform: scale(1.0); }
}

.typing-text-3 {
    font-size: 0.75rem;
    color: #64748b;
    font-weight: 500;
}
```

### React
```tsx
import React from 'react';

export function TypingIndicator() {
  return (
    <div className="typing-container-3">
      <div className="typing-avatar-3">🤖</div>
      <div className="typing-bubble-3">
        <div className="typing-dot-3 dot-a-3"></div>
        <div className="typing-dot-3 dot-b-3"></div>
        <div className="typing-dot-3 dot-c-3"></div>
      </div>
      <span className="typing-text-3">AI is thinking...</span>
    </div>
  );
}
```

---

## Effect #4: Prompt Suggestion Cards
*Sliding grid layout list of premade prompts that fill input controls when clicked.*

### HTML
```html
<div class="prompt-box-4">
    <div class="prompt-title-4">Suggested Prompts</div>
    <div class="prompt-list-4">
        <div class="prompt-card-4" onclick="selectPrompt4(this)">
            <span class="prompt-icon-4">✍️</span> Write a marketing email
        </div>
        <div class="prompt-card-4" onclick="selectPrompt4(this)">
            <span class="prompt-icon-4">🐛</span> Debug React error
        </div>
        <div class="prompt-card-4" onclick="selectPrompt4(this)">
            <span class="prompt-icon-4">📊</span> Summarize financial data
        </div>
    </div>
    <div class="prompt-selected-display-4 hidden" id="prompt-selected-4"></div>
</div>
```

### CSS
```css
.prompt-box-4 {
    width: 100%;
    max-width: 440px;
    padding: 12px;
    background: #0d131f;
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 12px;
}

.prompt-title-4 {
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--text-secondary);
    margin-bottom: 10px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    text-align: left;
}

.prompt-list-4 {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.prompt-card-4 {
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 8px;
    padding: 8px 12px;
    font-size: 0.78rem;
    color: #cbd5e1;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 10px;
    transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
    text-align: left;
}

.prompt-card-4:hover {
    background: rgba(99, 102, 241, 0.08);
    border-color: rgba(99, 102, 241, 0.3);
    color: #ffffff;
    transform: translateX(4px);
}

.prompt-icon-4 {
    font-size: 1rem;
}

.prompt-selected-display-4 {
    margin-top: 10px;
    padding: 8px 12px;
    background: rgba(16, 185, 129, 0.1);
    border: 1px solid rgba(16, 185, 129, 0.3);
    border-radius: 6px;
    font-size: 0.75rem;
    color: #a7f3d0;
    text-align: left;
    animation: slide-up-4 0.3s ease;
}

.prompt-selected-display-4.hidden {
    display: none;
}

@keyframes slide-up-4 {
    from { opacity: 0; transform: translateY(5px); }
    to { opacity: 1; transform: translateY(0); }
}
```

### JavaScript
```javascript
function selectPrompt4(element) {
    const text = element.innerText.substring(2); // Skip icon
    const display = document.getElementById('prompt-selected-4');
    if (display) {
        display.classList.remove('hidden');
        display.innerHTML = `<strong>Selected:</strong> "${text}"`;
    }
}
```

### React
```tsx
import React, { useState } from 'react';

export function PromptSuggestions() {
  const [selected, setSelected] = useState<string | null>(null);

  const prompts = [
    { icon: '✍️', text: 'Write a marketing email' },
    { icon: '🐛', text: 'Debug React error' },
    { icon: '📊', text: 'Summarize financial data' }
  ];

  return (
    <div className="prompt-box-4">
      <div className="prompt-title-4">Suggested Prompts</div>
      <div className="prompt-list-4">
        {prompts.map((p, idx) => (
          <div key={idx} className="prompt-card-4" onClick={() => setSelected(p.text)}>
            <span className="prompt-icon-4">{p.icon}</span> {p.text}
          </div>
        ))}
      </div>
      {selected && (
        <div className="prompt-selected-display-4">
          <strong>Selected:</strong> "{selected}"
        </div>
      )}
    </div>
  );
}
```

---

## Effect #5: Interactive Slash Commands Menu
*Drop-up menu panel that displays system assistant command options matching key inputs.*

### HTML
```html
<div class="command-widget-5">
    <div class="command-menu-5" id="command-menu-5">
        <div class="command-item-5" onclick="selectCommand5('/image')">
            <span class="cmd-icon-5">🖼️</span>
            <div class="cmd-info-5">
                <span class="cmd-name-5">/image</span>
                <span class="cmd-desc-5">Generate a visual design prototype</span>
            </div>
        </div>
        <div class="command-item-5" onclick="selectCommand5('/code')">
            <span class="cmd-icon-5">💻</span>
            <div class="cmd-info-5">
                <span class="cmd-name-5">/code</span>
                <span class="cmd-desc-5">Write complete frontend components</span>
            </div>
        </div>
        <div class="command-item-5" onclick="selectCommand5('/explain')">
            <span class="cmd-icon-5">🤔</span>
            <div class="cmd-info-5">
                <span class="cmd-name-5">/explain</span>
                <span class="cmd-desc-5">Get details about custom algorithms</span>
            </div>
        </div>
    </div>
    <div class="input-container-5">
        <input type="text" class="input-field-5" placeholder="Type / to search commands..." id="input-field-5" onkeyup="checkSlashCommand5(event)">
    </div>
</div>
```

### CSS
```css
.command-widget-5 {
    width: 100%;
    max-width: 400px;
    position: relative;
    display: flex;
    flex-direction: column;
}

.command-menu-5 {
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 10px;
    padding: 6px;
    display: flex;
    flex-direction: column;
    gap: 4px;
    position: absolute;
    bottom: calc(100% + 8px);
    left: 0;
    right: 0;
    box-shadow: 0 10px 25px rgba(0,0,0,0.4);
    opacity: 0;
    transform: translateY(10px);
    pointer-events: none;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: 10;
}

.command-menu-5.active {
    opacity: 1;
    transform: translateY(0);
    pointer-events: auto;
}

.command-item-5 {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 8px 10px;
    border-radius: 6px;
    cursor: pointer;
    transition: background 0.2s;
    text-align: left;
}

.command-item-5:hover {
    background: rgba(99, 102, 241, 0.15);
}

.cmd-icon-5 {
    font-size: 1.1rem;
}

.cmd-info-5 {
    display: flex;
    flex-direction: column;
    gap: 2px;
}

.cmd-name-5 {
    font-size: 0.78rem;
    font-weight: 600;
    color: #ffffff;
}

.cmd-desc-5 {
    font-size: 0.65rem;
    color: #94a3b8;
}

.input-container-5 {
    width: 100%;
}

.input-field-5 {
    width: 100%;
    background: #1f2937;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 8px;
    padding: 10px 14px;
    color: #ffffff;
    font-size: 0.8rem;
    font-family: inherit;
}

.input-field-5:focus {
    outline: none;
    border-color: rgba(99, 102, 241, 0.5);
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.2);
}
```

### JavaScript
```javascript
function checkSlashCommand5(event) {
    const input = event.target;
    const menu = document.getElementById('command-menu-5');
    if (input.value.startsWith('/')) {
        menu.classList.add('active');
    } else {
        menu.classList.remove('active');
    }
}

function selectCommand5(commandName) {
    const input = document.getElementById('input-field-5');
    const menu = document.getElementById('command-menu-5');
    if (input) {
        input.value = commandName + ' ';
        input.focus();
    }
    if (menu) {
        menu.classList.remove('active');
    }
}
```

### React
```tsx
import React, { useState } from 'react';

export function SlashCommandsMenu() {
  const [val, setVal] = useState('');
  const [menuOpen, setMenuOpen] = useState(false);

  const cmds = [
    { name: '/image', icon: '🖼️', desc: 'Generate a visual design prototype' },
    { name: '/code', icon: '💻', desc: 'Write complete frontend components' },
    { name: '/explain', icon: '🤔', desc: 'Get details about custom algorithms' }
  ];

  const handleInput = (e: React.ChangeEvent<HTMLInputElement>) => {
    const value = e.target.value;
    setVal(value);
    setMenuOpen(value.startsWith('/'));
  };

  const selectCmd = (name: string) => {
    setVal(name + ' ');
    setMenuOpen(false);
  };

  return (
    <div className="command-widget-5">
      <div className={`command-menu-5 ${menuOpen ? 'active' : ''}`}>
        {cmds.map((cmd) => (
          <div key={cmd.name} className="command-item-5" onClick={() => selectCmd(cmd.name)}>
            <span className="cmd-icon-5">{cmd.icon}</span>
            <div className="cmd-info-5">
              <span className="cmd-name-5">{cmd.name}</span>
              <span className="cmd-desc-5">{cmd.desc}</span>
            </div>
          </div>
        ))}
      </div>
      <div className="input-container-5">
        <input
          type="text"
          className="input-field-5"
          placeholder="Type / to search commands..."
          value={val}
          onChange={handleInput}
        />
      </div>
    </div>
  );
}
```

---

## Effect #6: Streaming Text Response
*Simulated typewriter response displaying dynamic text segments loaded sequentially.*

### HTML
```html
<div class="stream-container-6">
    <div class="stream-header-6">
        <span class="stream-avatar-6">🤖</span>
        <span class="stream-title-6">Assistant Response</span>
        <button class="stream-replay-6" onclick="replayStream6()">Replay</button>
    </div>
    <div class="stream-body-6" id="stream-body-6">
        <!-- Text stream output container -->
    </div>
</div>
```

### CSS
```css
.stream-container-6 {
    width: 100%;
    max-width: 400px;
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.35);
}

.stream-header-6 {
    padding: 10px 14px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
    background: rgba(0, 0, 0, 0.15);
    display: flex;
    align-items: center;
    gap: 10px;
}

.stream-avatar-6 {
    font-size: 0.9rem;
}

.stream-title-6 {
    font-size: 0.78rem;
    font-weight: 600;
    color: #cbd5e1;
    flex-grow: 1;
    text-align: left;
}

.stream-replay-6 {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.08);
    color: #cbd5e1;
    padding: 4px 10px;
    border-radius: 4px;
    font-size: 0.65rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
}

.stream-replay-6:hover {
    background: rgba(99, 102, 241, 0.15);
    border-color: #6366f1;
    color: #ffffff;
}

.stream-body-6 {
    padding: 14px;
    font-size: 0.78rem;
    color: #e2e8f0;
    line-height: 1.5;
    min-height: 80px;
    text-align: left;
    white-space: pre-wrap;
    font-family: var(--font-mono);
}

.stream-cursor-6 {
    display: inline-block;
    width: 6px;
    height: 12px;
    background-color: #6366f1;
    margin-left: 2px;
    animation: cursor-blink-6 0.8s infinite;
}

@keyframes cursor-blink-6 {
    0%, 100% { opacity: 0; }
    50% { opacity: 1; }
}
```

### JavaScript
```javascript
const sampleText6 = "I've analyzed your component library code.\nFound: 3 duplicate CSS variables.\nReady to refactor modules.";
let streamTimer = null;

function replayStream6() {
    const body = document.getElementById('stream-body-6');
    if (!body) return;
    
    clearInterval(streamTimer);
    body.innerHTML = '<span class="stream-cursor-6"></span>';
    
    let index = 0;
    streamTimer = setInterval(() => {
        if (index < sampleText6.length) {
            // Insert character before cursor
            const textSegment = sampleText6.substring(0, index + 1);
            body.innerHTML = textSegment + '<span class="stream-cursor-6"></span>';
            index++;
        } else {
            // Remove cursor on complete
            body.innerHTML = sampleText6;
            clearInterval(streamTimer);
        }
    }, 45);
}

// Auto start when visible or loaded
setTimeout(replayStream6, 500);
```

### React
```tsx
import React, { useState, useEffect } from 'react';

export function StreamingTextResponse() {
  const textContent = "I've analyzed your component library code.\nFound: 3 duplicate CSS variables.\nReady to refactor modules.";
  const [displayedText, setDisplayedText] = useState('');
  const [complete, setComplete] = useState(false);

  const startStreaming = () => {
    setDisplayedText('');
    setComplete(false);
    let index = 0;
    
    const interval = setInterval(() => {
      if (index < textContent.length) {
        setDisplayedText(textContent.substring(0, index + 1));
        index++;
      } else {
        setComplete(true);
        clearInterval(interval);
      }
    }, 45);

    return () => clearInterval(interval);
  };

  useEffect(() => {
    startStreaming();
  }, []);

  return (
    <div className="stream-container-6">
      <div className="stream-header-6">
        <span className="stream-avatar-6">🤖</span>
        <span className="stream-title-6">Assistant Response</span>
        <button className="stream-replay-6" onClick={startStreaming}>
          Replay
        </button>
      </div>
      <div className="stream-body-6">
        {displayedText}
        {!complete && <span className="stream-cursor-6"></span>}
      </div>
    </div>
  );
}
```

---

## Effect #7: Floating Assistant Toggle
*Floating toggle action button displaying active chat overlays on click triggers.*

### HTML
```html
<div class="assistant-widget-7">
    <div class="assistant-portal-7" id="assistant-portal-7">
        <div class="portal-header-7">
            <span>Helper Bot</span>
            <button class="portal-close-btn-7" onclick="toggleAssistant7()">✕</button>
        </div>
        <div class="portal-body-7">
            How can I help you find custom UI component files?
        </div>
    </div>
    <button class="assistant-toggle-7" id="assistant-toggle-7" onclick="toggleAssistant7()">
        <span class="toggle-icon-7">💬</span>
        <span class="toggle-badge-7">1</span>
    </button>
</div>
```

### CSS
```css
.assistant-widget-7 {
    position: absolute;
    bottom: 15px;
    right: 15px;
    z-index: 100;
}

.assistant-portal-7 {
    position: absolute;
    bottom: 60px;
    right: 0;
    width: 250px;
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.35);
    overflow: hidden;
    transform: scale(0.8) translateY(20px);
    opacity: 0;
    pointer-events: none;
    transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.assistant-portal-7.active {
    transform: scale(1) translateY(0);
    opacity: 1;
    pointer-events: auto;
}

.portal-header-7 {
    background: rgba(0, 0, 0, 0.2);
    padding: 8px 12px;
    font-size: 0.75rem;
    font-weight: 600;
    color: #ffffff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.portal-close-btn-7 {
    background: transparent;
    border: none;
    color: #94a3b8;
    cursor: pointer;
}

.portal-body-7 {
    padding: 12px;
    font-size: 0.72rem;
    color: #cbd5e1;
    text-align: left;
    line-height: 1.4;
}

.assistant-toggle-7 {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%);
    border: none;
    cursor: pointer;
    box-shadow: 0 4px 15px rgba(59, 130, 246, 0.4);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    transition: transform 0.2s;
}

.assistant-toggle-7:hover {
    transform: scale(1.05);
}

.toggle-icon-7 {
    font-size: 1.25rem;
}

.toggle-badge-7 {
    position: absolute;
    top: -2px;
    right: -2px;
    background: #ef4444;
    color: white;
    font-size: 0.55rem;
    font-weight: 700;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid #0d131f;
}
```

### JavaScript
```javascript
function toggleAssistant7() {
    const portal = document.getElementById('assistant-portal-7');
    if (portal) {
        portal.classList.toggle('active');
    }
}
```

### React
```tsx
import React, { useState } from 'react';

export function AssistantToggle() {
  const [isOpen, setIsOpen] = useState(false);
  const [unread, setUnread] = useState(1);

  const toggle = () => {
    setIsOpen(!isOpen);
    setUnread(0);
  };

  return (
    <div className="assistant-widget-7" style={{ position: 'relative' }}>
      <div className={`assistant-portal-7 ${isOpen ? 'active' : ''}`}>
        <div className="portal-header-7">
          <span>Helper Bot</span>
          <button className="portal-close-btn-7" onClick={toggle}>✕</button>
        </div>
        <div className="portal-body-7">
          How can I help you find custom UI component files?
        </div>
      </div>
      <button className="assistant-toggle-7" onClick={toggle}>
        <span className="toggle-icon-7">💬</span>
        {unread > 0 && <span className="toggle-badge-7">{unread}</span>}
      </button>
    </div>
  );
}
```

---

## Effect #8: Rich Input Controller Bar
*Typing input fields enclosing multiple action buttons for file uploads, microphones, and sending text triggers.*

### HTML
```html
<div class="input-bar-8">
    <button class="icon-btn-8" title="Attach file" onclick="showInputTip8('Attachment Clicked')">📎</button>
    <button class="icon-btn-8" title="Voice input" onclick="showInputTip8('Microphone Active')">🎤</button>
    <input class="textarea-8" placeholder="Message assistant..." id="input-8" onkeydown="handleInputEnter8(event)"></input>
    <button class="send-btn-8" onclick="sendInputMessage8()">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
            <line x1="22" y1="2" x2="11" y2="13"></line>
            <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
        </svg>
    </button>
</div>
```

### CSS
```css
.input-bar-8 {
    width: 100%;
    max-width: 440px;
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 24px;
    padding: 6px 8px;
    display: flex;
    align-items: center;
    gap: 6px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
    transition: border-color 0.3s, box-shadow 0.3s;
}

.input-bar-8:focus-within {
    border-color: rgba(99, 102, 241, 0.5);
    box-shadow: 0 0 10px rgba(99, 102, 241, 0.15);
}

.icon-btn-8 {
    background: transparent;
    border: none;
    color: #64748b;
    width: 28px;
    height: 28px;
    border-radius: 50%;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.2s;
    font-size: 0.9rem;
}

.icon-btn-8:hover {
    background: rgba(255, 255, 255, 0.05);
    color: #cbd5e1;
}

.textarea-8 {
    flex-grow: 1;
    background: transparent;
    border: none;
    color: #f8fafc;
    font-size: 0.78rem;
    font-family: inherit;
    padding: 6px 4px;
}

.textarea-8:focus {
    outline: none;
}

.send-btn-8 {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    background: #6366f1;
    color: #ffffff;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.2s;
    flex-shrink: 0;
}

.send-btn-8:hover {
    background: #4f46e5;
    transform: scale(1.05);
}
```

### JavaScript
```javascript
function showInputTip8(text) {
    if (typeof showToast === 'function') {
        showToast(text);
    } else {
        alert(text);
    }
}

function sendInputMessage8() {
    const input = document.getElementById('input-8');
    if (input && input.value.trim()) {
        showInputTip8(`Message Sent: "${input.value}"`);
        input.value = '';
    }
}

function handleInputEnter8(event) {
    if (event.key === 'Enter') {
        sendInputMessage8();
    }
}
```

### React
```tsx
import React, { useState } from 'react';

export function RichInputBar() {
  const [text, setText] = useState('');

  const handleSend = () => {
    if (!text.trim()) return;
    alert(`Message Sent: "${text}"`);
    setText('');
  };

  return (
    <div className="input-bar-8">
      <button className="icon-btn-8" title="Attach file" onClick={() => alert('Attachment Clicked')}>
        📎
      </button>
      <button className="icon-btn-8" title="Voice input" onClick={() => alert('Microphone Active')}>
        🎤
      </button>
      <input
        className="textarea-8"
        placeholder="Message assistant..."
        value={text}
        onChange={(e) => setText(e.target.value)}
        onKeyDown={(e) => e.key === 'Enter' && handleSend()}
      />
      <button className="send-btn-8" onClick={handleSend}>
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
          <line x1="22" y1="2" x2="11" y2="13"></line>
          <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
        </svg>
      </button>
    </div>
  );
}
```
