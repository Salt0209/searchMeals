<template>
    <div class="flex flex-col p-8">
  

    </div>
</template>

<script setup>
import {ref,computed, onMounted} from 'vue'
import store from '../store';
import axiosClient from '../axiosClient.js'


const ingredients= ref([])

onMounted(async ()=>{
    const response = await axiosClient.get('/list.php?i=list')
    console.log(response.data)
    ingredients.value = response.data
})
</script>