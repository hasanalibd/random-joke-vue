<script setup>
import {ref, reactive} from 'vue'

const users = reactive([{
  name: 'Hasan Ali',
  gender: 'Male',
  age: 32,
  email: 'www.hasanali.com',
  phone: '01850030472',
  country: "Bangladesh",
  profile: 'https://cdn-icons-png.flaticon.com/512/3106/3106773.png'
}])


function getUser(){
  fetch('https://randomuser.me/api/?results=50')
  .then(res => res.json())
  .then(data =>{
    data.results.forEach(user =>{
      console.log(user);
      users.push({
        name:user.name.first,
        gender:user.gender,
        age: user.dob.age,
        email: user.email,
        phone: user.phone,
        country: user.location.country,
        profile: user.picture.medium,
      })
    })
  })
}

</script>

<template>
  <section class="container mx-auto">
    <button @click="getUser()" class="btn btn-info my-5">Get Random User</button>
    <div class="grid lg:grid-cols-4 md:grid-cols-2 gap-3">
      <div class="card bg-base-100 shadow-xl" v-for="user in users">
      <figure class="px-5 pt-5">
        <img :src="user.profile" alt="Shoes" class="border-4 border-red-400 rounded-full w-36" />
      </figure>
      <div class="card-body items-center text-center">
        <h2 class="text-2xl">{{ user.name }}</h2>
        <p class="text-xl">Age: {{ user.age }}</p>
        <p class="text-xl">{{ user.country }}</p>
        <p class="text-xl">{{ user.phone }}</p>
        <p class="text-xl">{{ user.email }}</p>
      </div>
    </div>
    </div>
    
  </section>
</template>

<style scoped>

</style>
