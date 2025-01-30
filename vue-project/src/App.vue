<template>
  <h1 style="color: white;">Food</h1>
  <ul style="color: white; list-style-type: disc;">
    <li v-for="country in countries" :key="country.id">{{ country.name }}</li>
  </ul>
  <food-item/> 
  <food-item2/> 
  <food-item/> <br>
  <personal-profile/> <br>
</template>

<script setup>
  import { ref, onMounted } from 'vue'
  import { supabase } from './lib/supabaseClient'

  const countries = ref([])

  async function getCountries() {
    const { data } = await supabase.from('countries').select()
    countries.value = data
  }

  onMounted(() => {
    getCountries()
  })
  </script>


<style>
</style>  