<template>
  <button class="btn-chamativo">
    <slot>Botão</slot>
  </button>
</template>

<script setup>
// Nenhuma lógica JS necessária para slot simples
</script>

<style scoped>
.btn-chamativo {
  background: linear-gradient(90deg, #ff512f 0%, #dd2476 100%);
  color: #fff;
  border: none;
  border-radius: 32px;
  padding: 0.8rem 2.2rem;
  font-size: 1.2rem;
  font-weight: bold;
  box-shadow: 0 4px 18px rgba(221,36,118,0.18);
  cursor: pointer;
  letter-spacing: 1px;
  transition: transform 0.15s, box-shadow 0.15s, background 0.2s;
  outline: none;
}
.btn-chamativo:hover {
  background: linear-gradient(90deg, #dd2476 0%, #ff512f 100%);
  transform: scale(1.07);
  box-shadow: 0 8px 32px rgba(221,36,118,0.28);
}
</style>
