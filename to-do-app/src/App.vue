<template>
  <div>
    <h1>Todo App</h1>
  <AddTask></AddTask><br>
  <store></store>
  </div>
</template>

<script>
import AddTask from './components/AddTask.vue'
export default {
  components: { AddTask  },
  
}
</script>


<style>
  body{
    text-align: center;
  }
</style>