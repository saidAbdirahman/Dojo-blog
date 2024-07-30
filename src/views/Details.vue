<template>
  <h1>Details</h1>
<div v-if="error">{{erorr}}</div>
<div class="post" v-if="post">
    <h3>{{post.title}}</h3>
    <p class="pre">{{post.body}}</p>
</div>
</template>

<script>
import getPost from '@/compasable/getPost';

export default {
    props:['id'],
    setup(props){
        const {post,error,load} = getPost(props.id)
        load()

        return{post,error}
    }

}
</script>

<style>

</style>