<script>
export default {
  data() {
    return {
      contador: 0
    }
  },
  methods: {
    incrementarContador() {
      this.contador++
    },
    decrementarContador() {
      if(this.contador > 0){
        this.contador--
      }
    }
  },
  resetar(){
    this.contador = 0
  },
  mounted() {
    console.log(`O valor inicial do contador é ${this.contador}.`)
  }
}
</script>

<template>
  <button @click="incrementarContador">+</button>
  <button @click="decrementarContador">-</button>
  <button @click="resetar">C</button>
  <p>Valor do contador é: {{ contador }}</p>
</template>

<style scoped>
button {
  font-weight: bold;
  cursor: pointer;
}
</style>
