<template>
  <p>{{ greeting }}</p>
</template>

<script>
import { inject } from 'vue';

export default {
  setup() {
    // Importamos la variable computada `greeting` del componente padre
    const greeting = inject('greeting');

    return {
      greeting
    };
  }
};
</script>
