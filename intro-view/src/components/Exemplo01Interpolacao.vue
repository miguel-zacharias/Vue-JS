<script setup>
import { ref } from 'vue'

const nome = ref('Miguel')
const num1 = ref(20)
const num2 = ref(33)

const nome1 = ref('João')
const idade = ref(25)
const profissao = ref('Programador')

const a = ref(15)
const b = ref(25)

const data = new Date()
const dia = String(data.getDate()).padStart(2, '0')
const mes = String(data.getMonth() + 1).padStart(2, '0')
const ano = data.getFullYear()
const dataFormatada = ref(`${dia}/${mes}/${ano}`)
</script>

<template>
  <h1>Exemplo 1</h1>
  <br />
  <p>O seu nome é: {{ nome }}</p>
  <p>A soma de {{ num1 }} + {{ num2 }} é igual a: {{ num1 + num2 }}</p>
  <br />

  <div>
    <h1>Exercício 1.1</h1>
    <p>Meu nome é {{ nome1 }}, tenho {{ idade }} anos, e sou {{ profissao }}</p>
  </div>

  <br />

  <div>
    <h1>Exercício 1.2</h1>
    <p>A soma de {{ a }} + {{ b }} é igual à: {{ a + b }}</p>
    <p>A subtração de {{ a }} - {{ b }} é igual à: {{ a - b }}</p>
    <p>A multiplicação de {{ a }} * {{ b }} é igual à: {{ a * b }}</p>
    <p>A divisão de {{ a }} / {{ b }} é igual à: {{ a / b }}</p>
  </div>

  <br />

  <div>
    <h1>Exercício 1.3</h1>
    <p>A data atual é: {{ dataFormatada }}</p>
  </div>
</template>
