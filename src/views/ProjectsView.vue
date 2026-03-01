<script setup>
import { ref } from 'vue'

const projects = ref([
  {
    id: 1,
    title: 'TPI',
    description: 'Un site web à venir',
    technologies: ['Laravel', 'Vue.js', 'Inertia.js'],
    image: 'https://placehold.co/600x400/42b883/white?text=Site+Web+à+venir', 
    githubLink: 'https://github.com/',
  },
  {
    id: 2,
    title: 'Anime Tracker', 
    description: 'Dashboard complet pour suivre sa collection d\'animes. Gestion des états (à voir, terminé), notes et statistiques.',
    technologies: ['Laravel', 'Inertia.js', 'Vue.js', 'Tailwind CSS'],
    image: '/images/animeTracker.png', 
    githubLink: 'https://github.com/William-Stilli/AnimeList',
  },
  {
    id: 3,
    title: 'Portfolio Personnel',
    description: 'Ce site web ! Développé avec Vue 3 et Vite pour présenter mes compétences.',
    technologies: ['Vue.js', 'CSS3', 'Vite'],
    image: '/images/portefolio.png',
    githubLink: 'https://github.com/ton-pseudo/portfolio',
  }
])
</script>

<template>
  <div class="projects-container">
    <h1>Mes Projets</h1>
    <p class="intro">Voici une sélection de mes travaux scolaires et personnels.</p>

    <div class="projects-grid">
      <article v-for="project in projects" :key="project.id" class="project-card">
        
        <div class="card-image">
          <img :src="project.image" :alt="project.title" />
        </div>

        <div class="card-content">
          <h2>{{ project.title }}</h2>
          <p class="description">{{ project.description }}</p>
          
          <div class="tags">
            <span v-for="tech in project.technologies" :key="tech" class="tag">
              {{ tech }}
            </span>
          </div>

          <div class="links">
            <a v-if="project.githubLink" :href="project.githubLink" target="_blank" class="btn-code">
              GitHub <i class="icon">📂</i>
            </a>
          </div>
        </div>

      </article>
    </div>
  </div>
</template>

<style scoped>
.projects-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem 0;
}

h1 {
  text-align: center;
  color: #2c3e50;
  margin-bottom: 0.5rem;
}

.intro {
  text-align: center;
  color: #666;
  margin-bottom: 3rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  padding: 0 1rem;
}

.project-card {
  background: white;
  border-radius: 12px;
  overflow: hidden; 
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  display: flex;
  flex-direction: column;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15);
}

.card-image img {
  width: 100%;
  height: 200px;
  object-fit: cover; 
}

.card-content {
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  flex-grow: 1; 
}

.card-content h2 {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
  color: #2c3e50;
}

.description {
  color: #555;
  font-size: 0.95rem;
  margin-bottom: 1rem;
  flex-grow: 1;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 1.5rem;
}

.tag {
  background-color: #eef2f5;
  color: #2c3e50;
  padding: 4px 10px;
  border-radius: 6px;
  font-size: 0.8rem;
  font-weight: 600;
}

.links {
  display: flex;
  gap: 10px;
}

.links a {
  text-decoration: none;
  padding: 8px 16px;
  border-radius: 6px;
  font-size: 0.9rem;
  font-weight: bold;
  text-align: center;
  flex: 1;
}

.btn-code {
  background-color: #333;
  color: white;
}

.btn-demo {
  background-color: #42b883;
  color: white;
}

.btn-code:hover, .btn-demo:hover {
  opacity: 0.9;
}
</style>