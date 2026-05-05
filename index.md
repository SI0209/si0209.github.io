---
layout: home
author_profile: true
---

<style>
:root {
  --bg: radial-gradient(circle at top left, #07101f, #0a1121 30%, #020511 100%);
  --panel: rgba(15, 28, 58, 0.82);
  --panel-strong: rgba(20, 35, 70, 0.96);
  --accent: #52c8ff;
  --accent-soft: #8f6dff;
  --text: #e9f4ff;
  --border: rgba(82, 200, 255, 0.22);
}
* { box-sizing: border-box; }
body, .page__body, .home, .page {
  background: var(--bg) !important;
  color: var(--text);
  overflow-x: hidden;
}

/* Animated grid background */
body::before {
  content: "";
  position: fixed;
  inset: 0;
  background-image:
    linear-gradient(rgba(82,200,255,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(82,200,255,0.03) 1px, transparent 1px);
  background-size: 60px 60px;
  animation: gridScroll 40s linear infinite;
  z-index: 0;
  pointer-events: none;
}
@keyframes gridScroll {
  0% { transform: translate(0, 0); }
  100% { transform: translate(60px, 60px); }
}

/* Floating gradient orbs */
.orb-container {
  position: fixed;
  inset: 0;
  overflow: hidden;
  z-index: 0;
  pointer-events: none;
}
.orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.35;
  animation: orbFloat 20s ease-in-out infinite alternate;
}
.orb-1 { width: 400px; height: 400px; background: var(--accent); top: 10%; left: 15%; animation-delay: 0s; }
.orb-2 { width: 320px; height: 320px; background: var(--accent-soft); top: 50%; right: 10%; animation-delay: -7s; }
.orb-3 { width: 280px; height: 280px; background: #ff6bc6; bottom: 5%; left: 40%; animation-delay: -14s; }
@keyframes orbFloat {
  0% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(40px, -30px) scale(1.15); }
  100% { transform: translate(-20px, 20px) scale(0.9); }
}

.page__content,
.page__main,
.page {
  position: relative;
  z-index: 1;
}

.index-hero,
.index-section {
  max-width: 1040px;
  margin: 0 auto;
  padding: 2rem 1rem;
}
.index-hero {
  display: grid;
  gap: 2rem;
}
.hero-card,
.section-card {
  position: relative;
  background: linear-gradient(160deg, rgba(22, 38, 71, 0.72), rgba(9, 16, 31, 0.64));
  border: 1px solid var(--border);
  border-radius: 34px;
  box-shadow:
    0 32px 80px rgba(2, 8, 20, 0.5),
    inset 0 1px 0 rgba(255,255,255,0.06),
    inset 0 -1px 0 rgba(0,0,0,0.2);
  backdrop-filter: blur(24px) saturate(1.3);
  padding: 2rem;
  transform-style: preserve-3d;
  transition: transform 0.35s ease, box-shadow 0.35s ease;
}
.hero-card {
  overflow: hidden;
}
.hero-card::before,
.section-card::before {
  content: "";
  position: absolute;
  top: -40%;
  right: -40%;
  width: 260px;
  height: 260px;
  background: radial-gradient(circle, rgba(82,200,255,0.22), transparent 55%);
  filter: blur(40px);
  pointer-events: none;
}
.hero-card::after,
.section-card::after {
  content: "";
  position: absolute;
  bottom: -30%;
  left: -20%;
  width: 200px;
  height: 200px;
  background: radial-gradient(circle, rgba(143,109,255,0.18), transparent 55%);
  filter: blur(50px);
  pointer-events: none;
}
.hero-card:hover,
.section-card:hover,
.project-card:hover,
.contact-card:hover,
.skill-pill:hover {
  box-shadow:
    0 40px 100px rgba(82, 200, 255, 0.12),
    inset 0 1px 0 rgba(255,255,255,0.1),
    0 0 0 1px rgba(82,200,255,0.15);
}
.hero-card h1,
.hero-card h2,
.section-card h3 {
  margin: 0;
}
.hero-title {
  font-size: clamp(2.8rem, 5vw, 4.5rem);
  line-height: 1.02;
  background: linear-gradient(135deg, #fff 0%, var(--accent) 50%, var(--accent-soft) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-shadow: 0 0 40px rgba(82,200,255,0.15);
}
.hero-subtitle {
  margin-top: 1rem;
  color: #c5d6ff;
  font-size: 1.05rem;
  max-width: 720px;
}
.hero-grid {
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  margin-top: 2rem;
}
.hero-stat {
  padding: 1.25rem;
  border-radius: 24px;
  background: rgba(17, 32, 62, 0.55);
  border: 1px solid rgba(82, 200, 255, 0.12);
  text-align: center;
  backdrop-filter: blur(12px);
  transition: transform 0.25s ease, border-color 0.25s ease;
}
.hero-stat:hover {
  transform: translateY(-4px) scale(1.02);
  border-color: var(--accent);
}
.hero-stat strong {
  display: block;
  font-size: 1.75rem;
  margin-bottom: 0.35rem;
  color: var(--accent);
  text-shadow: 0 0 20px rgba(82,200,255,0.4);
}
.section-card {
  margin-top: 1rem;
}
.section-header {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1.25rem;
}
.section-header .marker {
  width: 0.75rem;
  height: 0.75rem;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--accent), var(--accent-soft));
  box-shadow: 0 0 18px rgba(82, 200, 255, 0.35);
  animation: markerPulse 3s ease-in-out infinite;
}
@keyframes markerPulse {
  0%, 100% { box-shadow: 0 0 18px rgba(82,200,255,0.35); transform: scale(1); }
  50% { box-shadow: 0 0 30px rgba(82,200,255,0.55); transform: scale(1.15); }
}
.card-grid {
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
}
.skill-pill {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.9rem 1.2rem;
  border-radius: 999px;
  background: rgba(10, 20, 40, 0.6);
  border: 1px solid rgba(255, 255, 255, 0.06);
  color: var(--text);
  font-weight: 600;
  backdrop-filter: blur(10px);
  transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease;
  cursor: default;
}
.skill-pill:hover {
  transform: translateY(-4px) scale(1.05);
  border-color: var(--accent);
  box-shadow: 0 8px 30px rgba(82,200,255,0.15), 0 0 0 1px rgba(82,200,255,0.1);
}
.project-card {
  padding: 1.5rem;
  border-radius: 28px;
  background: rgba(14, 26, 54, 0.65);
  border: 1px solid rgba(82, 200, 255, 0.12);
  backdrop-filter: blur(12px);
  transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
}
.project-card:hover {
  transform: translateY(-6px) scale(1.01);
  box-shadow: 0 24px 60px rgba(82, 200, 255, 0.15);
  border-color: rgba(82,200,255,0.25);
}
.project-card h3 {
  margin-bottom: 0.65rem;
  color: #fff;
  text-shadow: 0 0 15px rgba(82,200,255,0.15);
}
.project-card p {
  color: #b9c8ff;
  line-height: 1.7;
}
.contact-grid {
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}
.contact-card {
  padding: 1.4rem;
  border-radius: 28px;
  background: rgba(12, 22, 42, 0.6);
  border: 1px solid rgba(143, 109, 255, 0.14);
  backdrop-filter: blur(14px);
  transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease;
}
.contact-card:hover {
  transform: translateY(-4px) scale(1.02);
  border-color: var(--accent-soft);
  box-shadow: 0 16px 50px rgba(143,109,255,0.15);
}
.contact-card strong {
  color: var(--accent);
  text-shadow: 0 0 12px rgba(82,200,255,0.3);
}
@media (max-width: 680px) {
  .hero-card,
  .section-card {
    transform: none;
  }
}
</style>

