<script setup>
import { ref } from 'vue'
let texto = ref('')

let cadastro = ref({
    nome: '',
    email: '',
    idade: '',
    bio: '',
})


let imc = ref({
    peso: '',
    altura: '',
    resultado: '',
})


let isError = false
let isActive = false
let validacao = false
</script>

<style scoped>

.Iserror {
    color: red;
}
.validacao {
    color: green;
}
.ok {
    color: green;
}
</style>
<template>
    <h1>Exemplo 5</h1>
    <input type="text" v-model="texto" />
    <p>Valor do input: {{ texto }}</p>

    <h1>Exercício 5.1</h1>
    <input type="text" v-model="cadastro.nome" placeholder="Nome" />
    <input type="email" v-model="cadastro.email" placeholder="Email" />
    <input type="number" v-model="cadastro.idade" placeholder="Idade" />
    <textarea v-model="cadastro.bio" placeholder="Bio"></textarea>
    <p>Nome: {{ cadastro.nome }}</p>
    <p>Email: {{ cadastro.email }}</p>
    <p>Idade: {{ cadastro.idade }}</p>
    <p>Bio: {{ cadastro.bio }}</p>


    <h1>Exercício 5.2</h1>
    <input type="number" v-model="imc.peso" placeholder="Peso (kg)" />
    <input type="number" v-model="imc.altura" placeholder="Altura (m)" />
    <button @click="imc.resultado = (imc.peso / (imc.altura * imc.altura)).toFixed(2)">Calcular IMC</button>
    <p v-if="imc.resultado && imc.resultado <= 18.5">Abaixo do peso</p>
    <p v-else-if="imc.resultado > 18.5 && imc.resultado <= 25">Peso normal</p>
    <p v-else-if="imc.resultado > 25 && imc.resultado <= 29.9">Sobrepeso</p>
    <p v-else-if="imc.resultado > 29.9 && imc.resultado <= 34.9">Obesidade</p>
    <p v-else-if="imc.resultado > 34.9 && imc.resultado <= 39.9">Obesidade</p>
    <p v-else-if="imc.resultado > 39.9">Obesidade</p>
    
    <p :class="{
        'ok': isActive,
        'falha': isError,
        'validacao': validacao
    }"></p>
</template>