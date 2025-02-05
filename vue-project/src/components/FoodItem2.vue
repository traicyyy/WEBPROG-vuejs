<template>
  <div class="food-item banana">
    <h2>{{ name }}</h2>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'Bananas',
      message: 'I like bananas'
    };
  }
};
</script>

<style scoped>
.food-item.banana {
  border: 2px solid #FFD700;
  display: inline-block;
  margin: 15px;
  padding: 15px;
  background-color: #FFEB3B;
  color: #000000;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
</style>
