<template>
  <div class="profile-icon" @click="handleClick">
    <img :src="avatarSrc" :alt="altText" />
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

defineProps({
  avatarSrc: {
    type: String,
    default: '/default-avatar.png' // Imagen por defecto en public/
  },
  altText: {
    type: String,
    default: 'Perfil'
  }
});

const emit = defineEmits(['profileClicked']);

const handleClick = () => {
  emit('profileClicked'); // Dispara evento al hacer clic
};
</script>

<style scoped>
.profile-icon {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.3s;
}

.profile-icon:hover {
  transform: scale(1.1);
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
