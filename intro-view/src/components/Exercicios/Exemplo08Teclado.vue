<script setup>
import { ref } from 'vue'
let inputValue = ref('')
let teclaPressionada = ref('')
let contadorEspaco = ref(0)

function mensagem() {
  alert(`Executando a função: ${inputValue.value}`)
}

function mostrarTecla(event) {
  teclaPressionada.value = event.key
}

function contarEspaco(event) {
  if (event.code === 'Space') {
    contadorEspaco.value++
  }
}
</script>

<template>
  <h1>Exemplo 8</h1>
  <input type="text" @keyup.enter="mensagem" v-model="inputValue" placeholder="Pressione Enter" />

  <h1>Exemplo 8.1 - keydown</h1>
  <input type="text" @keydown="mostrarTecla" placeholder="Digite algo..." />
  <p>Última tecla pressionada: <strong>{{ teclaPressionada }}</strong></p>

  <h1>Exemplo 8.2 - keypress</h1>
  <input type="text" @keypress="contarEspaco" placeholder="Pressione espaço..." />
  <p>Espaços pressionados: <strong>{{ contadorEspaco }}</strong></p>
</template>