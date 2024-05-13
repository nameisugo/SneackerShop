<script setup>
import Card from './Card.vue'

defineProps({
    items: Array
})

const emit = defineEmits(['addToFavourite', 'addToCart'])
</script>

<template>
  <div class="grid grid-cols-4 gap-5" v-auto-animate>
    <Card
        v-for="item in items"
        :key="item.id"
        :title="item.title"
        :imageUrl="item.imageUrl" 
        :price="item.price"
        :onClickFavourite="() => emit('addToFavourite', item)"
        :onClickAdd="() => emit('addToCart', item)"
        :isFavourite="item.isFavourite"
        :isAdded="item.isAdded"
    />
  </div>
</template>
