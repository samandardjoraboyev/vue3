<template>
  <!--card start-->

card
  <Card :card="cardData" @cardId1="cardIdFromChild"/>
  <!--card end-->
</template>

<script>

import Card from '@/components/Card.vue'
import cardData from "@/mock/cardData"

export default {
  components: {
    Card,
  },
  data() {
    return {
      cardData,

    }
  },
  methods:{
    cardIdFromChild(e){
      alert(e)
    }
  },

  mounted() {
    this.cardData = this.cardData.card.filter(card => card.id == +this.$route.params.id)
    console.log('this.card', this.cardData)

  }
}
</script>

<style>

  .card {
    display: flex;
    border: 2px solid black;
    margin: 15px;


  }
</style>