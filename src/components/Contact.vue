<template>
  <section id="contact" class="contact">

    <h2 class="title">Final Quest 🎯</h2>
    <p class="subtitle">Let’s connect and create something beautiful</p>

    <div class="contact-card">

      <h3>Contact MoriMo 💌</h3>
      <p class="text">
        Interested in working together, a project, or just want to say hi?
        You can reach me safely through these channels:
      </p>

      <!-- CONTACT OPTIONS -->
      <div class="options">

        <!-- EMAIL -->
        <a
          href="mailto:moriellemoke@gmail.com"
          class="option"
        >
          📧
          <span>Email</span>
          <small>moriellemoke@gmail.com</small>
        </a>

        <!-- INSTAGRAM -->
        <a
          href="https://www.instagram.com/moriellemoke/"
          target="_blank"
          class="option"
        >
          📸
          <span>Instagram</span>
          <small>@moriellemoke</small>
        </a>

      </div>

      <p class="coming">
        More social quests coming soon… TikTok, Pro Instagram & more ✨
      </p>

    </div>

  </section>
</template>

<style scoped>
.contact {
  min-height: 100vh;
  background: #E6D9F6;
  padding: 120px 40px;
  text-align: center;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.title {
  font-size: 2.6rem;
  color: #5b2d91;
  margin-bottom: 6px;
}

.subtitle {
  color: #6b4a8f;
  margin-bottom: 50px;
}

/* ===== CARD ===== */

.contact-card {
  background: #F3EDE5;
  border-radius: 30px;
  padding: 40px 30px;
  max-width: 420px;
  width: 100%;

  box-shadow: 0 25px 60px rgba(90,45,145,0.35);
}

.contact-card h3 {
  color: #5A331D;
  margin-bottom: 14px;
}

.text {
  color: #5a3d7a;
  font-size: 0.95rem;
  margin-bottom: 30px;
}

/* ===== OPTIONS ===== */

.options {
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.option {
  background: #ffffff;
  border-radius: 20px;
  padding: 16px;

  text-decoration: none;
  color: #5b2d91;

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;

  font-size: 1.3rem;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.option span {
  font-weight: 700;
  font-size: 1rem;
}

.option small {
  font-size: 0.75rem;
  color: #6b4a8f;
}

.option:hover {
  transform: translateY(-6px) scale(1.02);
  box-shadow: 0 18px 35px rgba(90,45,145,0.4);
}

/* ===== COMING SOON ===== */

.coming {
  margin-top: 25px;
  font-size: 0.8rem;
  color: #6b4a8f;
}

/* MOBILE */

@media (max-width: 700px) {
  .contact {
    padding: 100px 30px;
  }

  .title {
    font-size: 2rem;
  }
}
</style>
