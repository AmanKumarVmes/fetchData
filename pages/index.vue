<template>
    <div class="fetch">
        <h1>Fetching Data</h1>
    <br>
    <div>
       {{ data }}
    </div>
   <NuxtLink to="/second">Second</NuxtLink>
    </div>

</template>
<script setup lang="ts">


const {data} =await  useFetch(`https://jsonplaceholder.typicode.com/todos/1`,{key:'preData'})
</script>
<style>
    .fetch{
        text-align: center;
    }
</style>
