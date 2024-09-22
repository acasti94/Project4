<template>
    <form @submit.prevent="submitForm">
        <h4>What is the ingredient?</h4>
            <input v-model="name" placeholder="ex. ``Bananas, Oranges...``" required />
        <h4>How many do you need?</h4>
            <input v-model.number="quantity" type="number" placeholder="ex. 1, 2, 3, 4..." required />
        <h4>How much does it cost?</h4>
            <input v-model.number="price" type="number" placeholder="ex. 1.99" required />
        <h4>How many calories is the ingredient?</h4>
            <input v-model.number="calories" type="number" placeholder="ex. 40" required />
        <h6></h6>
    <button type="submit">Add Ingredient</button>
    </form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: '',
        quantity: 1,
        price: 0,
        calories: 0
      };
    },
    methods: {
      submitForm() {
        const ingredient = {
          name: this.name,
          quantity: this.quantity,
          price: this.price,
          calories: this.calories
        };
        this.$emit('add-ingredient', ingredient);
        this.name = '';
        this.quantity = 1;
        this.price = 0;
        this.calories = 0;
      }
    }
  };
  </script>
  