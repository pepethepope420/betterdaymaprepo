<template>
    <main>
        <h2>Add Post:</h2>
        <p>Title</p>
        <input type="text" v-model="title">
        <p>Tags (separate each tag by a commar)</p>
        <input type="text" v-model="tags">
        <p>body</p>
        <input type="text" v-model="body">
        <p></p>
        <button v-on:click="addPostButton()">Post</button>
    </main>
</template>

<script>
import posts from '@/assets/posts.json'
export default {
    components: {
        posts
    },
    data () {
        return {
            title:"",
            tags:"",
            body:""
        }
    },
    methods: {
        addPostButton () {
            console.log (posts);
            var postCount = 1;
            for (var post in posts){
                postCount +=1;
            }
            console.log (postCount)
            var newPostName = "post" +postCount;
            posts[newPostName] = {
                "title": this.title,
                "text": this.body,
                "author": "testAuthor"
            }
        }
    }
}
</script>