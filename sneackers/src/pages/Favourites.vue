<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'

import CardList from '../components/CardList.vue'

const favourites = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get(
      'https://e47e951d50f88911.mokky.dev/favourites?_relations=items'
    )

    favourites.value = data.map((obj) => obj.item)
  } catch (err) {
    console.log(err)
  }
})
</script>

<template>
  <CardList :items="favourites" />
</template>
