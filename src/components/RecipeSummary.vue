<template>
    <div>
      <h2>Recipe Summary</h2>
      <p>Sum of Costs: ${{ totalCost }}</p>
      <p>Calories: {{ totalCalories }} cal</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      ingredients: Array
    },
    computed: {
      totalCost() {
        return this.ingredients.reduce((sum, ingredient) => sum + (ingredient.quantity * ingredient.price), 0);
      },
      totalCalories() {
        return this.ingredients.reduce((sum, ingredient) => sum + (ingredient.quantity * ingredient.calories), 0);
      }
    }
  };
  </script>
  