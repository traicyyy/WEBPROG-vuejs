<template>
  <div class="food-item orange">
    <h2>{{ name }}</h2>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'Oranges',
      message: 'I like oranges'
    };
  }
};
</script>

<style scoped>
.food-item.orange {
  border: 2px solid #8B4513;
  display: inline-block;
  margin: 15px;
  padding: 15px;
  background-color: #FFA500;
  color: #000000;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
</style>
