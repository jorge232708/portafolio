<template>
  <header>
    <router-link to="/">
      <Logo />
    </router-link>
    <NavMenu />
    <SearchMenu />
    <ProfileIcon />
  </header>
</template>

<script setup>
import Logo from './minicomponentes/Logo.vue';
import NavMenu from './minicomponentes/NavMenu.vue';
import SearchMenu from './minicomponentes/SearchBar.vue';
import ProfileIcon from './minicomponentes/ProfileIcon.vue';
</script>

<style scoped>
header {
  position: fixed; /* Hace que se quede arriba */
  top: 0;
  left: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%; /* Que ocupe todo el espacio disponible */
  min-width: 50rem; /* Controla el ancho en rem */
  max-height: 4rem; /* Controla la altura máxima */
  margin: 0; /* Lo centra dentro del contenedor principal */
  background-color: #003366;
}

router-link {
  display: flex;
  align-items: center;
  text-decoration: none;
}

.nav-menu {
  flex-grow: 1;
  max-width: 35rem;
}

.search-menu {
  max-width: 300px;
}

.profile-icon {
  width: 50px;
  height: 50px;
  margin-right: 2.5rem;
}
</style>
