<script setup>
import { ref } from 'vue'

defineProps({
  msg:String,
  stl:{
    type:String,
    required:true
  }
})

const count = ref(0)
const saludo = ref("")

const miCondicion = ()=> count.value < 3
const reset = (nuevoNumero)=> count.value = nuevoNumero

const checkTitle = ()=> count.value < 2?"Hola":"Espere un momento"
</script>

<template>
  <h1>{{ msg }}</h1>
  <h3 :title="checkTitle()" >{{ stl }}</h3>
  <h1>Hola {{ saludo }}</h1>
  <input type="text" v-model="saludo">

  <div class="card">
    <button v-show="miCondicion()" type="button" @click="count++">count is {{ count }}</button>
    <button v-if="count === 3" type="button" @click="reset(-1)">reset</button>
  </div>
  <h1>{{ count }}</h1>

</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
