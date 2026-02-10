<template>
  <section id="about" class="about">

    <!-- TITLE -->
    <h2 class="title">
      <span class="emoji-bubble">👋</span>
      About Me
    </h2>

    <!-- FLIP SCENE -->
    <div class="card-scene">
      <div
        class="id-card"
        :class="{ flipped: isFlipped }"
        @click="isFlipped = !isFlipped"
      >

        <!-- ===== FRONT ===== -->
        <div class="card-face card-front">

          <div class="photo-frame">
            <div class="photo-bg">
              <img src="@/assets/profile.jpg" alt="MoriMo photo" />
            </div>
          </div>

          <div class="info">
            <h3 class="name">MoriMo</h3>
            <p class="role">UX/UI & Web Designer</p>

            <ul class="details">
              <li><strong>Origin:</strong> Belgian — Congolese roots 🇧🇪🇨🇩</li>
              <li><strong>Passion:</strong> Music & creative expression 🎶</li>
              <li><strong>Focus:</strong> User-centered design</li>
            </ul>

            <p class="hint">Tap to flip →</p>
          </div>

        </div>

        <!-- ===== BACK ===== -->
        <div class="card-face card-back">

          <h3 class="back-title">🎨 What I love to create</h3>

          <p class="back-text">
            I enjoy designing visuals, logos and graphic identities.
            I also work with photography and enhance images using
            Photoshop to create strong visual impact.
          </p>

          <p class="back-text">
            I love using Canva to explore ideas quickly and create
            engaging visuals, and I design wireframes and mockups
            on Figma with a strong focus on user experience.
          </p>

          <p class="back-text">
            I studied web design and I’m passionate about digital
            communication, video editing and social media management
            such as Instagram, Facebook and TikTok.
          </p>

          <div class="tools">
            <span>Canva</span>
            <span>Figma</span>
            <span>Photoshop</span>
            <span>UX/UI</span>
            <span>Social Media</span>
          </div>

          <p class="hint">← Tap to go back</p>

        </div>

      </div>
    </div>

  </section>
</template>

<script setup>
import { ref } from 'vue'
const isFlipped = ref(false)
</script>

<style scoped>
.about {
  min-height: 100vh;
  background: #f6f1fb;
  padding: 120px 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* TITLE */

.title {
  display: flex;
  align-items: center;
  gap: 14px;
  font-size: 2.3rem;
  color: #5b2d91;
  margin-bottom: 60px;
}

.emoji-bubble {
  background: #b892ff;
  color: white;
  width: 46px;
  height: 46px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.3rem;
  box-shadow: 0 10px 25px rgba(120,70,180,0.4);
}

/* SCENE */

.card-scene {
  perspective: 1200px;
  width: 100%;
  max-width: 900px;
}

/* CARD */

.id-card {
  position: relative;
  width: 100%;
  min-height: 480px;
  transform-style: preserve-3d;
  transition: transform 0.9s cubic-bezier(.17,.89,.32,1.49);
  cursor: pointer;
}

.id-card.flipped {
  transform: rotateY(180deg);
}

/* FACES */

.card-face {
  position: absolute;
  inset: 0;
  backface-visibility: hidden;
  background: linear-gradient(135deg, #ffffff, #f0e9ff);
  border-radius: 30px;
  padding: 40px;
  box-shadow: 0 30px 60px rgba(120,70,180,0.25);
  display: flex;
  gap: 40px;
}

/* FRONT */

.card-front {
  display: flex;
}

/* PHOTO */

.photo-frame {
  display: flex;
  justify-content: center;
}

.photo-bg {
  width: 220px;
  height: 280px;
  border-radius: 26px;
  background: linear-gradient(135deg, #d8c9ff, #b892ff);
  padding: 10px;
}

.photo-bg img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 20px;
}

/* INFO */

.info {
  display: flex;
  flex-direction: column;
}

.name {
  font-size: 2rem;
  color: #5b2d91;
}

.role {
  color: #7b4ac7;
  font-weight: 600;
  margin-bottom: 16px;
}

.details {
  list-style: none;
  padding: 0;
  margin-bottom: 20px;
}

.details li {
  color: #4b2b6a;
  font-size: 0.95rem;
  margin-bottom: 6px;
}

.hint {
  margin-top: auto;
  font-size: 0.8rem;
  opacity: 0.6;
}

/* BACK */

.card-back {
  transform: rotateY(180deg);
  flex-direction: column;
}

.back-title {
  font-size: 1.6rem;
  color: #5b2d91;
  margin-bottom: 20px;
}

.back-text {
  color: #4b2b6a;
  line-height: 1.7;
  margin-bottom: 14px;
}

/* TOOLS */

.tools {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 20px;
}

.tools span {
  background: #e7dcfb;
  color: #5b2d91;
  padding: 8px 14px;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 600;
}

/* MOBILE */

@media (max-width: 800px) {
  .card-face {
    flex-direction: column;
    text-align: center;
  }

  .photo-bg {
    width: 180px;
    height: 220px;
  }

  .tools {
    justify-content: center;
  }
}
</style>
