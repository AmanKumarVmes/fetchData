<template>
  <div class="refetch">
    <h1>Re Fetching Data</h1>
    <button @click="newData">Re-Fetch</button><br />
    <div>
      {{ data }}
      <!-- {{ error }} -->
    </div>
    <br />
    <NuxtLink to="/">Go Back</NuxtLink>
  </div>
</template>
<script setup lang="ts">
const { data } = useNuxtData("preData");
function newData() {
  setTimeout(async () => {
    data.value = await useAsyncData(
      "predata",
      () => $fetch("https://jsonplaceholder.typicode.com/todos/2",
      {
        params:{
            default:data,
            immediate:true,
        }
      })
    )
  }, 2000);
}
</script>
<style setup>
.refetch {
  text-align: center;
}
</style>
