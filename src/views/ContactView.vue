<script setup>
import { ref } from 'vue'

const email = 'williamstilli20@gmail.com'
const phone = '076 408 03 88'
const copied = ref(false)

const copyEmail = () => {
  navigator.clipboard.writeText(email)
  copied.value = true
  
  setTimeout(() => {
    copied.value = false
  }, 2000)
}
</script>

<template>
  <div class="contact-container">
    <h1>Travaillons ensemble !</h1>
    <p class="subtitle">
      Actuellement à la recherche d'une opportunité en tant que 
      <strong>Développeur Junior</strong> (Web & Mobile) dès août 2026.
    </p>

    <div class="contact-cards">
      
      <div class="card email-card">
        <div class="icon">📧</div>
        <h3>Email</h3>
        <p>{{ email }}</p>
        <div class="actions">
          <a :href="'mailto:' + email" class="btn-primary">M'écrire</a>
          <button @click="copyEmail" class="btn-secondary">
            {{ copied ? 'Copié ! ✅' : 'Copier' }}
          </button>
        </div>
      </div>

      <div class="card phone-card">
        <div class="icon">📱</div>
        <h3>Téléphone</h3>
        <p>{{ phone }}</p>
        <a :href="'tel:' + phone.replace(/\s/g, '')" class="btn-primary">M'appeler</a>
      </div>

      <div class="card social-card">
        <div class="icon">🌐</div>
        <h3>Réseaux Sociaux</h3>
        <p>Retrouvez-moi sur :</p>
        <div class="social-links">
          <a href="https://www.linkedin.com/in/william-thibaut-stilli-6745013b4" target="_blank" class="link">LinkedIn</a>
          <a href="https://github.com/William-Stilli" target="_blank" class="link">GitHub</a>
        </div>
      </div>

    </div>

    <div class="location-info">
      <p>Basé à <strong>Bienne, Suisse</strong> (Disponible sur Berne/Jura/Neuchâtel)</p>
    </div>
  </div>
</template>

<style scoped>
.contact-container {
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
  padding: 3rem 1rem;
}

h1 {
  font-size: 2.5rem;
  color: #2c3e50;
  margin-bottom: 0.5rem;
}

.subtitle {
  color: #666;
  margin-bottom: 3rem;
  font-size: 1.1rem;
}

.contact-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.card {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.05);
  transition: transform 0.2s;
  border: 1px solid #eee;
}

.card:hover {
  transform: translateY(-5px);
  border-color: #42b883;
}

.icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

h3 {
  margin-bottom: 0.5rem;
  color: #2c3e50;
}

p {
  color: #555;
  margin-bottom: 1.5rem;
}

.actions {
  display: flex;
  gap: 10px;
  justify-content: center;
}

.btn-primary {
  background-color: #42b883;
  color: white;
  padding: 8px 16px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: bold;
  border: none;
  cursor: pointer;
  font-size: 0.9rem;
}

.btn-secondary {
  background-color: transparent;
  color: #666;
  padding: 8px 16px;
  border-radius: 6px;
  border: 1px solid #ccc;
  cursor: pointer;
  font-size: 0.9rem;
}

.btn-secondary:hover {
  border-color: #42b883;
  color: #42b883;
}

.social-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.link {
  color: #2c3e50;
  text-decoration: none;
  font-weight: bold;
  border-bottom: 2px solid #eee;
  padding-bottom: 2px;
}

.link:hover {
  color: #42b883;
  border-color: #42b883;
}

.location-info {
  color: #888;
  font-size: 0.9rem;
  margin-top: 2rem;
}
</style>