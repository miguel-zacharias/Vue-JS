<script setup>

let nomes = ['Miguel', 'João', 'Maria', 'Ana', 'Pedro']
let text = '<p style="text-decoration: underline;">isso aqui é sublinhado</p>'

</script>

<template>
    <h1>Exemplo 03</h1>
    <ul>

        <li v-for="(nome, index) in nomes">{{ index + 1 }}. {{ nome }}</li>

    </ul>
    <div v-html="text"></div>
    <div>{{ text }}</div>
</template>

