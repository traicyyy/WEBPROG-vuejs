<template>
  <div class="comments-container">
    <h1 class="comments-title">Comments</h1>
    <ul class="comments-list">
      <li v-for="comment in comments" :key="comment.id" class="comment-item">
        <span class="comment-name">{{ comment.name }}:</span> 
        <span class="comment-text">{{ comment.comment }}</span>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { supabase } from '../lib/supabaseClient'

const comments = ref([])

async function getComments() {
  const { data } = await supabase.from('comments').select()
  comments.value = data
}

onMounted(() => {
  getComments()
})

</script>

<style scoped>
.comments-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-top: 20px;
    background-color: #fffc;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 4px 6px #0000001a;
    width: 50%;
    margin: 20px auto;
}

.comments-title {
  color: white;
  text-align: center;
  color: #db841c;
  font-family: "Proxima Nova Medium", sans-serif;
  font-weight: bold;
}

.comments-list {
  list-style: none;
  padding: 0;
  width: 100%;
}

.comment-item {
  background: #333;
  color: white;
  padding: 10px;
  margin: 5px 0;
  border-radius: 5px;
  display: flex;
  align-items: center;
}

.comment-name {
  font-weight: bold;
  margin-right: 8px;
  color: #ffcc00;
}

.comment-text {
  color: white;
}
</style>
