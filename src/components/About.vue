<template>
  <section id="about" class="about">

    <h2 class="title">About Me</h2>

    <div class="id-card">

      <!-- PHOTO -->
      <div class="photo-frame">
        <div class="photo-bg">
          <!-- Mets ta photo dans src/assets/profile.jpg -->
          <img src="@/assets/profile.jpg" alt="MoriMo photo" />
        </div>
      </div>

      <!-- INFOS -->
      <div class="info">

        <h3 class="name">MoriMo</h3>
        <p class="role">UX/UI & Web Designer</p>

        <ul class="details">
          <li><strong>Origin:</strong> Belgian — Congolese roots 🇧🇪🇨🇩</li>
          <li><strong>Passion:</strong> Music & creative expression 🎶</li>
          <li><strong>Focus:</strong> User-centered digital experiences</li>
        </ul>

        <p class="bio">
          I love designing playful and meaningful interfaces that combine
          soft aesthetics with intuitive interactions. I’m inspired by
          storytelling, games and emotional design to create experiences that
          people truly enjoy using.
        </p>

        <div class="tags">
          <span>User-Centered</span>
          <span>Creative</span>
          <span>Detail-Oriented</span>
          <span>Always Learning</span>
        </div>

      </div>

    </div>

  </section>
</template>

<style scoped>
.about {
  min-height: 100vh;
  background: #f6f1fb;
  padding: 120px 80px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.title {
  font-size: 2.5rem;
  color: #5b2d91;
  margin-bottom: 70px;
}

/* ID CARD */

.id-card {
  background: linear-gradient(135deg, #ffffff, #f0e9ff);
  border-radius: 30px;
  padding: 40px;
  max-width: 900px;
  width: 100%;

  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 40px;

  box-shadow: 0 30px 60px rgba(120, 70, 180, 0.25);
}

/* PHOTO */

.photo-frame {
  display: flex;
  align-items: center;
  justify-content: center;
}

.photo-bg {
  width: 240px;
  height: 300px;
  border-radius: 26px;
  background: linear-gradient(135deg, #d8c9ff, #b892ff);
  padding: 10px;

  box-shadow: 0 20px 45px rgba(120, 70, 180, 0.35);

  display: flex;
  align-items: center;
  justify-content: center;
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
  margin-bottom: 4px;
}

.role {
  color: #7b4ac7;
  font-weight: 600;
  margin-bottom: 20px;
}

.details {
  list-style: none;
  padding: 0;
  margin-bottom: 18px;
}

.details li {
  color: #4b2b6a;
  margin-bottom: 6px;
  font-size: 0.95rem;
}

.bio {
  color: #4b2b6a;
  line-height: 1.7;
  margin-bottom: 25px;
}

/* TAGS */

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.tags span {
  background: #e7dcfb;
  color: #5b2d91;
  padding: 8px 14px;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 600;
}

/* MOBILE */

@media (max-width: 900px) {
  .about {
    padding: 100px 30px;
  }

  .title {
    font-size: 2rem;
  }

  .id-card {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .photo-bg {
    width: 200px;
    height: 260px;
  }

  .tags {
    justify-content: center;
  }
}
</style>
