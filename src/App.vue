<script setup>
import { ref, onMounted } from 'vue'

const contador = ref(0)

function incrementarContador() {
  contador.value++
}
function decrementarContador() {
  contador.value--
}
// function maiorOuMenor(){
//   if(contador.value >= 10){
//     return `maior/igual`
    
//   }else{
//     return `menor`
//   }
// }
function resetar(){
  contador.value = 0
}


onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})
</script>

<template>
  <button @click="incrementarContador">+</button>
  <button @click="decrementarContador">-</button>
  <button @click="resetar">C</button>
  <p>Valor do contador é: {{ contador }}</p>
  <div id="vermelho" v-if="contador >= 10">
    Numero maior/igual que dez
  </div>
  <div id="azul" v-else>
  Numero menor que dez
  </div>
</template>

<style scoped>
button {
  font-weight: bold;
  cursor: pointer;
}
#vermelho{
  color: red;
}
#azul{
  color: blue;
}
</style>
