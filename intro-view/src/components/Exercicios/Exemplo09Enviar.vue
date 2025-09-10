<script setup>
import { h } from 'vue';

function validaFormulario(){
    alert('Formulário enviado com sucesso!')
    event.preventDefault() // Previne o comportamento padrão do formulário
}
</script>

<template>
    <h1>Exemplo 09</h1>
    <form action="https://soundcloud.com/zako-in-track" @submit="validaFormulario">
        <input type="text" placeholder="Enviar Formulário" required />
    </form>
</template>