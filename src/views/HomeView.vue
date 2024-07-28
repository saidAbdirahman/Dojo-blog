<template>
  <div class="home">

home
<p >My name is {{name}} and my age is {{age}}</p>
<button @click="handleEvent()">click me </button>
<button @click="age++">add 1 to age</button>
<input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from 'vue'
// @ is an alias to /src


export default {
  name: 'HomeView',
  setup(){
    console.log('setuped')
    const name =ref('said') 
    const age = ref(21)

    // const p = ref(null)
    const handleEvent = () => {
      name.value = ref('Masoud')
    
    }

    return {
      name,
      age,
      handleEvent:handleEvent,
      
    }
  } ,
  
}
</script>
