<template>
  <div class="card" @click="cardClickked(card[0]?.title)">
    <div class="flex text-start flex-col justify-center item-center">
      <h1>{{card[0]?.h}}</h1>
      <h1>{{card[0]?.title}}</h1>
      <h3>{{card[0]?.id}}</h3>
      <p>{{card[0]?.text}}</p>
    </div>
    <img class="m-5" width="200" :src="card[0]?.img" alt="default image">
    <router-link to="/about"></router-link>
  </div>
</template>


<script>
export default {
  name:'Card',
  props:['card'],
  emits:['cardId1'],
  methods:{
    cardClickked(id){
      this.$emit('cardId1', id)
    }
  }
}

</script>

