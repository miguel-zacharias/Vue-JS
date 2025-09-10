<script setup>
import { defineProps, defineEmits } from 'vue'
const props = defineProps({
  nome: String,
  price: Number
})
const emit = defineEmits(['buy'])
function comprar() {
  emit('buy', props.nome)
}
</script>

<template>
  <div class="produto-item">
    <h3>{{ nome }}</h3>
    <p>Preço: R$ {{ price.toFixed(2) }}</p>
    <button @click="comprar">Comprar</button>
  </div>
</template>

<style scoped>
.produto-item {
  border: 1px solid #000000;
  border-radius: 8px;
  padding: 1rem;
  margin-bottom: 1rem;
  background: #001c38;
  max-width: 250px;
}
button {
  background: #22c55e;
  color: #2b2b2b;
  border: none;
  border-radius: 4px;
  padding: 0.5rem 1rem;
  cursor: pointer;
  font-weight: 600;
  margin-top: 0.5rem;
}
button:hover {
  background: #16a34a;
}
</style>
