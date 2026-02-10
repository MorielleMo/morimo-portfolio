<template>
  <footer class="footer">

    <div class="footer-content">

      <!-- BRAND -->
      <div class="brand">
        <h3>MoriMo</h3>
        <p>UX/UI & Web Designer — Creating meaningful digital experiences ✨</p>
      </div>

      <!-- NAV -->
      <nav class="footer-nav">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#works">Works</a>
        <a href="#skills">Skills</a>
        <a href="#contact">Contact</a>
      </nav>

      <!-- SOCIAL -->
      <div class="social">
        <p>Let’s connect 💜</p>
        <a
          href="https://www.instagram.com/moriellemoke/"
          target="_blank"
          rel="noopener"
        >
          Instagram
        </a>
      </div>

    </div>

    <!-- BOTTOM -->
    <div class="footer-bottom">
      © {{ year }} MoriMo — All rights reserved
    </div>

  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>

<style scoped>
.footer {
  background: #5b2d91;
  color: #F3EDE5;
  padding: 60px 40px 30px;
}

/* CONTENT */

.footer-content {
  max-width: 1100px;
  margin: auto;

  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr;
  gap: 40px;
}

/* BRAND */

.brand h3 {
  font-size: 1.8rem;
  margin-bottom: 10px;
}

.brand p {
  font-size: 0.9rem;
  opacity: 0.85;
}

/* NAV */

.footer-nav {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.footer-nav a {
  color: #F3EDE5;
  text-decoration: none;
  font-size: 0.9rem;
  transition: opacity 0.2s ease;
}

.footer-nav a:hover {
  opacity: 0.7;
}

/* SOCIAL */

.social p {
  margin-bottom: 10px;
  font-size: 0.9rem;
}

.social a {
  color: #F3EDE5;
  text-decoration: none;
  font-weight: 600;
  background: rgba(255,255,255,0.15);
  padding: 8px 16px;
  border-radius: 999px;
  display: inline-block;
  transition: background 0.2s ease, transform 0.2s ease;
}

.social a:hover {
  background: rgba(255,255,255,0.25);
  transform: translateY(-2px);
}

/* BOTTOM */

.footer-bottom {
  text-align: center;
  margin-top: 40px;
  font-size: 0.75rem;
  opacity: 0.7;
}

/* MOBILE */

@media (max-width: 900px) {
  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .footer-nav {
    align-items: center;
  }
}
</style>
