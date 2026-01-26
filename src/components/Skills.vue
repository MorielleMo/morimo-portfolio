<template>
  <section id="skills" class="skills">

    <h2 class="title">Player Skills 🎮</h2>
    <p class="subtitle">MoriMo — UX/UI Designer Build</p>

    <div class="skills-grid">

      <!-- ===== TECH SKILLS ===== -->
      <div class="card">
        <h3 class="card-title">⚔️ Technical Skills</h3>

        <div v-for="skill in hardSkills" :key="skill.name" class="skill-bar">
          <div class="label-row">
            <span>{{ skill.name }}</span>
            <span class="percent">{{ skill.level }}%</span>
          </div>

          <div class="bar-bg">
            <div class="bar-fill" :style="{ width: skill.level + '%' }"></div>
          </div>
        </div>
      </div>

      <!-- ===== SOFT SKILLS ===== -->
      <div class="card">
        <h3 class="card-title">💖 Soft Skills</h3>

        <div class="soft-grid">
          <span v-for="s in softSkills" :key="s" class="pill">
            {{ s }}
          </span>
        </div>
      </div>

      <!-- ===== LANGUAGES ===== -->
      <div class="card full">
        <h3 class="card-title">🌍 Languages</h3>

        <div class="languages">
          <div
            v-for="lang in languages"
            :key="lang.name"
            class="lang-card"
          >
            <strong>{{ lang.name }}</strong>
            <span>{{ lang.level }}</span>
          </div>
        </div>
      </div>

    </div>

  </section>
</template>

<script setup>
const hardSkills = [
  { name: "UX Design", level: 85 },
  { name: "UI Design", level: 82 },
  { name: "Figma / Prototyping", level: 80 },
  { name: "HTML & CSS", level: 78 },
  { name: "Responsive Design", level: 75 },
  { name: "WordPress", level: 70 }
]

const softSkills = [
  "Creativity",
  "Empathy",
  "Communication",
  "Problem Solving",
  "Team Spirit",
  "Detail Oriented"
]

const languages = [
  { name: "French 🇫🇷", level: "Native" },
  { name: "English 🇬🇧", level: "Good level" },
  { name: "Spanish 🇪🇸", level: "Beginner" },
  { name: "Dutch 🇳🇱", level: "Learning" }
]
</script>

<style scoped>
.skills {
  min-height: 100vh;
  background: #E6D9F6;
  padding: 120px 80px;
}

.title {
  text-align: center;
  font-size: 2.6rem;
  color: #5b2d91;
  margin-bottom: 6px;
}

.subtitle {
  text-align: center;
  color: #6b4a8f;
  margin-bottom: 60px;
}

/* ===== GRID ===== */

.skills-grid {
  max-width: 1100px;
  margin: auto;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
}

/* ===== CARD ===== */

.card {
  background: #F3EDE5;
  border-radius: 28px;
  padding: 30px;

  box-shadow: 0 18px 40px rgba(90,45,145,0.25);
}

.card.full {
  grid-column: span 2;
}

.card-title {
  color: #5A331D;
  font-size: 1.5rem;
  margin-bottom: 20px;
}

/* ===== TECH SKILLS ===== */

.skill-bar {
  margin-bottom: 18px;
}

.label-row {
  display: flex;
  justify-content: space-between;
  font-weight: 600;
  color: #5b2d91;
  margin-bottom: 6px;
}

.percent {
  font-size: 0.8rem;
  opacity: 0.7;
}

.bar-bg {
  width: 100%;
  height: 12px;
  background: #d8c4eb;
  border-radius: 999px;
  overflow: hidden;
}

.bar-fill {
  height: 100%;
  background: linear-gradient(90deg, #9b7fdc, #5b2d91);
  border-radius: 999px;
  animation: load 1.2s ease-out forwards;
}

@keyframes load {
  from { width: 0; }
}

/* ===== SOFT SKILLS ===== */

.soft-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.pill {
  background: #5b2d91;
  color: #F3EDE5;
  padding: 10px 16px;
  border-radius: 999px;
  font-size: 0.85rem;
  box-shadow: 0 8px 20px rgba(90,45,145,0.4);
}

/* ===== LANGUAGES ===== */

.languages {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 20px;
}

.lang-card {
  background: #ffffff;
  border-radius: 18px;
  padding: 18px;
  text-align: center;

  border: 2px solid #5b2d91;
}

.lang-card strong {
  display: block;
  color: #5b2d91;
  margin-bottom: 6px;
}

.lang-card span {
  color: #5A331D;
  font-size: 0.85rem;
}

/* ===== MOBILE ===== */

@media (max-width: 900px) {
  .skills {
    padding: 100px 30px;
  }

  .skills-grid {
    grid-template-columns: 1fr;
  }

  .card.full {
    grid-column: span 1;
  }

  .title {
    font-size: 2rem;
  }
}
</style>
