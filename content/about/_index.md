---
title: "About"
date: 2026-02-24T01:39:53+01:00
layout: "single"
---

<style>
.about-card {
    max-width: 720px;
    margin: 0 auto;
    padding: 3rem 2rem;
    text-align: center;
    font-family: 'Courier New', monospace;
}

.about-avatar {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid #00ff41;
    box-shadow: 0 0 30px rgba(0, 255, 65, 0.25), 0 0 60px rgba(0, 255, 65, 0.08);
    margin-bottom: 1.5rem;
    transition: box-shadow 0.3s ease;
}
.about-avatar:hover {
    box-shadow: 0 0 40px rgba(0, 255, 65, 0.5), 0 0 80px rgba(0, 255, 65, 0.15);
}

.about-name {
    font-size: 2rem;
    font-weight: bold;
    color: #00ff41;
    margin-bottom: 0.3rem;
    letter-spacing: 2px;
}

.about-role {
    font-size: 0.9rem;
    color: #555;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 2rem;
}

.about-divider {
    width: 60px;
    height: 2px;
    background: linear-gradient(90deg, transparent, #00ff41, transparent);
    margin: 1.5rem auto;
}

.about-bio {
    color: #aaa;
    font-size: 0.95rem;
    line-height: 1.9;
    text-align: left;
    max-width: 580px;
    margin: 0 auto 2.5rem;
    border-left: 2px solid rgba(0,255,65,0.3);
    padding-left: 1.2rem;
}

.about-bio strong {
    color: #00ff41;
}

.about-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    margin-bottom: 2.5rem;
}

.about-tag {
    background: rgba(0,255,65,0.04);
    border: 1px solid rgba(0,255,65,0.2);
    color: #00ff41;
    padding: 4px 14px;
    border-radius: 3px;
    font-size: 0.78rem;
    letter-spacing: 1px;
}

.about-socials {
    display: flex;
    justify-content: center;
    gap: 1.5rem;
    margin-top: 1rem;
}

.about-social-link {
    display: flex;
    align-items: center;
    gap: 8px;
    color: #888;
    text-decoration: none;
    font-size: 0.9rem;
    letter-spacing: 1px;
    border: 1px solid rgba(255,255,255,0.08);
    padding: 10px 20px;
    border-radius: 4px;
    transition: all 0.3s ease;
    background: rgba(255,255,255,0.02);
}

.about-social-link:hover {
    color: #fff;
    border-color: rgba(255,255,255,0.3);
    background: rgba(255,255,255,0.05);
    text-decoration: none;
}

.about-social-link svg {
    flex-shrink: 0;
}
</style>

<div class="about-card">

  <img class="about-avatar" src="https://github.com/st0rmESP.png" alt="st0rmESP" />

  <div class="about-name">st0rmESP</div>
  <div class="about-role">// Cybersecurity Enthusiast & CTF Player</div>

  <div class="about-divider"></div>

  <div class="about-bio">
    Apasionado de la <strong>ciberseguridad ofensiva</strong>, el hacking ético y la resolución de retos. Activo en plataformas como <strong>HackTheBox</strong> y <strong>TryHackMe</strong>, donde disfruto resolviendo máquinas, challenges y prolabs.
    <br><br>
    En este blog comparto <strong>write-ups detallados</strong>, técnicas de pentesting, herramientas y todo lo que aprendo en el camino —porque el conocimiento compartido es el que más crece.
    <br><br>
    <em style="color: #555;">"The quieter you become, the more you are able to hear."</em>
  </div>

  <div class="about-tags">
    <span class="about-tag">PENTESTING</span>
    <span class="about-tag">CTF</span>
    <span class="about-tag">RED TEAM</span>
    <span class="about-tag">HACKTHEBOX</span>
    <span class="about-tag">TRYHACKME</span>
    <span class="about-tag">LINUX</span>
    <span class="about-tag">PYTHON</span>
  </div>

  <div class="about-socials">
    <!-- GitHub -->
    <a class="about-social-link" href="https://github.com/st0rmESP" target="_blank" rel="noopener">
      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/>
      </svg>
      GITHUB
    </a>
    <!-- LinkedIn -->
    <a class="about-social-link" href="https://www.linkedin.com/in/st0rmESP" target="_blank" rel="noopener">
      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
        <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
      </svg>
      LINKEDIN
    </a>
  </div>

</div>
