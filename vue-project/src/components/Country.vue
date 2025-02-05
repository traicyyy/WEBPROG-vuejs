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
    background-color: #fffc;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 4px 6px #0000001a;
    width: 50%;
    max-width: 300px;
    margin: 20px;
}

.countries-title {
    color: #000000;
    text-align: center;
    font-family: "Proxima Nova Medium",sans-serif;
    text-transform: uppercase;
    font-weight: bold
}

.countries-list {
    list-style: none;
    width: 70%;
    margin: 20px auto;
    justify-content: center;
}

.country-item {
    background: #f5c284;
    color: #0b0505;
    padding: 10px;
    margin: 5px 0;
    border-radius: 5px;
    text-align: center
}
</style>
