<template>
  <div class="home">

<h2>Refs</h2>
<p >{{saidOne.name}} - {{ saidOne.age }}</p>
<button @click="updatesaidOne()">update saidOne age</button>
<hr>
<h2>Reactive</h2>
<p >{{saidTwo.name}} - {{ saidTwo.age }}</p>
<button @click="updatesaidTwo()">update saidTwo age</button>
  </div>
</template>

<script>
import { ref,reactive } from 'vue'
// @ is an alias to /src


export default {
  name: 'HomeView',
  setup(){
    const saidOne = ref({name:'said',age:41})
    const saidTwo = reactive({name:'abu motion',age:21})
   const updatesaidOne = () =>{
    saidOne.value.age = 31
   
   }
   const updatesaidTwo = () =>{
    saidTwo.age = 11
   }
       return {
      saidOne,
      updatesaidOne,
      saidTwo,
      updatesaidTwo
      
    }
  } ,
  
}
</script>
