<template>
  <div class="caixa-slot">
    <h3>Conteúdo do componente:</h3>
    <slot>Conteúdo padrão se nada for passado!</slot>
  </div>
</template>

<script setup>
// Nenhuma lógica JS necessária para slot simples
</script>

<style scoped>
.caixa-slot {
  border: 2px dashed #ff0000;
  border-radius: 8px;
  padding: 1rem;
  margin: 1rem 0;
  background: #000000;
}
</style>
