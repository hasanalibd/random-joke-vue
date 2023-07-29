<script setup>
import {ref, reactive, onMounted} from 'vue'
const countries = reactive([
  {name: "Bangladesh", capital: "Dhaka", population: 1675000, flags: 'https://cdn-icons-png.flaticon.com/512/185/185034.png'}
])

function getAllCountries(list = 'All'){
  countries.length = 0
  fetch('https://restcountries.com/v3.1/all?fields=name,capital,flags,population')
  .then(response => response.json())
  .then(data =>{
    if(list == "All"){
    data.forEach(country =>{
      countries.push({
        name:country.name.common,
        capital:country.capital[0],
        flags:country.flags.svg,
        population:country.population
      })
    })
  }else{
    data.filter(c => c.name.common.startsWith(list)).forEach(country =>{
      countries.push({
        name:country.name.common,
        capital:country.capital[0],
        flags:country.flags.svg,
        population:country.population
      })
    })
  }
  })
}


// onMounted((list = 'All') =>{
//   countries.length = 0
//   fetch('https://restcountries.com/v3.1/all?fields=name,capital,flags,population')
//   .then(response => response.json())
//   .then(data =>{
//     if(list == "All"){
//     data.forEach(country =>{
//       countries.push({
//         name:country.name.common,
//         capital:country.capital[0],
//         flags:country.flags.svg,
//         population:country.population
//       })
//     })
//   }else{
//     data.filter(c => c.name.common.startsWith(list)).forEach(country =>{
//       countries.push({
//         name:country.name.common,
//         capital:country.capital[0],
//         flags:country.flags.svg,
//         population:country.population
//       })
//     })
//   }
//   })
// })

</script>

<template>
  <section class="container mx-auto">
    <h1 class="text-2xl">Country List</h1>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded w-48 m-1" @click="getAllCountries()">
      List of Countries
    </button>
    <br>
    <div>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('A')">
      A
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('B')">
        B
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('C')">
        C
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('D')">
        D
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('E')">
        E
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('F')">
        F
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('G')">
        G
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('H')">
        H
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('I')">
        I
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('J')">
        J
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('K')">
        K
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('L')">
        L
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('M')">
        M
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('N')">
        N
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('O')">
        O
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('P')">
        P
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('Q')">
        Q
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('R')">
        R
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('S')">
        S
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('T')">
        T
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('U')">
        U
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('V')">
        V
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('W')">
        W
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('X')">
        X
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('Y')">
        Y
      </button>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded  m-1" @click="getAllCountries('Z')">
        Z
      </button>
    </div>
 
    <div class="grid lg:grid-cols-5 md:grid-cols-3 sm:grid-cols-2">
      <div class="border p-3 m-2 rounded-lg bg-slate-200" v-for="country in countries">
        <img class="w-[350px] h-[140px] mx-auto" :src="country.flags?country.flags : 'no flags'" alt="">
        <h2 class="text-xl font-semibold">{{ country.name }}</h2>
        <h2 class="text-xl font-normal">{{ country.capital }}</h2>
        <p class="text-xl font-normal">{{ country.population }}</p>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>
