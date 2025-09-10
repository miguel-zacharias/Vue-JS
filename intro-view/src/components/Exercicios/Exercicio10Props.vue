<script setup>

    const props2 = defineProps({
     tittle: String,
     price: Number,
     image: String,
     inStock: Boolean,
})
</script>

<template>
    <div class="card">
        <h2>{{ tittle }}</h2>
        <img :src="image" :alt="tittle" width="200" />
        <p>Price: ${{ price }}</p>
        <p :class="inStock ? 'ativo' : 'inativo'">{{ inStock ? 'In Stock' : 'Out of Stock' }}</p>

    </div>
</template>

<style scoped>
    .card{
         border: 1px solid #ccc;
        border-radius: 8px;
        padding: 1 rem;
        margin: 1 rem 0;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }

</style>