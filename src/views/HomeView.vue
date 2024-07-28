<template>
  <div class="home">

home
<p ref="p">My name is {{name}} and my age is {{age}}</p>
<button @click="handleEvent()">click me </button>
  </div>
</template>

<script>
import { ref } from 'vue'
// @ is an alias to /src


export default {
  name: 'HomeView',
  setup(){
    console.log('setuped')
    let name = 'said'
    let age = 21

    const p = ref(null)
    const handleEvent = () => {
      console.log(p,p.value)
      p.value.classList.add('test')
      p.value.textContent ='Hello, Said'
    }

    return {
      name,
      age,
      handleEvent:handleEvent,
      p
    }
  } ,
  
}
</script>
