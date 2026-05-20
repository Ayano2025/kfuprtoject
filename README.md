# kfuprtoject

index.html
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap');
 
/* ═══════════════════════════════════════
   CSS VARIABLES — LIGHT THEME
═══════════════════════════════════════ */
:root {
  --bg:         #FFF8D0;
  --bg-card:    #FFFFFF;
  --bg-msg-in:  #FFFFFF;
  --bg-msg-out: #E84040;
  --accent:     #E84040;
  --accent-soft:#FF7A70;
  --yellow:     #FFF8D0;
  --border-col: #1A1410;
  --shadow-col: #1A1410;
  --text:       #1A1410;
  --text-muted: #5A4A40;
  --text-inv:   #FFFFFF;
  --border:     3.5px solid #1A1410;
  --shadow:     5px 5px 0px #1A1410;
  --shadow-sm:  3px 3px 0px #1A1410;
  --shadow-lg:  8px 8px 0px #1A1410;
  --radius:     2px;
  --input-bg:   #FFFFFF;
  --header-bg:  #FFF8D0;
  --nav-bg:     #FFFFFF;
  --transition: 0.22s cubic-bezier(0.4, 0, 0.2, 1);
}
 
[data-theme="dark"] {
  --bg:         #08080F;
  --bg-card:    #0B1929;
  --bg-msg-in:  #0B1929;
  --bg-msg-out: #B83030;
  --accent:     #FF5349;
  --accent-soft:#FF7A70;
  --yellow:     #1A1A2E;
  --border-col: #1E3A5F;
  --shadow-col: #0D2B50;
  --text:       #E8EAF0;
  --text-muted: #7A8BAA;
  --text-inv:   #FFFFFF;
  --border:     3.5px solid #1E3A5F;
  --shadow:     5px 5px 0px #0D2B50;
  --shadow-sm:  3px 3px 0px #0D2B50;
  --shadow-lg:  8px 8px 0px #0D2B50;
  --input-bg:   #0F2035;
  --header-bg:  #06060D;
  --nav-bg:     #0B1929;
}
 
/* ═══════════════════════════════════════
   RESET & BASE
═══════════════════════════════════════ */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
 
html {
  font-size: 16px;
  scroll-behavior: smooth;
}
 
body {
  font-family: 'Space Mono', monospace;
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  transition: background var(--transition), color var(--transition);
  overflow-x: hidden;
}
 
a { text-decoration: none; color: inherit; }
 
/* ═══════════════════════════════════════
   PAGE TRANSITION OVERLAY
═══════════════════════════════════════ */
.page-overlay {
  position: fixed;
  inset: 0;
  background: var(--accent);
  z-index: 9999;
  pointer-events: none;
  transform: translateX(-100%);
  transition: transform 0.4s cubic-bezier(0.77, 0, 0.175, 1);
}
 
.page-overlay.slide-in  { transform: translateX(0%); }
.page-overlay.slide-out { transform: translateX(100%); }
 
/* ═══════════════════════════════════════
   HEADER
═══════════════════════════════════════ */
.header {
  background: var(--header-bg);
  border-bottom: var(--border);
  padding: 0 28px;
  height: 64px;
  display: flex;
  align-items: center;
  gap: 16px;
  position: sticky;
  top: 0;
  z-index: 100;
  transition: background var(--transition);
}
 
.header-logo {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 26px;
  letter-spacing: 2px;
  color: var(--accent);
  border: var(--border);
  box-shadow: var(--shadow-sm);
  padding: 2px 10px;
  background: var(--bg-card);
  transition: box-shadow var(--transition), transform var(--transition);
  user-select: none;
}
 
.header-logo:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow);
}
 
.header-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 22px;
  letter-spacing: 3px;
  flex: 1;
  color: var(--text);
}
 