<div class="orb-container">
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>
</div>

<div class="index-hero">
  <article class="hero-card">
    <span class="section-header"><span class="marker"></span><strong>Futuristic Portfolio</strong></span>
    <h1 class="hero-title">Hi, I’m Suhail — crafting digital experiences with a modern, 3D-inspired edge.</h1>
    <p class="hero-subtitle">BCom Information Systems graduate and full-stack web developer, building polished systems, eCommerce experiences, and brand-first websites with clean architecture and futuristic visual design.</p>
    <div class="hero-grid">
      <div class="hero-stat"><strong>03+</strong> years of web development experience</div>
      <div class="hero-stat"><strong>05+</strong> commercial and client projects delivered</div>
      <div class="hero-stat"><strong>01</strong> mission: create smarter digital solutions</div>
    </div>
  </article>
</div>

<div class="index-section">
  <section class="section-card">
    <div class="section-header"><span class="marker"></span><strong>Skills</strong></div>
    <div class="card-grid">
      <span class="skill-pill">C#</span>
      <span class="skill-pill">SQL Server</span>
      <span class="skill-pill">ASP.NET Web Forms</span>
      <span class="skill-pill">WordPress</span>
      <span class="skill-pill">HTML &amp; CSS</span>
      <span class="skill-pill">UI / UX Design</span>
    </div>
  </section>

  <section class="section-card">
    <div class="section-header"><span class="marker"></span><strong>Projects</strong></div>
    <div class="card-grid">
      <article class="project-card">
        <h3>Driving School Booking System</h3>
        <p>End-to-end booking and schedule management platform built with .NET C#, ASP.NET, and SQL Server. Designed for efficiency, reliability, and smooth admin control.</p>
      </article>
      <article class="project-card">
        <h3>CampusMart Website</h3>
        <p>A multi-vendor eCommerce marketplace powered by WordPress and WooCommerce, crafted for seamless product discovery and vendor onboarding.</p>
      </article>
      <article class="project-card">
        <h3>SI Digital Technologies</h3>
        <p>Client-facing business website built to elevate digital branding, lead generation, and online credibility with a polished, modern aesthetic.</p>
      </article>
    </div>
  </section>

  <section class="section-card">
    <div class="section-header"><span class="marker"></span><strong>Contact</strong></div>
    <div class="contact-grid">
      <article class="contact-card"><strong>Email</strong><p>suh.ism0209@gmail.com</p></article>
      <article class="contact-card"><strong>Phone</strong><p>+27 66 003 5077</p></article>
      <article class="contact-card"><strong>GitHub</strong><p><a href="https://github.com/SI0209" style="color: #8f6dff; text-decoration: none;">github.com/SI0209</a></p></article>
      <article class="contact-card"><strong>LinkedIn</strong><p><a href="https://www.linkedin.com/in/suhail-ismail-73589b288" style="color: #8f6dff; text-decoration: none;">linkedin.com/in/suhail-ismail-73589b288</a></p></article>
    </div>
  </section>
</div>
