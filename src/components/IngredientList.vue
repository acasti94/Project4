<template>
    <ul>
      <li v-for="(ingredient, index) in ingredients" :key="index">
        {{ ingredient.name }} - 
        {{ ingredient.quantity }} units for ${{ ingredient.price }} each - {{ ingredient.calories }} calories each
      </li>

      <button @click="$emit('remove-ingredient', index)">Remove</button>
    </ul>
  </template>
  
  <script>
  export default {
    props: {
      ingredients: Array
    }
  };
  </script>
  