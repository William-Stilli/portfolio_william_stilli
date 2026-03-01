<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="app-container">
    
    <header>
      <div class="logo">
        <h1>William Stilli</h1>
      </div>

      <nav>
        <RouterLink to="/">Accueil</RouterLink>
        <RouterLink to="/projets">Mes Projets</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </nav>
    </header>

    <main>
      <RouterView />
    </main>

    <footer>
      <p>&copy; 2026 William Stilli - Développeur Web & Mobile</p>
      <div class="socials">
        <a href="https://github.com/ton-github" target="_blank">GitHub</a>
        <a href="https://linkedin.com/in/ton-linkedin" target="_blank">LinkedIn</a>
      </div>
    </footer>

  </div>
</template>

<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Arial', sans-serif;
  background-color: #f4f4f4;
  color: #333;
  line-height: 1.6;
}

.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header {
  background-color: #2c3e50;
  color: white;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header h1 {
  font-size: 1.5rem;
}

nav a {
  color: white;
  text-decoration: none;
  margin-left: 20px;
  font-weight: bold;
}

nav a:hover {
  color: #42b883; 
}

nav a.router-link-active {
  color: #42b883;
  text-decoration: underline;
}

main {
  flex: 1;
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}

footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 1rem;
  margin-top: auto;
}

footer a {
  color: #42b883;
  text-decoration: none;
  margin: 0 10px;
}
</style>