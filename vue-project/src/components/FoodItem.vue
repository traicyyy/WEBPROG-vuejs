<template>
  <h1 class="food-title">Food</h1>
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

.food-title {
  font-family: "Proxima Nova Medium", sans-serif;
  font-size: 36px;
  text-align: center;
  color: #db841c;
  margin-top: 20px;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-weight: bold;
}
</style>
