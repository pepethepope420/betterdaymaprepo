<script>
import posts from '@/assets/posts.json'
</script>
<template>
    <main>
      <h2>posts:</h2>
      <div v-for="post in posts" v-bind:key="post" class="postClass">
        <h1>{{ post.title }}</h1>
        <h2>{{ post.author }}</h2>
        <p>{{ post.text }}</p>
      </div>
    </main>
</template>