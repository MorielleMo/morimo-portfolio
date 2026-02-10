<template>
  <footer class="footer">

    <div class="footer-content">

      <!-- BRAND -->
      <div class="brand">
        <img :src="logo" alt="MoriMo logo" class="footer-logo" />
        <p class="tagline">
          UX/UI & Web Designer<br />
          Creating meaningful digital experiences ✨
        </p>
      </div>

      <!-- NAV -->
      <nav class="footer-nav">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#brand">Brand</a>
        <a href="#works">Works</a>
        <a href="#skills">Skills</a>
        <a href="#contact">Contact</a>
      </nav>

      <!-- CONTACT / SOCIAL -->
      <div class="social">
        <p class="connect">Let’s connect 💜</p>

        <a
          href="https://www.instagram.com/morimo.design/"
          target="_blank"
          rel="noopener"
          class="social-link"
        >
          Instagram
        </a>

        <a
          href="mailto:hello.morimo.design@gmail.com"
          class="social-link"
        >
          hello.morimo.design@gmail.com
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
import logo from '@/assets/logo.png'
const year = new Date().getFullYear()
</script>

<style scoped>
.footer {
  background: #5b2d91;
  color: #F3EDE5;
  padding: 70px 40px 30px;
}

/* CONTENT */

.footer-content {
  max-width: 1100px;
  margin: auto;

  display: grid;
  grid-template-columns: 1.5fr 1fr 1.2fr;
  gap: 50px;
  align-items: flex-start;
}

/* BRAND */

.brand {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.footer-logo {
  width: 140px;
}

.tagline {
  font-size: 0.9rem;
  opacity: 0.85;
  line-height: 1.6;
}

/* NAV */

.footer-nav {
  display: flex;
  flex-direction: column;
  gap: 12px;
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

.social {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.connect {
  font-size: 0.9rem;
  margin-bottom: 6px;
}

.social-link {
  color: #F3EDE5;
  text-decoration: none;
  font-weight: 600;
  background: rgba(255,255,255,0.15);
  padding: 8px 16px;
  border-radius: 999px;
  width: fit-content;
  transition: background 0.2s ease, transform 0.2s ease;
}

.social-link:hover {
  background: rgba(255,255,255,0.25);
  transform: translateY(-2px);
}

/* BOTTOM */

.footer-bottom {
  text-align: center;
  margin-top: 50px;
  font-size: 0.75rem;
  opacity: 0.7;
}

/* MOBILE */

@media (max-width: 900px) {
  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 40px;
  }

  .brand {
    align-items: center;
  }

  .footer-nav {
    align-items: center;
  }

  .social {
    align-items: center;
  }
}
</style>
