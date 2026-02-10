<template>
  <section id="works" class="works">

    <h2 class="title">My Works ✨</h2>
    <p class="subtitle">
      Projects created during my studies and personal practice
    </p>

    <!-- ================= CAROUSEL WEB PROJECTS ================= -->

    <div class="carousel-wrapper">

      <button class="nav left" @click="prev">❮</button>

      <div class="carousel">
        <div
          class="track"
          :style="{ transform: `translateX(-${current * 320}px)` }"
        >
          <div
            v-for="p in projects"
            :key="p.title"
            class="card"
          >
            <div class="image">
              <span class="tag">{{ p.type }}</span>
            </div>

            <div class="info">
              <h3>{{ p.title }}</h3>
              <p>{{ p.desc }}</p>

              <a :href="p.link" target="_blank" class="btn">
                View project →
              </a>
            </div>
          </div>
        </div>
      </div>

      <button class="nav right" @click="next">❯</button>

    </div>

    <!-- ================= DESIGN GALLERY ================= -->

    <h3 class="gallery-title">Design Gallery 🎨</h3>
    <p class="gallery-sub">Canva • Illustrator • Photoshop</p>

    <div class="gallery-grid">
      <div
        v-for="(img, i) in gallery"
        :key="i"
        class="gallery-item"
      >
        <img :src="img.src" :alt="img.type" />
        <span class="badge">{{ img.type }}</span>
      </div>
    </div>

  </section>
</template>

<script setup>
import { ref } from 'vue'

/* ===== CAROUSEL ===== */

const current = ref(0)

const projects = [
  {
    title: "Moonoa — Fictive Brand",
    type: "WordPress",
    desc: "Fictive website created during my studies using WordPress.",
    link: "https://morimo-ovh.com/cms2/"
  },
  
  {
    title: "Examen Blanc",
    type: "HTML / CSS",
    desc: "Practice exam project built with HTML and CSS.",
    link: "https://morimo-ovh.com/examen-blanc/"
  },
  {
    title: "Acheter Local",
    type: "HTML / CSS",
    desc: "First HTML/CSS test project about local shopping.",
    link: "https://morimo-ovh.com/examen-moke-acheter-local/"
  },
  {
    title: "Roman Couchard — Client",
    type: "WordPress",
    desc: "Artist portfolio website made for a real client using WordPress.",
    link: "https://morimo-ovh.com/site-roman-couchard/"
  }
]

function next() {
  if (current.value < projects.length - 1) current.value++
}

function prev() {
  if (current.value > 0) current.value--
}

/* ===== GALLERY IMPORTS (NOMS EXACTS) ===== */

import illu1 from '@/assets/gallery/image illustrator 1.png'
import illu2 from '@/assets/gallery/image illustrator 2.png'
import illu3 from '@/assets/gallery/image illustrator 3.png'

import ps1 from '@/assets/gallery/image photoshop 1.png'
import ps2 from '@/assets/gallery/image photoshop 2.jpeg'
import ps3 from '@/assets/gallery/image photoshop 3.png'

import canva1 from '@/assets/gallery/logo canva 1.png'
import canva2 from '@/assets/gallery/logo canva 2.png'
import canva3 from '@/assets/gallery/logo canva 3.png'

const gallery = [
  { src: illu1, type: 'Illustrator' },
  { src: illu2, type: 'Illustrator' },
  { src: illu3, type: 'Illustrator' },

  { src: ps1, type: 'Photoshop' },
  { src: ps2, type: 'Photoshop' },
  { src: ps3, type: 'Photoshop' },

  { src: canva1, type: 'Canva' },
  { src: canva2, type: 'Canva' },
  { src: canva3, type: 'Canva' },
]
</script>

<style scoped>
.works {
  min-height: 100vh;
  background: #E6D9F6;
  padding: 120px 80px;
  text-align: center;
}

/* ===== TITLES ===== */

.title {
  font-size: 2.5rem;
  color: #5b2d91;
  margin-bottom: 12px;
}

.subtitle {
  color: #6b4a8f;
  margin-bottom: 70px;
}

/* ===== CAROUSEL ===== */

.carousel-wrapper {
  position: relative;
  max-width: 1000px;
  margin: auto;
  display: flex;
  align-items: center;
}

.carousel {
  overflow: hidden;
  width: 100%;
}

.track {
  display: flex;
  gap: 30px;
  transition: transform 0.6s cubic-bezier(.17,.67,.29,1.02);
}

.card {
  min-width: 300px;
  background: #F3EDE5;
  border-radius: 26px;
  overflow: hidden;
  box-shadow: 0 18px 40px rgba(90,45,145,0.25);
  display: flex;
  flex-direction: column;
}

.image {
  height: 160px;
  background: linear-gradient(135deg, #cbb6ff, #9b7fdc);
  position: relative;
}

.tag {
  position: absolute;
  top: 12px;
  left: 12px;
  background: #5A331D;
  color: #F3EDE5;
  padding: 6px 14px;
  border-radius: 999px;
  font-size: 0.7rem;
}

.info {
  padding: 22px;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.btn {
  margin-top: auto;
  align-self: flex-start;
  padding: 10px 22px;
  background: #5A331D;
  color: #F3EDE5;
  border-radius: 999px;
  text-decoration: none;
}

/* ===== NAV ===== */

.nav {
  background: #5b2d91;
  color: white;
  border: none;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  font-size: 1.4rem;
  cursor: pointer;
}

.nav.left { margin-right: 15px; }
.nav.right { margin-left: 15px; }

/* ===== GALLERY ===== */

.gallery-title {
  margin-top: 120px;
  font-size: 2rem;
  color: #5b2d91;
}

.gallery-sub {
  color: #6b4a8f;
  margin-bottom: 40px;
}

.gallery-grid {
  max-width: 1100px;
  margin: auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 24px;
}

.gallery-item {
  position: relative;
  border-radius: 18px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 10px 25px rgba(0,0,0,0.15);
}

.gallery-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.badge {
  position: absolute;
  bottom: 10px;
  left: 10px;
  background: rgba(90,45,145,0.9);
  color: white;
  padding: 6px 14px;
  border-radius: 999px;
  font-size: 0.7rem;
}
</style>
