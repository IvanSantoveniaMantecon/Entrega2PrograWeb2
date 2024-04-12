<template>
  <select v-model="selectedLanguage">
    <option value="es">Español</option>
    <option value="en">Inglés</option>
    <option value="fr">Francés</option>
  </select>
</template>

<script>
export default {
  setup() {
    // No necesitamos variables reactivas en este componente
    return {
      selectedLanguage: 'es' // Por defecto, seleccionamos el español
    };
  }
};
</script>
