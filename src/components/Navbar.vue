<template>
  <nav class="nav">
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#identity">Identity</a></li>
      <li><a href="#works">Works</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</template>

<style scoped>
.nav {
  position: fixed;
  top: 30px;
  right: 40px;
  z-index: 100;
}

.nav ul {
  display: flex;
  gap: 22px;
  list-style: none;
  padding: 14px 24px;
  background: rgba(255,255,255,0.75);
  backdrop-filter: blur(10px);
  border-radius: 999px;
  box-shadow: 0 10px 25px rgba(120,70,180,0.25);
}

.nav a {
  text-decoration: none;
  color: #5b2d91;
  font-weight: 600;
  font-size: 0.85rem;
}

.nav a:hover {
  color: #7b4ac7;
}

/* MOBILE */
@media (max-width: 700px) {
  .nav {
    right: 50%;
    transform: translateX(50%);
  }

  .nav ul {
    gap: 14px;
    padding: 10px 16px;
  }
}
</style>
