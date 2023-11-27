<template>
  <q-page class="flex flex-center">
    <!-- <img alt="Quasar logo" src="../assets/logo.svg" style="width: 200px; height: 200px"> -->
    <div class="q-pa-md">
      <q-table
        flat bordered
        title="Treats"
        dense
        :rows="rows"
        :columns="columns"
        row-key="name"
      />
    </div>
  </q-page>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const columns = [
  { name: 'userId', align: 'center', label: 'User ID', field: (row)=>row.id },
  { name: 'title', align: 'center', label: 'Title', field: (row)=>row.title },
  { name: 'completed', align: 'center', label: 'Completed', field: (row)=>row.completed },
]
const rows = ref([
  // {
  //   name: 'Frozen Yogurt',
  //   calories: 159,
  //   fat: 6.0,
  // },
  // {
  //   name: 'Ice cream sandwich',
  //   calories: 237,
  //   fat: 9.0,
    
  // },
  // {
  //   name: 'Eclair',
  //   calories: 262,
  //   fat: 16.0,
  // }  
])
onMounted(() => {
  fetch("https://jsonplaceholder.typicode.com/todos")
    .then((res) => {
      return res.json();
    })
    .then((data) => {
      rows.value = data
    })
})
  //  {
  //   data.forEach((todo) => {
  //     const ApiData = `<td>${todo.id}</td><td>${todo.title}</td><td>${
  //       todo.completed ? "Yes" : "No"
  //     }</td>`;
  //     document.querySelector("tbody").insertAdjacentHTML("beforeend", ApiData);
  //   });
  //   console.log(data);
  // }
  // )
</script> 
