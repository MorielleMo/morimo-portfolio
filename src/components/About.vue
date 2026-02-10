<template>
  <section id="about" class="about">

    <!-- TITLE -->
    <h2 class="title">
      About Me
      <span class="emoji-bubble">👋</span>
    </h2>

    <!-- FLIP SCENE -->
    <div class="card-scene">
      <div
        class="id-card"
        :class="{ flipped: isFlipped }"
        @click="isFlipped = !isFlipped"
      >

        <!-- ===== FRONT (RECTO) ===== -->
        <div class="card-face card-front">

          <!-- PHOTO -->
          <div class="photo-frame">
            <div class="photo-bg">
              <img src="@/assets/profile.jpg" alt="MoriMo photo" />
            </div>
          </div>

          <!-- INFO -->
          <div class="info">
            <h3 class="name">MoriMo</h3>
            <p class="role">UX/UI & Web Designer</p>

            <ul class="details">
              <li><strong>Origin:</strong> Belgian — Congolese roots 🇧🇪🇨🇩</li>
              <li><strong>Passion:</strong> Music & creative expression 🎶</li>
              <li><strong>Focus:</strong> User-centered digital experiences</li>
            </ul>

            <!-- BIO (desktop priority, OK if cropped on mobile) -->
            <p class="bio">
              I love designing playful and meaningful interfaces that combine
              soft aesthetics with intuitive interactions. I’m inspired by
              storytelling, games and emotional design to create experiences
              that people truly enjoy using.
            </p>

            <!-- TAGS -->
            <div class="tags-section">
              <p class="tags-title">Values & Mindset</p>

              <div class="tags">
                <span>User-Centered</span>
                <span>Creative</span>
                <span>Detail-Oriented</span>
                <span>Always Learning</span>
              </div>
            </div>

            <p class="hint">Tap to flip →</p>
          </div>

        </div>

        <!-- ===== BACK (VERSO) ===== -->
        <div class="card-face card-back">

          <h3 class="back-title">What I love to create</h3>

          <p class="back-text">
            I especially enjoy designing visuals, logos and graphic identities.
            I also work with photography, editing and enhancing images using
            Photoshop to increase visual impact and emotion.
          </p>

          <p class="back-text">
            I’m a big fan of Canva, a tool I use to quickly explore ideas, test
            concepts and create effective visuals. I also design wireframes and
            mockups in Figma, focusing on user experience, visual hierarchy and
            overall consistency.
          </p>

          <p class="back-text">
            Having studied web design, I’m also interested in digital
            communication, video editing, and social media management such as
            Instagram, Facebook and TikTok.
          </p>

          <p class="back-text">
            My goal is to create modern, coherent and human-centered projects
            that tell a story and strengthen a brand’s identity.
          </p>

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
/* ===== SECTION ===== */

.about {
  min-height: 100vh;
  background: #f6f1fb;
  padding: 120px 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* ===== TITLE ===== */

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

/* ===== SCENE ===== */

.card-scene {
  perspective: 1200px;
  width: 100%;
  max-width: 900px;
}

/* ===== CARD ===== */

.id-card {
  position: relative;
  width: 100%;
  height: 520px;
  transform-style: preserve-3d;
  transition: transform 0.9s cubic-bezier(.17,.89,.32,1.49);
  cursor: pointer;
}

.id-card.flipped {
  transform: rotateY(180deg);
}

/* ===== FACES ===== */

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

/* ===== FRONT ===== */

.card-front {
  display: flex;
}

/* PHOTO */

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
  margin-bottom: 16px;
}

.details li {
  color: #4b2b6a;
  font-size: 0.95rem;
  margin-bottom: 6px;
}

.bio {
  color: #4b2b6a;
  line-height: 1.7;
  margin-bottom: 20px;
}

/* TAGS */

.tags-section {
  margin-top: 20px;
}

.tags-title {
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #7b4ac7;
  margin-bottom: 12px;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.tags span {
  background: #e7dcfb;
  color: #5b2d91;
  padding: 8px 16px;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 600;
}

/* ===== BACK ===== */

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

/* ===== MOBILE (STABLE & SAFE) ===== */

@media (max-width: 800px) {

  .card-scene {
    height: 80vh;
  }

  .id-card {
    height: 100%;
  }

  .card-face {
    padding: 30px 20px;
    flex-direction: column;
    text-align: center;
    overflow-y: auto;
  }

  .photo-bg {
    width: 180px;
    height: 220px;
    margin: 0 auto;
  }

  .tags {
    justify-content: center;
  }
}
</style>
