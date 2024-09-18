
<template>
  <header>
    <h1>Better Daymap</h1>
    <button>add post</button>
    <button v-on:click="posts.toggle(); login.toggle()">login</button>
  </header>

  <main>
    <postSection id="posts"></postSection>
    <loginPage id="login"></loginPage>
  </main>
</template>

<script setup>
import loginPage from './components/login-page.vue'
import postSection from './components/post-Section.vue'

</script>
<style scoped>
.postClass {
  margin: 10px;
  padding: 10px;
  border-style: solid;
  border-color: whitesmoke;
}
</style>
