<script setup>
import {ref, reactive, onMounted} from 'vue'
import CountryCard from './components/CountryCard.vue'
let countries = reactive([])
let isLoading = ref(true)

onMounted(()=>{
    fetch('https://restcountries.com/v3.1/all?fields=name,capital,flags,population')
    .then(res => res.json())
    .then(data =>{
        console.log(data);
        countries=data
        isLoading.value=false
    })
    .catch(error => console.log('Data Fetching Error', error))
    isLoading.value=false
})

</script>

<template>
    <div class="container mx-auto">
        <h1 class="text-4xl text-green-500 text-center" v-if="isLoading">Loading....</h1>
    
        <div v-else class="grid md:grid-cols-3 lg:grid-cols-4 gap-5">
            <CountryCard v-for="(country, index) in countries" :key="index" :country="country" />
        </div>
    </div>
</template>


<style scoped>

</style>