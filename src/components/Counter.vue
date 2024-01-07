<template>
  <main class="flex">
    <button class="border-2 bg-green-500" @click="decrement">-</button>
    <div>{{counter}}</div>
    <button class="border-2 bg-green-500" @click="increment">+</button>
  </main>
</template>

<script>

export default {
  data(){
    return{
      counter: 0
    }
  },
  methods:{
    decrement(){
      this.counter--
    },
    increment(){
      this.counter++
    }
  },
}

</script>


<style>

</style>