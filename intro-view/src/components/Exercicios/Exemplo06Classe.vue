<script setup>
import { ref } from 'vue'

const isError = ref(false)
const isActive = ref(false)
const validacao = ref(true)
const isDisabled = ref(false)

function setFalha() {
  isError.value = true
  isActive.value = false
  validacao.value = false
  isDisabled.value = true
}

function setOk() {
  isError.value = false
  isActive.value = true
  validacao.value = false
  isDisabled.value = false
}

function setValidacao() {
  isError.value = false
  isActive.value = false
  validacao.value = true
  isDisabled.value = false
}
</script>

<template>
  <p :class="{
        'ok': isActive,
        'falha': isError,
        'validacao': validacao
    }">
    Exemplo de classe dinâmica
  </p>

  
  <br />

  <button @click="setOk">OK</button>
  <button @click="setFalha">Falha</button>
  <button @click="setValidacao">Validar</button>
</template>

<style scoped>
.falha {
  color: red;
}
.validacao {
  color: green;
}
.ok {
  color: green;
}
</style>


