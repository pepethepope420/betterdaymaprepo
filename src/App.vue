
<template>
  <header>
    <h1>Better Daymap</h1>
    <button v-on:click="addPost()">add post</button>
    <button v-on:click="openLoginMethod()">login</button>
  </header>

  <main>
    <postSection v-if="openLogin == false && postPageAdd == false"></postSection>
    <loginPage v-if="openLogin == true"></loginPage>
    <addPostPage v-if="postPageAdd == true"></addPostPage>
  </main>
</template>

<script>
import loginPage from './components/login-page.vue'
import postSection from './components/post-Section.vue'
import addPostPage from './components/add-post.vue'
export default {
  name: "app",
  components: {
      loginPage,
      postSection,
      addPostPage
  },
  data (){
    return {
      openLogin: false,
      postPageAdd: false
    }
  },
  methods:{
    openLoginMethod (){
      this.openLogin = true
    },
    addPost (){
      this.postPageAdd = true
    }
  }
}
</script>
<style scoped>
.postClass {
  margin: 10px;
  padding: 10px;
  border-style: solid;
  border-color: whitesmoke;
}
</style>
