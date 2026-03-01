<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="home-container">
    <section class="hero">
      <div class="intro-text">
        <h1>Bonjour, je suis <span class="name">William</span></h1>
        <h2>Futur Informaticien CFC (2026)</h2>
        <p class="subtitle">
          Spécialisé dans le développement d'applications modernes avec
          <strong>Flutter</strong> (Mobile) et <strong>Vue.js/Laravel</strong> (Web).
        </p>
        
        <div class="buttons">
          <RouterLink to="/projets" class="btn btn-primary">
            Voir mes projets 
          </RouterLink>
          
          <RouterLink to="/contact" class="btn btn-secondary">
            Me contacter
          </RouterLink>
        </div>
      </div>
    </section>

    <section class="skills-preview">
      <h3>Ma Stack Technique</h3>
      <div class="badges">
        <span class="badge">Vue.js</span>
        <span class="badge">Laravel</span>
        <span class="badge">Flutter</span>
        <span class="badge">Dart</span>
        <span class="badge">SQL & NoSQL</span>
        <span class="badge">Git / GitHub</span>
      </div>
    </section>
  </div>
</template>

<style scoped>
.home-container {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
  padding-top: 3rem;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
  color: #2c3e50;
}

.name {
  color: #42b883; 
}

.hero h2 {
  font-size: 1.5rem;
  color: #555;
  margin-bottom: 1.5rem;
  font-weight: normal;
}

.subtitle {
  font-size: 1.1rem;
  color: #666;
  margin-bottom: 2.5rem;
  line-height: 1.6;
}

.buttons {
  display: flex;
  gap: 15px;
  justify-content: center;
  margin-bottom: 4rem;
}

.btn {
  padding: 12px 24px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
  transition: transform 0.2s, background-color 0.2s;
}

.btn:hover {
  transform: translateY(-2px);
}

.btn-primary {
  background-color: #42b883;
  color: white;
  border: 2px solid #42b883;
}

.btn-secondary {
  background-color: transparent;
  color: #2c3e50;
  border: 2px solid #2c3e50;
}

.skills-preview h3 {
  margin-bottom: 1.5rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #888;
}

.badges {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}

.badge {
  background-color: #eee;
  padding: 8px 16px;
  border-radius: 20px;
  font-size: 0.9rem;
  color: #333;
  font-weight: 500;
}
</style>