.header-back {
  display: flex;
  align-items: center;
  gap: 8px;
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  font-weight: 700;
  border: var(--border);
  box-shadow: var(--shadow-sm);
  background: var(--bg-card);
  color: var(--text);
  padding: 6px 14px;
  cursor: pointer;
  transition: transform var(--transition), box-shadow var(--transition);
  text-transform: uppercase;
  letter-spacing: 1px;
}
 
.header-back:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow);
}
 
.header-back:active {
  transform: translate(2px, 2px);
  box-shadow: none;
}
 
/* Theme Toggle */
.theme-toggle {
  border: var(--border);
  box-shadow: var(--shadow-sm);
  background: var(--bg-card);
  color: var(--text);
  width: 40px;
  height: 40px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  transition: transform var(--transition), box-shadow var(--transition), background var(--transition);
  flex-shrink: 0;
}
 
.theme-toggle:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow);
}
 
.theme-toggle:active {
  transform: translate(2px, 2px);
  box-shadow: none;
}
 
/* ═══════════════════════════════════════
   INDEX PAGE — MAIN LANDING
═══════════════════════════════════════ */
.landing {
  min-height: calc(100vh - 64px);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 40px 24px;
  gap: 48px;
}
 
.landing-hero {
  text-align: center;
}
 
.landing-hero h2 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(48px, 10vw, 110px);
  letter-spacing: 4px;
  line-height: 0.92;
  color: var(--text);
  -webkit-text-stroke: 1px var(--text);
}
 
.landing-hero h2 .highlight {
  color: var(--accent);
  -webkit-text-stroke: 1px var(--accent);
  display: block;
}
 
.landing-hero p {
  font-size: 13px;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--text-muted);
  margin-top: 16px;
}
 
.landing-nav {
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
  justify-content: center;
}
 
/* ═══════════════════════════════════════
   BIG NAV BUTTONS
═══════════════════════════════════════ */
.big-btn {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
  width: 220px;
  height: 220px;
  border: var(--border);
  box-shadow: var(--shadow-lg);
  background: var(--bg-card);
  color: var(--text);
  cursor: pointer;
  transition: transform var(--transition), box-shadow var(--transition), background var(--transition);
  position: relative;
  overflow: hidden;
}
 
.big-btn::before {
  content: '';
  position: absolute;
  inset: 0;
  background: var(--accent);
  transform: translateY(100%);
  transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1);
  z-index: 0;
}
 
.big-btn:hover::before { transform: translateY(0%); }
 
.big-btn:hover {
  color: #FFFFFF;
  transform: translate(-4px, -4px);
  box-shadow: var(--shadow-lg);
}
 
.big-btn:active {
  transform: translate(3px, 3px);
  box-shadow: 2px 2px 0px var(--shadow-col);
}
 
.big-btn .btn-icon {
  font-size: 52px;
  position: relative;
  z-index: 1;
  transition: transform var(--transition);
}
 
.big-btn:hover .btn-icon { transform: scale(1.15) rotate(-5deg); }
 
.big-btn .btn-label {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 26px;
  letter-spacing: 3px;
  position: relative;
  z-index: 1;
}
 
/* ═══════════════════════════════════════
   SUBJECTS PAGE
═══════════════════════════════════════ */
.subjects-page {
  min-height: calc(100vh - 64px);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 48px 24px;
  gap: 40px;
}
 
.section-label {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 13px;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: var(--text-muted);
  border-bottom: 2px solid var(--accent);
  padding-bottom: 6px;
}
 
.subjects-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(40px, 8vw, 80px);
  letter-spacing: 3px;
  text-align: center;
  color: var(--text);
}
 
.subjects-grid {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  justify-content: center;
}
 
.subject-btn {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  width: 180px;
  height: 180px;
  border: var(--border);
  box-shadow: var(--shadow);
  background: var(--bg-card);
  cursor: pointer;
  transition: transform var(--transition), box-shadow var(--transition), background var(--transition);
  position: relative;
  overflow: hidden;
}
 
.subject-btn::before {
  content: '';
  position: absolute;
  inset: 0;
  z-index: 0;
  transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1);
  transform: translateX(-100%);
}
 
