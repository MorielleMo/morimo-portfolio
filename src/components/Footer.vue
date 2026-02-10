<template>
  <footer class="footer">

    <!-- TOP -->
    <div class="footer-top">

      <!-- LOGO -->
      <img
        :src="logo"
        alt="MoriMo logo"
        class="footer-logo"
      />

      <!-- TAGLINE -->
      <p class="tagline">
        UX/UI & Web Designer · Creating meaningful digital experiences ✨
      </p>

      <!-- FOOTER NAV (INLINE) -->
      <nav class="footer-nav">
        <a href="#home">Home</a>
        <span>•</span>
        <a href="#about">About</a>
        <span>•</span>
        <a href="#brand">Brand</a>
        <span>•</span>
        <a href="#works">Works</a>
        <span>•</span>
        <a href="#skills">Skills</a>
        <span>•</span>
        <a href="#contact">Contact</a>
      </nav>

    </div>

    <!-- SOCIAL -->
    <div class="footer-social">
      <a
        href="https://www.instagram.com/morimo.design/"
        target="_blank"
        rel="noopener"
      >
        Instagram
      </a>

      <a href="mailto:hello.morimo.design@gmail.com">
        hello.morimo.design@gmail.com
      </a>
    </div>

    <!-- BOTTOM -->
    <div class="footer-bottom">
      © {{ year }} MoriMo — All rights reserved
    </div>

  </footer>
</template>

<script setup>
import logo from '@/assets/logo-black.png'
const year = new Date().getFullYear()
</script>

<style scoped>
.footer {
  background: #5b2d91;
  color: #F3EDE5;
  padding: 80px 30px 30px;
  text-align: center;
}

/* TOP */

.footer-top {
  max-width: 900px;
  margin: auto;

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 22px;
}

/* LOGO */

.footer-logo {
  width: 160px;
}

/* TAGLINE */

.tagline {
  font-size: 0.9rem;
  opacity: 0.85;
  max-width: 600px;
  line-height: 1.6;
}

/* NAV */

.footer-nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
  font-size: 0.85rem;
}

.footer-nav a {
  color: #F3EDE5;
  text-decoration: none;
  transition: opacity 0.2s ease;
}

.footer-nav span {
  opacity: 0.5;
}

.footer-nav a:hover {
  opacity: 0.7;
}

/* SOCIAL */

.footer-social {
  margin-top: 35px;
  display: flex;
  justify-content: center;
  gap: 18px;
  flex-wrap: wrap;
}

.footer-social a {
  color: #F3EDE5;
  text-decoration: none;
  font-weight: 600;
  background: rgba(255,255,255,0.15);
  padding: 8px 18px;
  border-radius: 999px;
  transition: background 0.2s ease, transform 0.2s ease;
}

.footer-social a:hover {
  background: rgba(255,255,255,0.25);
  transform: translateY(-2px);
}

/* BOTTOM */

.footer-bottom {
  margin-top: 45px;
  font-size: 0.75rem;
  opacity: 0.7;
}

/* MOBILE */

@media (max-width: 600px) {
  .footer-logo {
    width: 130px;
  }

  .footer-nav {
    gap: 6px;
  }
}
</style>
