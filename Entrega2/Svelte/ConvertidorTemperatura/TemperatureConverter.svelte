<script>
  import { writable } from 'svelte/store';

  // Creamos una variable reactiva para almacenar la temperatura en Celsius
  const celsius = writable(0);

  // Creamos una variable reactiva para almacenar la temperatura en Fahrenheit
  const fahrenheit = writable(32);

  // Función para convertir Celsius a Fahrenheit
  function convertCelsiusToFahrenheit() {
    const c = $celsius;
    const f = c * 9 / 5 + 32;
    fahrenheit.set(f);
  }

  // Función para convertir Fahrenheit a Celsius
  function convertFahrenheitToCelsius() {
    const f = $fahrenheit;
    const c = (f - 32) * 5 / 9;
    celsius.set(c);
  }
</script>

<div>
  <h2>Celsius: {$celsius}°C</h2>
  <input type="number" bind:value={$celsius} on:input={convertCelsiusToFahrenheit}>
  
  <h2>Fahrenheit: {$fahrenheit}°F</h2>
  <input type="number" bind:value={$fahrenheit} on:input={convertFahrenheitToCelsius}>
</div>

<style>
  div {
    text-align: center;
    margin-top: 20px;
  }
  
  input {
    margin-top: 10px;
    padding: 5px;
    width: 100px;
  }
</style>
