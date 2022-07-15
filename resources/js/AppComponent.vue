<template>
<div class="container">
    <h1>App vue component</h1>
<h3>I titoli dei post</h3>
<ul>
    <li
    v-for="post in posts"
    :key="post.id">
    <p>{{post.title}}</p>
    </li>
</ul>
</div>
</template>

<script>
export default {
name:'App',
data(){
return{
    apiUrl:'http://127.0.0.1:8000/api/posts',
    posts:[],
}
},
mounted(){
this.getApiUrl()
},
methods:{
    getApiUrl(){
        axios.get(this.apiUrl)
        .then(r=>{
            this.posts=r.data
        })
    }
}
}
</script>

<style>

</style>
