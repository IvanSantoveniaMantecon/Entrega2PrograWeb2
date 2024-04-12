<template>
  <p>{{ greeting }}</p>
</template>

<script>
import { ref, watchEffect } from 'vue';
import { computed } from 'vue';

export default {
  setup() {
    // Importamos la variable reactiva `name` del componente padre
    const { name } = inject('name');

    // Variable reactiva para almacenar el saludo
    const greeting = computed(() => `¡Hola, ${name.value}!`);

    return {
      greeting
    };
  }
};
</script>
