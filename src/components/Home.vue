<template>
  <section class="home" id="home">

    <!-- LOGO -->
    <img
      :src="logo"
      alt="MoriMo logo"
      class="logo"
      :class="{ hint: visibleBubbles.length === 0 }"
      @click="addBubble"
    />

    <!-- BULLES -->
    <div
      v-for="(b, i) in visibleBubbles"
      :key="b.label"
      class="bubble-wrapper"
      :class="'float' + i"
      :style="{
        left: b.x,
        top: b.y
      }"
    >
      <button class="bubble" @click="goTo(b.target)">
        {{ b.label }}
      </button>
    </div>

    <!-- BACK TO TOP -->
    <button
      v-show="showArrow"
      class="back-top"
      @click="scrollTop"
    >
      ↑
    </button>

  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import logo from '@/assets/logo.png'

/* ===== POSITIONS ===== */

const desktopBubbles = [
  { label: 'About',    target: 'about',    x: '120px',  y: '180px' },
  { label: 'Works',    target: 'works',    x: '1100px', y: '180px' },
  { label: 'Identity', target: 'identity', x: '560px',  y: '120px' },
  { label: 'Skills',   target: 'skills',   x: '250px',  y: '620px' },
  { label: 'Contact',  target: 'contact',  x: '1000px', y: '620px' }
]

const mobileBubbles = [
  { label: 'About',    target: 'about',    x: '50%', y: '18%' },
  { label: 'Works',    target: 'works',    x: '15%', y: '45%' },
  { label: 'Identity', target: 'identity', x: '50%', y: '72%' },
  { label: 'Skills',   target: 'skills',   x: '85%', y: '45%' },
  { label: 'Contact',  target: 'contact',  x: '50%', y: '92%' }
]

const allBubbles = ref([])
const visibleBubbles = ref([])

/* ===== INIT ===== */

function setupBubbles() {
  allBubbles.value = window.innerWidth < 768
    ? mobileBubbles
    : desktopBubbles
}

function addBubble() {
  if (visibleBubbles.value.length < allBubbles.value.length) {
    visibleBubbles.value.push(
      allBubbles.value[visibleBubbles.value.length]
    )
  }
}

function goTo(id) {
  const el = document.getElementById(id)
  if (el) el.scrollIntoView({ behavior: 'smooth' })
}

/* ===== BACK TO TOP ===== */

const showArrow = ref(false)

function onScroll() {
  showArrow.value = window.scrollY > 300
}

function scrollTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

/* ===== LIFECYCLE ===== */

onMounted(() => {
  setupBubbles()
  window.addEventListener('scroll', onScroll)
  window.addEventListener('resize', setupBubbles)
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
  window.removeEventListener('resize', setupBubbles)
})
</script>

<style scoped>
.home {
  height: 100vh;
  width: 100vw;
  background: #E6D9F6;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

/* LOGO */
.logo {
  width: 440px;
  cursor: pointer;
  z-index: 2;
}

.logo.hint {
  animation: pulse 2s ease-in-out infinite;
  filter: drop-shadow(0 0 14px rgba(140, 90, 255, 0.6));
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

/* BULLES */

.bubble-wrapper {
  position: absolute;
  z-index: 10;
  transform: translate(-50%, -50%);
}

.bubble {
  width: 130px;
  height: 130px;
  border-radius: 50%;
  cursor: pointer;
  background: radial-gradient(circle at top left, #ffffff, #b892ff);
  border: none;
  color: #4b1f7a;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow:
    inset 0 0 12px rgba(255,255,255,0.7),
    0 0 30px rgba(150,100,255,0.6);
  animation: bubblePop 0.45s cubic-bezier(.17,.89,.32,1.49) forwards;
}

@keyframes bubblePop {
  0%   { transform: scale(0.2); opacity: 0; }
  60%  { transform: scale(1.15); opacity: 1; }
  100% { transform: scale(1); }
}

/* FLOAT */

.float0 { animation: drift1 9s ease-in-out infinite; }
.float1 { animation: drift2 11s ease-in-out infinite; }
.float2 { animation: drift3 10s ease-in-out infinite; }
.float3 { animation: drift4 12s ease-in-out infinite; }
.float4 { animation: drift1 13s ease-in-out infinite; }

@keyframes drift1 {
  50% { transform: translate(-50%, -60%); }
}
@keyframes drift2 {
  50% { transform: translate(-40%, -40%); }
}
@keyframes drift3 {
  50% { transform: translate(-60%, -45%); }
}
@keyframes drift4 {
  50% { transform: translate(-55%, -65%); }
}

/* BACK TO TOP */

.back-top {
  position: fixed;
  bottom: 24px;
  right: 24px;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  border: none;
  background: #5b2d91;
  color: white;
  font-size: 1.3rem;
  cursor: pointer;
  z-index: 50;
  box-shadow: 0 12px 30px rgba(90,45,145,0.5);
}

/* MOBILE */

@media (max-width: 768px) {
  .logo {
    width: 280px;
  }

  .bubble {
    width: 110px;
    height: 110px;
    font-size: 0.85rem;
  }
}
</style>
