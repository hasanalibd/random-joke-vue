<script setup>
import { defineProps } from 'vue';
defineProps({
    country:Object
})

</script>
<template>
        <div class="bg-base-100 border rounded-md bg-blue-300">
            <div class="flex justify-center">
                <img class="w-[320px] h-[150px]" :src="country.flags.png"/>
            </div>
            <div class="card-body">
                <h2 class="card-title text-xl font-semibold text-center pt-3">{{ country.name.common }}</h2>
                <h2 class="card-title text-xl font-semibold text-center pt-3">{{ country.capital[0] }}</h2>
                <p class="font-medium text-center py-2">{{ country.population }}</p>
            </div>
        </div>
</template>

<style  scoped>

</style>