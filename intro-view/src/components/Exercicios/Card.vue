<script setup>
const props = defineProps({
  titulo: String,
  descricao: String,
  imagem: String
})
</script>

<template>
  <div class="card">
    <header class="card-header">
      <img v-if="imagem" :src="imagem" :alt="titulo" class="card-img" />
      <h3>{{ titulo }}</h3>
      <p class="descricao">{{ descricao }}</p>
    </header>
    <main class="card-main">
      <slot>Conteúdo do card</slot>
    </main>
    <footer class="card-footer">
      <slot name="footer">Rodapé padrão</slot>
    </footer>
  </div>
</template>

<style scoped>
.card {
  background: #181c2a;
  border-radius: 14px;
  box-shadow: 0 2px 16px rgba(0,0,0,0.25);
  max-width: 420px;
  width: 100%;
  margin: 1.5rem auto;
  overflow: hidden;
  border: 1.5px solid #3730a3;
}
.card-header {
  background: #23263a;
  color: #e0e7ff;
  padding: 1.2rem 1.5rem 0.7rem 1.5rem;
  text-align: center;
}
.card-img {
  display: block;
  margin: 0 auto 0.7rem auto;
  max-width: 90%;
  max-height: 180px;
  width: auto;
  height: auto;
  object-fit: contain;
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.10);
}
.card-header h3 {
  margin: 0 0 0.3rem 0;
  font-size: 1.3rem;
  font-weight: bold;
  color: #a5b4fc;
}
.card-header .descricao {
  margin: 0;
  font-size: 1rem;
  opacity: 0.85;
  color: #c7d2fe;
}
.card-main {
  padding: 1.2rem 1.5rem;
  color: #e0e7ff;
  font-size: 1.08rem;
}
.card-footer {
  background: #23263a;
  padding: 0.9rem 1.5rem;
  text-align: right;
  font-size: 1rem;
  color: #a5b4fc;
}
</style>
