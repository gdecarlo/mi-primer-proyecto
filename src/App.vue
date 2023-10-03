

<template>
<div v-if="isMounted">
  <button type="button" @click="agregarItem">agregar item</button>
  <!-- <Nt2 :nombre="persona.first_name +' '+persona.last_name" v-for="persona in personas" :key="persona.id"></Nt2> -->

  <div v-for="persona in personas" :key="persona.id">
    <h1>{{ persona.first_name +' '+persona.last_name }}</h1>
  </div>
</div>

  
  
  

</template>

<script setup>
import { onMounted, ref } from 'vue';
// import Nt2 from './components/Nt2.vue';
import axios from 'axios'

const personas = ref([])
const isMounted = ref(false)

onMounted(async ()=>{
   const resultado = await axios("https://random-data-api.com/api/v2/users?size=2")
   console.log(resultado.data)
   personas.value = resultado.data
   isMounted.value = true
})



const agregarItem = ()=> personas.value.push({id:3,nombre:"Jose"})

</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
