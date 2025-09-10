<script setup>
const props = defineProps({
    nome: String,
    email: String,
    telefone: String,
    idade: Number,
    ativo: Boolean,
})

</script>

<template>

    <div class="card" v-if="nome">
        <h3>{{ nome }}</h3>
        <p v-if="email">{{ email }}</p>
        <p v-if="telefone">{{ telefone }}</p>
        <span v-if="idade">Idade: {{ idade }} anos</span>
    <div :class="ativo ? 'ativo' : 'inativo'">{{ ativo ? 'Ativo' : 'Inativo' }}</div>
    </div>

</template>

<style scoped>
    .card {
        border: 1px solid #ccc;
        border-radius: 8px;
        padding: 1 rem;
        margin: 1 rem 0;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }
    .ativo {
        color: green;
        font-weight: bold;
    }
    .inativo {
        color: red;
        font-weight: bold;
    }
</style>