.subject-btn--practices::before  { background: #FF8C69; }
.subject-btn--lectures::before   { background: #E84040; }
.subject-btn--homework::before   { background: #FFD700; }
 
.subject-btn:hover::before { transform: translateX(0%); }
 
.subject-btn:hover {
  transform: translate(-3px, -3px);
  box-shadow: var(--shadow-lg);
}
 
.subject-btn:hover .sub-label { color: #1A1410; }
 
.subject-btn:active {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0px var(--shadow-col);
}
 
.sub-icon {
  font-size: 44px;
  position: relative;
  z-index: 1;
}
 
.sub-label {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 22px;
  letter-spacing: 2px;
  position: relative;
  z-index: 1;
  color: var(--text);
  transition: color var(--transition);
}
 
/* ═══════════════════════════════════════
   CHAT PAGE
═══════════════════════════════════════ */
.chat-page {
  display: flex;
  flex-direction: column;
  height: calc(100vh - 64px);
}
 
.chat-title-bar {
  border-bottom: var(--border);
  padding: 14px 28px;
  display: flex;
  align-items: center;
  gap: 16px;
  background: var(--nav-bg);
  flex-shrink: 0;
  transition: background var(--transition);
}
 
.chat-section-name {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 30px;
  letter-spacing: 3px;
  color: var(--accent);
}
 
.chat-count {
  font-size: 11px;
  color: var(--text-muted);
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-left: auto;
}
 
/* Messages Area */
.chat-messages {
  flex: 1;
  overflow-y: auto;
  padding: 24px 20px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  scrollbar-width: thin;
  scrollbar-color: var(--accent) transparent;
}
 
.chat-messages::-webkit-scrollbar { width: 6px; }
.chat-messages::-webkit-scrollbar-track { background: transparent; }
.chat-messages::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 0; }
 
/* Message Bubbles */
.msg-wrapper {
  display: flex;
  flex-direction: column;
  max-width: 72%;
  animation: msgSlideIn 0.28s cubic-bezier(0.4, 0, 0.2, 1) both;
}
 
@keyframes msgSlideIn {
  from { opacity: 0; transform: translateY(14px); }
  to   { opacity: 1; transform: translateY(0); }
}
 
.msg-wrapper.own {
  align-self: flex-end;
  align-items: flex-end;
}
 
.msg-bubble {
  border: var(--border);
  box-shadow: var(--shadow-sm);
  padding: 12px 16px;
  background: var(--bg-msg-in);
  color: var(--text);
  font-family: 'Space Mono', monospace;
  font-size: 13px;
  line-height: 1.55;
  max-width: 100%;
  transition: background var(--transition), border-color var(--transition);
  word-break: break-word;
}
 
.msg-wrapper.own .msg-bubble {
  background: var(--bg-msg-out);
  color: #FFFFFF;
}
 
.msg-time {
  font-size: 10px;
  color: var(--text-muted);
  letter-spacing: 1px;
  margin-top: 4px;
  padding: 0 2px;
}
 
/* Image Message */
.msg-image {
  max-width: 280px;
  max-height: 240px;
  object-fit: cover;
  display: block;
  border: var(--border);
  box-shadow: var(--shadow-sm);
  cursor: pointer;
  transition: transform var(--transition);
}
 
.msg-image:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow);
}
 
/* File Message */
.msg-file {
  display: flex;
  align-items: center;
  gap: 12px;
  border: var(--border);
  box-shadow: var(--shadow-sm);
  padding: 12px 16px;
  background: var(--bg-msg-in);
  cursor: pointer;
  transition: transform var(--transition), box-shadow var(--transition);
}
 
.msg-file:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow);
}
 
.msg-wrapper.own .msg-file {
  background: var(--bg-msg-out);
  color: #FFFFFF;
}
 
.msg-file-icon {
  font-size: 28px;
  flex-shrink: 0;
}
 
