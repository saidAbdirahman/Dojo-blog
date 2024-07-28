<template>
  <div class="home">

<input type="text" v-model="search">
<p>search term - {{ search }} </p>
<div v-for="name in matchingNames" :key="name">
  {{ name }}
</div>
  </div>
  <button @click="handleClick()">Stop watching</button>
</template>

<script>

import { ref,reactive, computed, watch, watchEffect, handleError } from 'vue'
// @ is an alias to /src


export default {
  name: 'HomeView',
  setup(){

    const search = ref('')
    const names = ref(['said', 'masoud', 'abdalla', 'ibra'])

    const matchingNames = computed(() => {
      return names.value.filter((name => name.includes(search.value)))
    })
    const stopWatch = watch(search, ()=>{
      console.log('search changed')
    })
    const stopEffect = watchEffect(()=>{
      console.log('watch effect')
    })
    const handleClick = () =>{
      stopEffect()
      stopWatch()
    }
       return { names, search, matchingNames, handleClick }
  } ,
  
}
</script>
