<template>
  <nav class="nav-menu">
    <ul>
      <li v-for="link in links" :key="link.text">
        <router-link :to="link.href">{{ link.text }}</router-link>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
  links: {
    type: Array,
    default: () => [
      { text: 'Inicio', href: '/' },
      { text: 'Proyectos', href: '/projects' },
      { text: 'Sobre mí', href: '/about' },
      { text: 'Contacto', href: '/contact' }
    ]
  }
});
</script>

<style scoped>
.nav-menu {
  display: flex;
  justify-content:space-around;
  padding: 0.5rem;
}

ul {
  display: flex;
  gap: 6rem;
  list-style: none;
  padding: 0;
}

li a {
  color: #fff;
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s;
}

li a:hover {
  color: #64b5ff;
}
</style>
