<template>
  <select v-model="state.selectedLanguage">
    <option value="es">Español</option>
    <option value="en">Inglés</option>
    <option value="fr">Francés</option>
  </select>
</template>

<script>
export default {
  props: ['state']
};
</script>
