<template>
  <select v-model="state.selectedLanguage">
    <option value="es">Español</option>
    <option value="en">Inglés</option>
    <option value="fr">Francés</option>
  </select>
</template>

<script>
import { inject } from 'vue';

export default {
  setup() {
    // Importamos el objeto reactivo `state` del componente padre
    const state = inject('state');

    return {
      state
    };
  }
};
</script>
