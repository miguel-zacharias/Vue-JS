<script setup>
import Exemplo01Interpolacao from './components/Exemplo01Interpolacao.vue';
import Exemplo02Condicional from './components/Exercicios/Exemplo02Condicional.vue';
import Exemplo03For from './components/Exercicios/Exemplo03For.vue';
import Exemplo05Model from './components/Exercicios/Exemplo05Model.vue';
import Exemplo06Classe from './components/Exercicios/Exemplo06Classe.vue';
import Exemplo07Clique from './components/Exercicios/Exemplo07Clique.vue';
import Exemplo08Teclado from './components/Exercicios/Exemplo08Teclado.vue';
import Exemplo09Enviar from './components/Exercicios/Exemplo09Enviar.vue';
import { ref } from 'vue';

import ProductItem from './components/Exercicios/ProductItem.vue';

const produtos = [
  { nome: 'Mouse Gamer', price: 120.99 },
  { nome: 'Teclado Mecânico', price: 299.90 },
  { nome: 'Monitor 24"', price: 899.00 },
  { nome: 'Headset', price: 199.50 }
];

const mensagemCompra = ref('');

function handleBuy(nomeProduto) {
  const msg = `Você comprou ${nomeProduto}.`;
  mensagemCompra.value = msg;
  console.log(msg);
}

import UserCard from './components/Exercicios/Exemplo10Props.vue';
const user = {
  nome: 'Miguel',
  email: 'miguel.odin11@gmail.com',
  idade: 20,
  telefone: '(11) 940742052',
  ativo: true,
}

import ProductCard from './components/Exercicios/Exercicio10Props.vue';
const product = {
  tittle: 'iPhone 15',
  price: 4518.04,
  image: 'https://http2.mlstatic.com/D_NQ_NP_779617-MLA71782867320_092023-O.webp',
  inStock: true,
}

import Exemplo11Emits from './components/Exercicios/Exemplo11Emits.vue'; 
import Exemplo12Slot from './components/Exercicios/Exemplo12Slot.vue';
const totalCliques = ref(0);
function atualizarTotal(Valor) {
  totalCliques.value = Valor;
}
</script>

<template>
  <Exemplo01Interpolacao />
  <Exemplo02Condicional />
  <Exemplo03For />
  <Exemplo05Model />
  <Exemplo06Classe />
  <Exemplo07Clique />
  <Exemplo08Teclado />
  <Exemplo09Enviar />
  <Exemplo10Props />


  <!-- ...outros componentes... -->

  <UserCard :nome="user.nome" :email="user.email" :idade="user.idade" :telefone="user.telefone" :ativo="user.ativo" />
  <ProductCard :tittle="product.tittle" :price="product.price" :image="product.image" :inStock="product.inStock" />


  <Exemplo11Emits @update="atualizarTotal" />
  <p>Total de Cliques: {{ totalCliques }}</p>

  <h2>Exemplo Slot</h2>
  <Exemplo12Slot>
    <p style="color:#6366f1; font-weight:bold;">Este texto está sendo passado via slot!</p>
  </Exemplo12Slot>

  <!-- Exercício 12 -->
  <h2 style="margin-top:2rem">Exercício 12 - Produtos à venda</h2>
  <div style="display: flex; gap: 1rem; flex-wrap: wrap;">
    <ProductItem
      v-for="(produto, idx) in produtos"
      :key="idx"
      :nome="produto.nome"
      :price="produto.price"
      @buy="handleBuy"
    />
  </div>
  <p v-if="mensagemCompra">{{ mensagemCompra }}</p>



  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">Sobre</router-link>
  </nav>
  <router-view />

</template>