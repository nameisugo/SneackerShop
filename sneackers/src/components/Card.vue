<script setup>
defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number,
  isFavourite: Boolean,
  isAdded: Boolean,
  onClickFavourite: Function,
  onClickAdd: Function
})

</script>

<template>
  <div
    class="relative bg-white border border-slate-100 rounded-3xl p-8 cursor-pointer transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      :src="!isFavourite ? '/like-1.svg' : '/like-2.svg'"
      alt="Like 1"
      class="absolute top-4 left-4"
      @click="onClickFavourite"
    />
    <img :src="imageUrl" alt="Sneacker" />
    <p class="mt-2">{{ title }}</p>

    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-400">Цена:</span>
        <b>{{ price }} руб.</b>
      </div>

      <img @click="onClickAdd" :src="!isAdded ? '/plus.svg' : '/checked.svg'" alt="Plus" />
    </div>
  </div>
</template>