.msg-file-info { display: flex; flex-direction: column; gap: 2px; }
.msg-file-name {
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.5px;
  word-break: break-all;
}
 
.msg-file-size { font-size: 10px; color: var(--text-muted); }
.msg-wrapper.own .msg-file-size { color: rgba(255,255,255,0.65); }
 
/* System / date divider */
.msg-divider {
  display: flex;
  align-items: center;
  gap: 12px;
  color: var(--text-muted);
  font-size: 11px;
  letter-spacing: 2px;
  text-transform: uppercase;
}
 
.msg-divider::before,
.msg-divider::after {
  content: '';
  flex: 1;
  height: 1.5px;
  background: var(--border-col);
  opacity: 0.25;
}
 
/* Empty state */
.chat-empty {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
  color: var(--text-muted);
  pointer-events: none;
}
 
.chat-empty-icon { font-size: 60px; opacity: 0.3; }
.chat-empty-text {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 22px;
  letter-spacing: 3px;
  opacity: 0.4;
}
 
/* ═══════════════════════════════════════
   INPUT BAR
═══════════════════════════════════════ */
.chat-input-area {
  border-top: var(--border);
  padding: 14px 16px;
  display: flex;
  align-items: flex-end;
  gap: 10px;
  background: var(--nav-bg);
  flex-shrink: 0;
  transition: background var(--transition);
}
 
.attach-btn {
  border: var(--border);
  box-shadow: var(--shadow-sm);
  background: var(--bg-card);
  color: var(--text);
  width: 44px;
  height: 44px;
  flex-shrink: 0;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  transition: transform var(--transition), box-shadow var(--transition), background var(--transition);
  position: relative;
}
 
.attach-btn:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow);
  background: var(--accent);
  color: #fff;
  border-color: var(--accent);
}
 
.attach-btn:active {
  transform: translate(2px, 2px);
  box-shadow: none;
}
 
#fileInput { display: none; }
 
.input-wrapper {
  flex: 1;
  position: relative;
}
 
.chat-textarea {
  width: 100%;
  border: var(--border);
  box-shadow: var(--shadow-sm);
  background: var(--input-bg);
  color: var(--text);
  font-family: 'Space Mono', monospace;
  font-size: 13px;
  padding: 12px 16px;
  resize: none;
  min-height: 44px;
  max-height: 150px;
  line-height: 1.5;
  outline: none;
  transition: box-shadow var(--transition), background var(--transition);
}
 
.chat-textarea::placeholder { color: var(--text-muted); }
 
.chat-textarea:focus {
  box-shadow: var(--shadow);
  outline: none;
}
 
.send-btn {
  border: var(--border);
  box-shadow: var(--shadow-sm);
  background: var(--accent);
  color: #FFFFFF;
  width: 44px;
  height: 44px;
  flex-shrink: 0;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  transition: transform var(--transition), box-shadow var(--transition);
}
 
.send-btn:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow);
  background: var(--accent-soft);
}
 
.send-btn:active {
  transform: translate(2px, 2px);
  box-shadow: none;
}
 
.send-btn:disabled {
  opacity: 0.4;
  cursor: default;
  transform: none;
  box-shadow: var(--shadow-sm);
}
 
/* File preview chip */
.file-preview-area {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  padding: 0 16px 10px;
  background: var(--nav-bg);
  border-top: 1px solid rgba(128,128,128,0.1);
  transition: background var(--transition);
}
 
.file-chip {
  display: flex;
  align-items: center;
  gap: 8px;
  border: var(--border);
  box-shadow: var(--shadow-sm);
  background: var(--bg-card);
  padding: 6px 12px;
  font-size: 11px;
  font-family: 'Space Mono', monospace;
  color: var(--text);
  max-width: 200px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  animation: chipIn 0.2s ease both;
}
 
@keyframes chipIn {
  from { opacity: 0; transform: scale(0.9); }
  to   { opacity: 1; transform: scale(1); }
}
 
