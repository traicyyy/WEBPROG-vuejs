<template>
  <div>
    <h2>JSONPlaceholder API Demo</h2>

    <div v-if="loading">Loading...</div>
    <div v-if="error">{{ error }}</div>

    <h3>Posts</h3>
    <ul>
      <li v-for="post in posts" :key="post.id">
        {{ post.title }} (ID: {{ post.id }})
        <button @click="editPost(post)">Edit</button>
        <button @click="deletePost(post.id)">Delete</button>
      </li>
    </ul>

    <h3>Add New Post</h3>
    <form @submit.prevent="addPost">
      <input type="text" v-model="newPost.title" placeholder="Title" required />
      <textarea v-model="newPost.body" placeholder="Body" required></textarea>
      <button type="submit">Add Post</button>
    </form>

    <div v-if="editingPost" class="edit-post-container">
      <h3>Edit Post</h3>
      <form @submit.prevent="updatePost">
        <input type="text" v-model="editPostData.title" placeholder="Title" required />
        <textarea v-model="editPostData.body" placeholder="Body" required></textarea>
        <button type="submit">Update Post</button>
        <button @click="cancelEdit">Cancel</button> 
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive, onMounted, computed } from 'vue';
import axios from 'axios';

//export default {
// setup() {
    const posts = ref([]);
    const loading = ref(false);
    const error = ref(null);
    const newPost = reactive({ title: '', body: '' });
    const editingPost = ref(false);
    const editPostData = reactive({ title: '', body: '', id: null }); // Include ID
    const selectedPost = ref(null);


    const fetchPosts = async () => {
      loading.value = true;
      error.value = null;
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
        posts.value = response.data;
      } catch (err) {
        error.value = err.message;
      } finally {
        loading.value = false;
      }
    };

    const addPost = async () => {
      try {
        const response = await axios.post('https://jsonplaceholder.typicode.com/posts', newPost);
        posts.value.push(response.data); // Add to the list
        newPost.title = ''; // Clear form
        newPost.body = '';
      } catch (err) {
        error.value = err.message;
      }
    };

    const deletePost = async (id) => {
      try {
        await axios.delete(`https://jsonplaceholder.typicode.com/posts/${id}`);
        posts.value = posts.value.filter(post => post.id !== id); // Remove from list
      } catch (err) {
        error.value = err.message;
      }
    };

    const editPost = (post) => {
      editingPost.value = true;
      editPostData.title = post.title;
      editPostData.body = post.body;
      editPostData.id = post.id; // Store the ID for the update
      selectedPost.value = post; // Store the original post data
    };

    const updatePost = async () => {
      try {
        const response = await axios.put(`https://jsonplaceholder.typicode.com/posts/${editPostData.id}`, editPostData);

        // Update the post in the array (more efficient than a full refesh)
         const index = posts.value.findIndex(p => p.id === editPostData.id);
         if (index !== -1) {
           posts.value[index] = response.data; // Update with the returned data
         }

        editingPost.value = false;
        selectedPost.value = null;
      } catch (err) {
        error.value = err.message;
      }
    };

    const cancelEdit = () => {
      editingPost.value = false;
      editPostData.title = '';
      editPostData.body = '';
      editPostData.id = null;
      selectedPost.value = null;
    };


    onMounted(fetchPosts);

    /* return {
      posts,
      loading,
      error,
      newPost,
      addPost,
      deletePost,
      editPost,
      updatePost,
      editingPost,
      editPostData,
      cancelEdit,
    }; */
//  },
//};
</script>

<style scoped>
body {
  font-family: "Proxima Nova Medium", sans-serif;
  color: #111;
}

div {
  max-width: 700px;
  margin: 40px auto;
  padding: 20px;
  background-color: #fffc;
  border: 2px black;
  border-radius: 10px;
}

h2 {
  font-family: "Proxima Nova Medium", sans-serif;
  font-size: 28px;
  font-weight: bold;
  text-transform: uppercase;
  color: #111;
  text-align: center;
  margin-bottom: 6px;
}

h3 {
  font-family: "Proxima Nova Medium", sans-serif;
  font-size: 28px;
  font-weight: bold;
  color: #111;
  text-align: center;
  margin-bottom: 6px;
}

ul {
  list-style: disc !important;
  padding-left: 20px;
  color: #000000;
  text-align: left;
  padding: 20px;
  margin: 10px;
}

li::marker {
  color: rgb(0, 0, 0);
  font-size: 1.2em;
  padding: 20px;
}

li { 
  align-items: center;
  gap: 5px;
}

li button {
  margin-left: 5px;
}

form {
  display: flex;
  flex-direction: column;
  gap: 6px;
  max-width: 350px;
  margin: 0 auto;
}

input, textarea {
  width: 100%;
  padding: 4px;
  font-size: 14px;
  border: 1px solid #111;
  background-color: #f9f9f9;
}

textarea {
  resize: vertical; /* Allow vertical resizing */
  min-height: 60px; /* Set a minimum height */
}

button {
  background-color: #e5d48f;
  border: 1px solid black;
  padding: 4px 8px;
  font-size: 12px;
  cursor: pointer;
  text-align: center;
  margin-top: 4px;
}

button:hover {
  background-color: #d4c378;
}

.edit-post-container {
  background-color: transparent;
  border: none;
  padding: 0;
}

</style>