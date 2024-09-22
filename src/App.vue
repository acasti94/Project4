<script>
import IngredientForm from './components/IngredientForm.vue';
import IngredientList from './components/IngredientList.vue';
import RecipeSummary from './components/RecipeSummary.vue';

export default {
  components: {
    IngredientForm,
    IngredientList,
    RecipeSummary
  },
  data() {
    return {
      ingredients: []
    };
  },
  methods: {
    addIngredient(ingredient) {
      this.ingredients.push(ingredient);
    },
    removeIngredient(index) {
      this.ingredients.splice(index, 1);
    },
    editIngredient(index, updatedIngredient) {
      this.$set(this.ingredients, index, updatedIngredient);
    }
  }
};
</script>

<template>
  <div id="app">
    <h1>Recipe Cost and Calorie Tracker</h1>
    <IngredientForm @add-ingredient="addIngredient" />
    <IngredientList 
      :ingredients="ingredients" 
      @remove-ingredient="removeIngredient"
      @edit-ingredient="editIngredient" 
    />
    <RecipeSummary :ingredients="ingredients" />
  </div>
</template>


