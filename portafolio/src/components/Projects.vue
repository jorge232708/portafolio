<template>
  <section class="projects">
    <h2>Mis Proyectos</h2>
    <div class="project-grid">
      <div 
        v-for="project in projects" 
        :key="project.id" 
        class="project-card"
        @click="goToProject(project.link)"
      >
        <img :src="project.image" :alt="project.title" />
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter();

defineProps({
  projects: {
    type: Array,
    default: () => [
      { id: 1, title: 'Portfolio', description: 'Mi portafolio profesional', image: '/images/portfolio.png', link: '/portfolio' },
      { id: 2, title: 'Vue Dashboard', description: 'Panel de control interactivo', image: '/images/dashboard.png', link: '/dashboard' },
      { id: 3, title: 'E-commerce', description: 'Tienda en línea completa', image: '/images/', link: '/' },
      { id: 4, title: 'Blog Personal', description: 'Mi blog personal sobre tecnología', image: '/images/', link: '/' }
    ]
  }
});

const goToProject = (link) => {
  router.push(link);
};
</script>

<style scoped>
.projects {
  padding: 2rem;
  background-color: #002244;
  color: #fff;
}

h2 {
  text-align: center;
  margin-bottom: 1.5rem;
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.project-card {
  background-color: #003366;
  padding: 1rem;
  border-radius: 8px;
  text-align: center;
  cursor: pointer;
  transition: transform 0.3s;
}

.project-card img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 6px;
}

.project-card:hover {
  transform: scale(1.05);
}
</style>
