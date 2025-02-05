<template>
  <div class="countries-container">
    <h1 class="countries-title">Countries</h1>
    <ul class="countries-list">
      <li v-for="country in countries" :key="country.id" class="country-item">
        {{ country.name }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { supabase } from '../lib/supabaseClient'

const countries = ref([])

async function getCountries() {
  const { data } = await supabase.from('countries').select()
  countries.value = data
}

onMounted(() => {
  getCountries()
})

</script>

<style scoped>
.countries-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 20px;
  background-color: rgb(255 255 255 / 80%);
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 500px;
}

.countries-title {
  color: #db841c;
  text-align: center;
  font-family: "Proxima Nova Medium", sans-serif;
  text-transform: uppercase;
}

.countries-list {
  list-style: none;
  padding: 0;
  width: 100%;
}

.country-item {
  background: #333;
  color: white;
  padding: 10px;
  margin: 5px 0;
  border-radius: 5px;
  text-align: center;
}
</style>
