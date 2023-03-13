<script setup>
import { ref, onMounted } from 'vue'

const nome = 'Eduardo'
const idade = 17
function inverter(texto) {
  return texto.split('').reverse().join('')
}
function inverterMaiusculo(texto) {
  return inverter(texto).toUpperCase()
}
function saudacao() {
  return `Olá, ${nome}!`
}

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
function resetar() {
  contador.value = 0
}


onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})
</script>

<template>
  <div class="info">
    <h1>Exemplo 1 - Mostrando informações na tela</h1>
    <p>Nome: {{ nome }} </p>
    <p>Idade: {{ idade }} anos</p>
    <hr />
    <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p>O nome tem {{ nome.length }} caracteres</p>
    <p>O nome invertido é: {{ inverter(nome) }} </p>
    <p>O nome invertido em maisculo é: {{ inverterMaiusculo(nome) }} </p>
    <hr />
    <p> Exemplo de saudação usando função</p>
    <p> {{ saudacao() }} </p>
    <hr />
    <button @click="incrementarContador">+</button>
    <button @click="decrementarContador">-</button>
    <button @click="resetar">C</button>
    <p>Valor do contador é: {{ contador }}</p>
    <div id="vermelho" v-if="contador > 10">
      O numero maior que 10
    </div>
    <div id="azul" v-else-if="contador < 10">
      O numero menor que 10
    </div>
    <div v-else>
      O numero é 10
    </div>
    <hr />
    <div v-if="contador % 2 === 0">
      É par
    </div>
    <div v-else>
      É ímpar
    </div>
  </div>
</template>

<style scoped>


button {
  font-weight: bold;
  cursor: pointer;
}

#vermelho {
  color: red;
}

#azul {
  color: green;
}

.info {
  background-color: rgba(35, 12, 22, 1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>
