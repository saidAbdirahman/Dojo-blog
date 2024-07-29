<template>
  <div class="home">
<h1>home</h1>
<div v-if="error">{{error}}</div>
<div v-if="posts.length"><PostList v-if="showposts" :posts="posts" /></div>
<div v-else>Posts loading...</div>
<button @click="showposts = !showposts">toggle</button>
<button @click="posts.pop()">delete post</button>
<!-- cron jobs in vue  -->
    </div>
</template>

<script>

import PostList from '@/components/PostList.vue';
import { ref,reactive, computed, watch, watchEffect, handleError } from 'vue'
import getPosts from '../compasable/getPosts'
// @ is an alias to /src



export default {
  name: 'HomeView',
  components: {PostList},
  setup(){
   const {posts,error,load} = getPosts()
   load()
    const showposts = ref(true)
    
       return {posts,showposts,error}
  } ,
  
  
}
</script>
