
<template>
  <header>
    <h1>Better Daymap</h1>
    <button v-on:click="addPost()">add post</button>
    <button v-on:click="openLoginMethod()">login</button>
  </header>

  <main>
    <div v-if="openLogin == false && postPageAdd == false">
        <h2>posts:</h2>
        <div v-for="(post, i) in this.posts" v-bind:key="i">
          <h1>{{ post.title }}</h1>
          <h2>{{ post.author }}</h2>
          <p>{{ post.text }}</p>
        </div>
      </div>
    <loginPage v-if="openLogin == true"></loginPage>
    <div v-if="postPageAdd == true">
      <h2>Add Post:</h2>
      <p>Title</p>
      <input type="text" v-model="title">
      <p>Tags (separate each tag by a commar)</p>
      <input type="text" v-model="tags">
      <p>body</p>
      <input type="text" v-model="body">
      <p></p>
      <button v-on:click="addPostButton()">Post</button>
    </div>
  </main>
</template>

<script>
import postData from './assets/posts.json'
import loginPage from './components/login-page.vue'
export default {
  name: "app",
  components: {
      loginPage,
      postData
  },
  data (){
    return {
      openLogin: false,
      postPageAdd: false,
      title:"",
      tags:"",
      body:"", 
      posts: postData
    }
  },
  methods:{
    openLoginMethod (){
      this.openLogin = true
    },
    addPost (){
      this.postPageAdd = true
    },
    addPostButton () {
        var postCount = 1;
        for (var post in this.posts){
            postCount +=1;
        }
        var newPostName = "post" +postCount;
        this.posts[newPostName] = {
            "title": this.title,
            "text": this.body,
            "author": "testAuthor"
        }
        this.postPageAdd = false;
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
