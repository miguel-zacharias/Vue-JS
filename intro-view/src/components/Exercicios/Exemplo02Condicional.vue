<script setup>

let exibir = true;
let media = 6
let idade = 20
let usuarioLogado = true

let compras = ['Pão', 'Leite', 'Ovos', 'Frutas',]
let produtos =[
    { nome: 'Pão', preco: 3.50, categoria: 'Alimentos' },
    { nome: 'Arroz', preco: 7.00, categoria: 'Alimentos' },
    { nome: 'Feijão', preco: 5.00, categoria: 'Alimentos' },
    { nome: 'Macarrão', preco: 4.50, categoria: 'Alimentos' },
    { nome: 'Pão de Queijo', preco: 6.00, categoria: 'Lanches' },
    { nome: 'Bolo', preco: 8.00, categoria: 'Lanches' },
    { nome: 'Refrigerante', preco: 3.00, categoria: 'Bebidas' },
    { nome: 'Água', preco: 1.50, categoria: 'Bebidas' },]
  
</script>



<template>

    <h1 v-if="exibir">Exemplo 2</h1>
    <p v-if="media >= 7">Parabéns Zé Bunda! Você foi Aprovado</p>
    <p v-else-if="media >= 5">Burro do cacete ta de Recuperação</p>
    <p v-else>Meu Deus você não presta pra nada, Está Reprovado</p>

    <h1>Exercício 2.1</h1>
    <p v-if="usuarioLogado">Bem-Vindo!  Usuário Logado</p>
    <p v-else>Tchau Tchau!  Usuário Deslogado</p>


    <h1>Exercício 2.2</h1>
    <p v-if="   idade >= 0 && idade <= 12">Você é uma Criança</p>
    <p v-else-if="idade >= 13 && idade <= 17">Você é um Adolescente</p>
    <p v-else-if="idade > 17 && idade <= 59">Você é um Adulto</p>
    <p v-else>Você é um Idoso</p>



    <h1>Exercício 3.1</h1>
    
    <ul>

        <li v-for="(compras, index) in compras">{{ index + 1 }}. {{ compras }}</li>

    </ul>


    <h1>Exercício 3.2</h1>
    <ul>

        <li v-for="(produto, index) in produtos">
            {{ index + 1 }}. {{ produto.nome }} - R$ {{ produto.preco.toFixed(2) }} ({{ produto.categoria }})
        </li>
    </ul>
    

</template>

<style scoped>
    ul {
        list-style-type: none;
    }
</style>