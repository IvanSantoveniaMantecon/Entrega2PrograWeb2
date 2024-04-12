<template>
  <p>{{ greeting }}</p>
</template>

<script>
import { ref, inject } from 'vue';

export default {
  setup() {
    // Importa la variable reactiva `greeting` del componente padre
    const greeting = inject('greeting');

    return {
      greeting
    };
  }
};
</script>
