<template>
  <main>
    <div
         v-for="card in cardData.card" :key="card.id" class="border-2 mx-2 my-4 border-sky-500 w-80 p-4">
      <div class="flex justify-center">

        <div class="flex flex-col">
          <div class="font-bold">{{ card.title }}</div>
          <h2 class="font-bold">{{card.h}}</h2>
          <div>{{ card.text }}</div>
          <Counter />
        </div>
        <div class="h-full">
          <img width="" :src="card.img" alt="default image">
        </div>

      </div>
    </div>
  </main>
</template>


<script>
import Counter from '@/components/Counter.vue'
export default {
  props:['cardData'],
  components:{
    Counter
  },
  data(){
    return {

    }
  }
}

</script>


<style>

</style>