.chip-name { flex: 1; overflow: hidden; text-overflow: ellipsis; }
 
.chip-remove {
  cursor: pointer;
  color: var(--accent);
  font-size: 14px;
  font-weight: 700;
  flex-shrink: 0;
  transition: transform var(--transition);
}
 
.chip-remove:hover { transform: scale(1.3); }
 
/* Image lightbox */
.lightbox {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.88);
  z-index: 9000;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: zoom-out;
  animation: fadeIn 0.2s ease;
}
 
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}
 
.lightbox img {
  max-width: 90vw;
  max-height: 90vh;
  object-fit: contain;
  border: 3px solid #fff;
  box-shadow: 0 0 60px rgba(232,64,64,0.5);
}
 
/* ═══════════════════════════════════════
   DECORATIVE TAPE ELEMENTS (brutalist)
═══════════════════════════════════════ */
.tape {
  display: inline-block;
  background: var(--accent);
  color: #fff;
  font-family: 'Bebas Neue', sans-serif;
  font-size: 12px;
  letter-spacing: 3px;
  padding: 2px 16px;
  transform: rotate(-1.5deg);
  user-select: none;
  opacity: 0.85;
}
 
/* Noise texture overlay */
body::after {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 9998;
  opacity: 0.5;
}
 
/* ═══════════════════════════════════════
   SCROLLBAR GLOBAL
═══════════════════════════════════════ */
* {
  scrollbar-width: thin;
  scrollbar-color: var(--accent) transparent;
}
 
/* ═══════════════════════════════════════
   RESPONSIVE
═══════════════════════════════════════ */
@media (max-width: 600px) {
  .header { padding: 0 14px; }
  .header-title { font-size: 16px; }
  .landing-hero h2 { font-size: 52px; }
  .big-btn { width: 160px; height: 160px; }
  .big-btn .btn-icon { font-size: 38px; }
  .big-btn .btn-label { font-size: 20px; }
  .subject-btn { width: 140px; height: 140px; }
  .msg-wrapper { max-width: 88%; }
  .chat-title-bar { padding: 10px 16px; }
  .chat-messages { padding: 16px 12px; }
}
 /* app.js — shared logic for all pages */
 
// ═══════════════════════════════════════
//  THEME
// ═══════════════════════════════════════
(function initTheme() {
  const stored = localStorage.getItem('pu-theme') || 'light';
  document.documentElement.setAttribute('data-theme', stored);
})();
 
function toggleTheme() {
  const current = document.documentElement.getAttribute('data-theme') || 'light';
  const next = current === 'light' ? 'dark' : 'light';
  document.documentElement.setAttribute('data-theme', next);
  localStorage.setItem('pu-theme', next);
  const btn = document.getElementById('themeToggle');
  if (btn) btn.textContent = next === 'dark' ? '☀️' : '🌙';
}
 
function updateThemeIcon() {
  const btn = document.getElementById('themeToggle');
  if (!btn) return;
  const current = document.documentElement.getAttribute('data-theme') || 'light';
  btn.textContent = current === 'dark' ? '☀️' : '🌙';
}
 
// ═══════════════════════════════════════
//  PAGE TRANSITIONS
// ═══════════════════════════════════════
function navigateTo(url) {
  const overlay = document.querySelector('.page-overlay');
  if (!overlay) { window.location.href = url; return; }
 
  overlay.classList.remove('slide-out');
  overlay.classList.add('slide-in');
 
  setTimeout(() => {
    window.location.href = url;
  }, 380);
}
 
// On page load — slide out the overlay
window.addEventListener('DOMContentLoaded', () => {
  updateThemeIcon();
 
  const overlay = document.querySelector('.page-overlay');
  if (overlay) {
    overlay.classList.add('slide-in');
    requestAnimationFrame(() => {
      requestAnimationFrame(() => {
        overlay.classList.remove('slide-in');
        overlay.classList.add('slide-out');
      });
    });
  }
 
  // Intercept all nav links that use data-navigate
  document.querySelectorAll('[data-navigate]').forEach(el => {
    el.addEventListener('click', e => {
      e.preventDefault();
      navigateTo(el.getAttribute('data-navigate') || el.href);
    });
  });
});
 
