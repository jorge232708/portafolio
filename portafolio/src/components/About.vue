<template>
  <section class="about">
    <div class="about-content">
      <div class="text-content">
        <h2>{{ title }}</h2>
        <p>{{ description }}</p>
      </div>
      <img :src="profileImage" :alt="altText" />
    </div>
  </section>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
  profileImage: {
    type: String,
    default: '/perfilDos.jpg' // Ruta en public/
  },
  altText: {
    type: String,
    default: 'Foto de perfil'
  },
  title: {
    type: String,
    default: 'Sobre mí'
  },
  description: {
    type: String,
    default: 'Soy Joaco, profesor de matematicas fisica, docente por mas de 25 años. Desarrollador frontend & backend. Me apasiona crear experiencias digitales únicas y funcionales. Con una sólida base en Vue.js, DRF, CSS y JavaScript, me especializo en el desarrollo de aplicaciones web que no solo son visualmente atractivas, sino también altamente eficientes y fáciles de usar. Mi enfoque es siempre hacia la mejora continua, buscando optimizar cada proyecto para ofrecer la mejor experiencia al usuario. Constantemente me desafío a optimizar diseños, mejorar la accesibilidad y explorar nuevas tecnologías para ofrecer soluciones innovadoras. Además, tengo un fuerte interés en la estrategia digital y el SEO, lo que me permite potenciar el impacto y visibilidad de cada proyecto que desarrollo.'
  }
});
</script>

<style scoped>
.about {
  padding: 2rem;
  color: #fff;
  max-width: 80%;
  margin: 0 auto; /* Centra el contenedor */
}

.about-content {
  display: grid;
  grid-template-columns: 1fr auto; /* Texto a la izquierda, imagen a la derecha */
  align-items: center;
  gap: 30px;
}

.text-content {
  text-align: justify;
  max-width: 600px;
}

h2 {
  font-size: 3rem; /* Más grande */
  margin-bottom: 2.5rem;
  margin-top: -20px; /* Lo sube visualmente */
}

p {
  font-size: 1.2rem;
}

img {
  width: 300px; /* Imagen más grande */
  height: 300px;
  border-radius: 50%;
  object-fit: cover;
  margin-top: 20px; /* Baja un poco la imagen */
}
</style>
