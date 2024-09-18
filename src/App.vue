<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import posts from './assets/posts.json'
</script>

<template>
  <header>
    <h1>Better Daymap</h1>
    <button>add post</button>
  </header>

  <main>
    <h2>posts:</h2>
    <div v-for="post in posts" class="postClass">
      <h1>{{ post.title }}</h1>
      <h2>{{ post.author }}</h2>
      <p>{{ post.text }}</p>
    </div>
  </main>
</template>

<style scoped>
.postClass {
  margin: 10px;
  padding: 10px;
  border-style: solid;
  border-color: whitesmoke;
}
</style>