// ═══════════════════════════════════════
//  CHAT ENGINE
// ═══════════════════════════════════════
 
// Section names
const SECTION_NAMES = {
  practices: 'ПРАКТИКИ',
  lectures:  'ЛЕКЦИИ',
  homework:  'ДОМАШКИ',
  credits:   'ЗАЧЕТЫ',
};
 
const SECTION_ICONS = {
  practices: '🔬',
  lectures:  '📖',
  homework:  '✏️',
  credits:   '✅',
};
 
function getSection() {
  const params = new URLSearchParams(window.location.search);
  return params.get('section') || 'lectures';
}
 
function getStorageKey(section) {
  return `pu-messages-${section}`;
}
 
function loadMessages(section) {
  try {
    const raw = localStorage.getItem(getStorageKey(section));
    return raw ? JSON.parse(raw) : [];
  } catch { return []; }
}
 
function saveMessages(section, messages) {
  try {
    localStorage.setItem(getStorageKey(section), JSON.stringify(messages));
  } catch (e) {
    if (e.name === 'QuotaExceededError') {
      alert('Хранилище заполнено. Удалите старые сообщения чтобы продолжить.');
    }
  }
}
 
function formatTime(ts) {
  const d = new Date(ts);
  return d.toLocaleTimeString('ru-RU', { hour: '2-digit', minute: '2-digit' });
}
 
function formatDate(ts) {
  const d = new Date(ts);
  return d.toLocaleDateString('ru-RU', { day: 'numeric', month: 'long' });
}
 
function getFileIcon(filename) {
  const ext = filename.split('.').pop().toLowerCase();
  const icons = {
    pdf: '📄', doc: '📝', docx: '📝', txt: '📃',
    xls: '📊', xlsx: '📊', csv: '📊',
    ppt: '📊', pptx: '📊',
    zip: '🗜️', rar: '🗜️', '7z': '🗜️',
    mp3: '🎵', wav: '🎵', ogg: '🎵',
    mp4: '🎬', avi: '🎬', mov: '🎬',
    js: '💻', ts: '💻', py: '💻', java: '💻', cpp: '💻',
    html: '🌐', css: '🎨',
    png: '🖼️', jpg: '🖼️', jpeg: '🖼️', gif: '🖼️', webp: '🖼️', svg: '🖼️',
  };
  return icons[ext] || '📎';
}
 
function formatSize(bytes) {
  if (bytes < 1024) return bytes + ' Б';
  if (bytes < 1024 * 1024) return (bytes / 1024).toFixed(1) + ' КБ';
  return (bytes / 1024 / 1024).toFixed(1) + ' МБ';
}
 
function buildMessageEl(msg) {
  const wrapper = document.createElement('div');
  wrapper.className = 'msg-wrapper own';
  wrapper.dataset.id = msg.id;
 
  let inner = '';
 
  if (msg.type === 'text') {
    const escaped = msg.content
      .replace(/&/g, '&amp;')
      .replace(/</g, '&lt;')
      .replace(/>/g, '&gt;')
      .replace(/\n/g, '<br>');
    inner = `<div class="msg-bubble">${escaped}</div>`;
  } else if (msg.type === 'image') {
    inner = `<img class="msg-image" src="${msg.content}" alt="${msg.filename || 'image'}"
               title="Нажмите для просмотра" onclick="openLightbox('${msg.id}')">`;
  } else if (msg.type === 'file') {
    const icon = getFileIcon(msg.filename);
    inner = `<div class="msg-file" onclick="downloadFile('${msg.id}')">
      <span class="msg-file-icon">${icon}</span>
      <div class="msg-file-info">
        <div class="msg-file-name">${msg.filename}</div>
        <div class="msg-file-size">${msg.size ? formatSize(msg.size) : ''}</div>
      </div>
    </div>`;
  }
 
  inner += `<div class="msg-time">${formatTime(msg.ts)}</div>`;
  wrapper.innerHTML = inner;
  return wrapper;
}
 
