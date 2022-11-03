<script setup>
  // import HelloWorld from './components/HelloWorld.vue'
  import todo_list from './components/todo_list.vue'
  import todo_item from './components/todo_item.vue';

</script>

<template>
  <div class="text-center w-full">
    <div class="wrapper m-auto mt-5 bg-gray-700 rounded-2xl h-96 w-80">
      <p class="text-3xl">Vue Todo list</p>
      <todo_list></todo_list>
    </div>
  </div>
  
</template>

<style>

</style>
