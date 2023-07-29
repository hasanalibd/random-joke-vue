<script setup>
import {ref, reactive} from 'vue'

const joke = reactive({
  value: 'Chuck Norries can do a wheelie on a unicycle.'
})

const image = reactive({
  icon: 'https://cdn-icons-png.flaticon.com/512/185/185034.png'
})

function getAJoke(){
  fetch('https://api.chucknorris.io/jokes/random')
  .then(response => response.json())
  .then(data => {
    joke.value = data.value
    image.icon=data.icon_url
  })
}
</script>

<template>
  <section class="flex flex-col items-center w-[500px]">
    <img :src="image.icon?image.icon:'https://cdn-icons-png.flaticon.com/512/3135/3135715.png'" alt="" class="w-12 py-3">
    <p class="border p-2">{{ joke.value }}</p>
    <button @click="getAJoke()" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded w-48 mt-5">Get a new joke</button>
  </section>
</template>

<style scoped>

</style>