// Global messages store for the current session
let _messages = [];
let _section = '';
 
function renderMessages() {
  const container = document.getElementById('chatMessages');
  if (!container) return;
 
  container.innerHTML = '';
 
  if (_messages.length === 0) {
    const empty = document.createElement('div');
    empty.className = 'chat-empty';
    empty.innerHTML = `<div class="chat-empty-icon">💬</div>
      <div class="chat-empty-text">ПОКА ПУСТО</div>`;
    container.appendChild(empty);
    return;
  }
 
  let lastDate = null;
  _messages.forEach(msg => {
    const dateStr = formatDate(msg.ts);
    if (dateStr !== lastDate) {
      const divider = document.createElement('div');
      divider.className = 'msg-divider';
      divider.textContent = dateStr;
      container.appendChild(divider);
      lastDate = dateStr;
    }
    container.appendChild(buildMessageEl(msg));
  });
 
  container.scrollTop = container.scrollHeight;
  updateCount();
}
 
function updateCount() {
  const el = document.getElementById('msgCount');
  if (el) el.textContent = `${_messages.length} запис.`;
}
 
function sendMessage(type, content, filename, size) {
  const msg = {
    id: 'msg_' + Date.now() + '_' + Math.random().toString(36).slice(2, 7),
    type,
    content,
    filename: filename || null,
    size: size || null,
    ts: Date.now(),
  };
  _messages.push(msg);
  saveMessages(_section, _messages);
 
  const container = document.getElementById('chatMessages');
  if (!container) return;
 
  // Remove empty state if present
  const empty = container.querySelector('.chat-empty');
  if (empty) empty.remove();
 
  // Add date divider if needed
  if (_messages.length === 1) {
    const divider = document.createElement('div');
    divider.className = 'msg-divider';
    divider.textContent = formatDate(msg.ts);
    container.appendChild(divider);
  } else {
    const prev = _messages[_messages.length - 2];
    if (formatDate(prev.ts) !== formatDate(msg.ts)) {
      const divider = document.createElement('div');
      divider.className = 'msg-divider';
      divider.textContent = formatDate(msg.ts);
      container.appendChild(divider);
    }
  }
 
  const el = buildMessageEl(msg);
  container.appendChild(el);
  container.scrollTop = container.scrollHeight;
  updateCount();
}
 
// ═══════════════════════════════════════
//  LIGHTBOX
// ═══════════════════════════════════════
function openLightbox(msgId) {
  const msg = _messages.find(m => m.id === msgId);
  if (!msg || msg.type !== 'image') return;
 
  const lb = document.createElement('div');
  lb.className = 'lightbox';
  lb.innerHTML = `<img src="${msg.content}" alt="${msg.filename || 'image'}">`;
  lb.addEventListener('click', () => lb.remove());
  document.body.appendChild(lb);
}
 
// ═══════════════════════════════════════
//  FILE DOWNLOAD
// ═══════════════════════════════════════
function downloadFile(msgId) {
  const msg = _messages.find(m => m.id === msgId);
  if (!msg || msg.type !== 'file') return;
  const a = document.createElement('a');
  a.href = msg.content;
  a.download = msg.filename || 'file';
  a.click();
}
 
