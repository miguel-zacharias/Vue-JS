
<script setup>
import { ref } from 'vue'
const show = ref(false)
function abrir() { show.value = true }
function fechar() { show.value = false }
</script>

<template>
  <button class="abrir-modal" @click="abrir">Abrir Modal!</button>
  <div v-if="show" class="modal-overlay" @click.self="fechar">
    <div class="modal-content">
      <header class="modal-header">
        <slot name="header">Cabeçalho padrão</slot>
        <button class="fechar" @click="fechar">×</button>
      </header>
      <section class="modal-body">
        <slot>Conteúdo padrão do modal</slot>
      </section>
      <footer class="modal-footer">
        <slot name="footer">Rodapé padrão</slot>
      </footer>
    </div>
  </div>
</template>

<style scoped>
.abrir-modal {
  background: linear-gradient(90deg, #6366f1 0%, #818cf8 100%);
  color: #fff;
  border: none;
  border-radius: 24px;
  padding: 0.7rem 2rem;
  font-size: 1.1rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
  cursor: pointer;
  box-shadow: 0 2px 8px rgba(99,102,241,0.10);
  transition: background 0.2s;
}
.abrir-modal:hover {
  background: linear-gradient(90deg, #818cf8 0%, #6366f1 100%);
}
.modal-overlay {
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(0,0,0,0.45);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}
.modal-content {
  background: #fff;
  border-radius: 16px;
  min-width: 320px;
  max-width: 90vw;
  box-shadow: 0 8px 32px rgba(0,0,0,0.18);
  overflow: hidden;
  animation: modalIn 0.3s;
  position: relative;
}
@keyframes modalIn {
  from { transform: translateY(-40px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}
.modal-header {
  background: #6366f1;
  color: #fff;
  padding: 1rem 1.5rem 1rem 1.5rem;
  font-size: 1.2rem;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.fechar {
  background: none;
  border: none;
  color: #fff;
  font-size: 1.7rem;
  cursor: pointer;
  margin-left: 1rem;
  transition: color 0.2s;
}
.fechar:hover {
  color: #ff5252;
}
.modal-body {
  padding: 1.5rem;
  color: #222;
}
.modal-footer {
  background: #f3f4f6;
  padding: 1rem 1.5rem;
  text-align: right;
}
</style>
