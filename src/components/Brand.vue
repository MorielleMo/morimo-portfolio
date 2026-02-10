<template>
  <section id="identity" class="brand">

    <h2 class="title">Design Playlist 🎧</h2>
    <p class="subtitle">Discover my brand identity as tracks</p>

    <!-- PHONE -->
    <div class="phone">

      <!-- SCREEN -->
      <div class="screen">

        <!-- TRACK 1 : LOGO -->
        <div v-if="track === 0" class="track">
          <img src="@/assets/logo.png" class="logo" />
          <h3>MoriMo Design</h3>
          <p>Brand logo & variations</p>
        </div>

        <!-- TRACK 2 : COLORS -->
        <div v-if="track === 1" class="track">
          <h3>Color Palette</h3>
          <div class="colors">
            <span style="background:#F3EDE5"></span>
            <span style="background:#5A331D"></span>
            <span style="background:#EABAaf"></span>
            <span style="background:#D8C4EB"></span>
            <span style="background:#C9A15B"></span>
            <span style="background:#7B977A"></span>
          </div>
        </div>

        <!-- TRACK 3 : TYPO -->
        <div v-if="track === 2" class="track">
          <h3>Typography</h3>
          <p class="season">The Seasons</p>
          <p class="inter">Inter — clean UI text</p>
        </div>

        <!-- TRACK 4 : COMPONENTS -->
        <div v-if="track === 3" class="track">
          <h3>UI Components</h3>
          <button class="btn primary">Primary</button>
          <button class="btn secondary">Secondary</button>
          <a class="link">Text link</a>
        </div>

        <!-- TRACK 5 : MOODBOARD -->
        <div v-if="track === 4" class="track mood">
          <img src="@/assets/moodboard.png" class="mood-img" />
        </div>

      </div>

      <!-- PLAYER -->
      <div class="player">
        <button @click="prev">⏮</button>
        <button class="play">⏯</button>
        <button @click="next">⏭</button>
      </div>

      <div class="track-name">
        Track {{ track + 1 }} / 5
      </div>

    </div>

  </section>
</template>

<script setup>
import { ref } from 'vue'

const track = ref(0)

function next() {
  track.value = (track.value + 1) % 5
}

function prev() {
  track.value = (track.value - 1 + 5) % 5
}
</script>

<style scoped>
/* ===== SECTION ===== */

.brand {
  min-height: 100vh;
  background: #E6D9F6;
  padding: 120px 40px;
  text-align: center;
}

.title {
  font-size: 2.4rem;
  color: #5b2d91;
}

.subtitle {
  margin-bottom: 60px;
  color: #6b4a8f;
}

/* ===== PHONE ===== */

.phone {
  width: 320px;
  max-width: 100%;
  margin: auto;
  background: #9b7fdc;
  border-radius: 40px;
  padding: 16px;
  box-shadow:
    0 30px 70px rgba(90,45,145,0.45),
    0 0 40px rgba(184,146,255,0.6);
}

/* ===== SCREEN ===== */

.screen {
  background: #F3EDE5;
  border-radius: 30px;
  padding: 20px;
  min-height: 360px;

  display: flex;
  align-items: center;
  justify-content: center;

  overflow-y: auto;
}

/* ===== TRACK ===== */

.track {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  animation: fade 0.35s ease;
  width: 100%;
  text-align: center;
}

@keyframes fade {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; }
}

.logo {
  width: 110px;
}

/* ===== COLORS ===== */

.colors {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}

.colors span {
  width: 42px;
  height: 42px;
  border-radius: 10px;
  border: 1.5px solid #000;
}

/* ===== TYPO ===== */

.season {
  font-size: 1.6rem;
  color: #5A331D;
}

.inter {
  color: #3a2a22;
}

/* ===== COMPONENTS ===== */

.btn {
  border-radius: 999px;
  padding: 10px 24px;
  border: none;
  font-weight: 600;
}

.primary {
  background: #5A331D;
  color: #F3EDE5;
}

.secondary {
  background: transparent;
  border: 2px solid #5A331D;
  color: #5A331D;
}

.link {
  color: #EABAaf;
  text-decoration: none;
}

/* ===== MOODBOARD ===== */

.mood-img {
  width: 100%;
  max-height: 260px;
  border-radius: 16px;
  object-fit: cover;
  box-shadow: 0 10px 25px rgba(0,0,0,0.25);
}

/* ===== PLAYER ===== */

.player {
  display: flex;
  justify-content: center;
  gap: 25px;
  margin-top: 16px;
}

.player button {
  border: none;
  background: none;
  font-size: 1.6rem;
  cursor: pointer;
  color: #ffffff;
}

.play {
  font-size: 2rem;
}

.track-name {
  margin-top: 8px;
  font-size: 0.8rem;
  color: #f4eefe;
}

/* ===== MOBILE ===== */

@media (max-width: 768px) {

  .brand {
    padding: 100px 20px;
  }

  .title {
    font-size: 2rem;
  }

  .phone {
    width: 100%;
    max-width: 340px;
  }

  .screen {
    min-height: 300px;
    max-height: 60vh;
  }

  .logo {
    width: 90px;
  }

  .season {
    font-size: 1.3rem;
  }

  .colors span {
    width: 36px;
    height: 36px;
  }
}
</style>