// ═══════════════════════════════════════
//  INIT CHAT PAGE
// ═══════════════════════════════════════
function initChat() {
  _section = getSection();
  _messages = loadMessages(_section);
 
  // Set title
  const titleEl = document.getElementById('chatSectionName');
  if (titleEl) {
    titleEl.textContent = SECTION_NAMES[_section] || _section.toUpperCase();
  }
  const iconEl = document.getElementById('chatSectionIcon');
  if (iconEl) {
    iconEl.textContent = SECTION_ICONS[_section] || '💬';
  }
 
  renderMessages();
 
  // Text input
  const textarea = document.getElementById('chatInput');
  const sendBtn = document.getElementById('sendBtn');
  const fileInput = document.getElementById('fileInput');
  const attachBtn = document.getElementById('attachBtn');
  const filePreviewArea = document.getElementById('filePreviewArea');
 
  let pendingFiles = []; // {file, dataURL, type}
 
  if (textarea) {
    textarea.addEventListener('input', () => {
      // Auto-resize
      textarea.style.height = 'auto';
      textarea.style.height = Math.min(textarea.scrollHeight, 150) + 'px';
      updateSendBtn();
    });
    textarea.addEventListener('keydown', e => {
      if (e.key === 'Enter' && !e.shiftKey) {
        e.preventDefault();
        doSend();
      }
    });
  }
 
  if (sendBtn) {
    sendBtn.addEventListener('click', doSend);
  }
 
  if (attachBtn && fileInput) {
    attachBtn.addEventListener('click', () => fileInput.click());
    fileInput.addEventListener('change', async () => {
      const files = Array.from(fileInput.files);
      for (const file of files) {
        await addPendingFile(file);
      }
      fileInput.value = '';
      renderPendingFiles();
      updateSendBtn();
    });
  }
 
  function updateSendBtn() {
    if (!sendBtn) return;
    const hasText = textarea && textarea.value.trim().length > 0;
    const hasFiles = pendingFiles.length > 0;
    sendBtn.disabled = !hasText && !hasFiles;
  }
 
  async function addPendingFile(file) {
    // Warn if > 4MB
    if (file.size > 4 * 1024 * 1024) {
      const ok = confirm(`Файл "${file.name}" занимает ${formatSize(file.size)}. Очень большие файлы могут не сохраниться. Продолжить?`);
      if (!ok) return;
    }
    const dataURL = await readFileAsDataURL(file);
    const isImage = file.type.startsWith('image/');
    pendingFiles.push({ file, dataURL, isImage });
  }
 
  function readFileAsDataURL(file) {
    return new Promise((resolve, reject) => {
      const reader = new FileReader();
      reader.onload = e => resolve(e.target.result);
      reader.onerror = () => reject(new Error('Ошибка чтения файла'));
      reader.readAsDataURL(file);
    });
  }
 
  function renderPendingFiles() {
    if (!filePreviewArea) return;
    filePreviewArea.innerHTML = '';
    pendingFiles.forEach((pf, i) => {
      const chip = document.createElement('div');
      chip.className = 'file-chip';
      chip.innerHTML = `
        <span>${getFileIcon(pf.file.name)}</span>
        <span class="chip-name" title="${pf.file.name}">${pf.file.name}</span>
        <span class="chip-remove" data-i="${i}" title="Удалить">✕</span>
      `;
      chip.querySelector('.chip-remove').addEventListener('click', () => {
        pendingFiles.splice(i, 1);
        renderPendingFiles();
        updateSendBtn();
      });
      filePreviewArea.appendChild(chip);
    });
  }
 
  function doSend() {
    const text = textarea ? textarea.value.trim() : '';
 
    // Send pending files first
    pendingFiles.forEach(pf => {
      if (pf.isImage) {
        sendMessage('image', pf.dataURL, pf.file.name, pf.file.size);
      } else {
        sendMessage('file', pf.dataURL, pf.file.name, pf.file.size);
      }
    });
    pendingFiles = [];
    renderPendingFiles();
 
    // Send text
    if (text) {
      sendMessage('text', text, null, null);
      textarea.value = '';
      textarea.style.height = 'auto';
    }
 
    updateSendBtn();
  }
 
  updateSendBtn();
}
 
// Start chat when DOM ready
document.addEventListener('DOMContentLoaded', () => {
  if (document.getElementById('chatMessages')) {
    initChat();
  }
});
 
