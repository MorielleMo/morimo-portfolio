<template>
  <section class="home" id="home">

    <!-- LOGO -->
    <img
      :src="logo"
      alt="MoriMo logo"
      class="logo"
      :class="{ hint: visibleBubbles.length === 0 }"
      @click="addBubble"
      :style="{ pointerEvents: visibleBubbles.length === allBubbles.length ? 'none' : 'auto' }"
    />

    <!-- BULLES -->
    <div
      v-for="(b, i) in visibleBubbles"
      :key="b.label"
      class="bubble-wrapper"
      :class="'float' + i"
      :style="{
        left: b.x + 'px',
        top: b.y + 'px'
      }"
    >
      <button class="bubble" @click="goTo(b.target)">
        {{ b.label }}
      </button>
    </div>

    <!-- BACK TO TOP ARROW -->
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

const allBubbles = [
  { label: 'About',    target: 'about',    x: 120,  y: 180 },
  { label: 'Works',    target: 'works',    x: 1100, y: 180 },
  { label: 'Identity', target: 'identity', x: 560,  y: 120 },
  { label: 'Skills',   target: 'skills',   x: 250,  y: 620 },
  { label: 'Contact',  target: 'contact',  x: 1000, y: 620 }
]

const visibleBubbles = ref([])

function addBubble() {
  if (visibleBubbles.value.length < allBubbles.length) {
    visibleBubbles.value.push(allBubbles[visibleBubbles.value.length])
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

onMounted(() => {
  window.addEventListener('scroll', onScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
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
}

/* LOGO */
.logo {
  width: 440px;
  cursor: pointer;
  z-index: 2;
}

/* HINT */
.logo.hint {
  animation: pulse 2s ease-in-out infinite;
  filter: drop-shadow(0 0 14px rgba(140, 90, 255, 0.6));
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

/* ===== BULLES ===== */

.bubble-wrapper {
  position: absolute;
  z-index: 10;
}

.bubble {
  width: 140px;
  height: 140px;
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
  transition: transform 0.2s ease;
}

.bubble:hover {
  transform: scale(1.1);
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
  0% { transform: translate(0,0); }
  50% { transform: translate(30px, -40px); }
  100% { transform: translate(0,0); }
}

@keyframes drift2 {
  0% { transform: translate(0,0); }
  50% { transform: translate(-35px, -30px); }
  100% { transform: translate(0,0); }
}

@keyframes drift3 {
  0% { transform: translate(0,0); }
  50% { transform: translate(25px, -25px); }
  100% { transform: translate(0,0); }
}

@keyframes drift4 {
  0% { transform: translate(0,0); }
  50% { transform: translate(-30px, -35px); }
  100% { transform: translate(0,0); }
}

/* ===== BACK TO TOP BUTTON ===== */

.back-top {
  position: fixed;
  bottom: 30px;
  right: 30px;
  width: 46px;
  height: 46px;
  border-radius: 50%;
  border: none;

  background: #5b2d91;
  color: white;
  font-size: 1.4rem;
  cursor: pointer;
  z-index: 50;

  box-shadow: 0 12px 30px rgba(90,45,145,0.5);
  animation: bounce 1.6s infinite;
}

@keyframes bounce {
  0%,100% { transform: translateY(0); }
  50% { transform: translateY(-6px); }
}
</style>
