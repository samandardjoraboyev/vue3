<template>
  <section>

    <main >
      <!--      card component start-->
      <CardMain class="flex justify-center mt-5 flex-wrap" :cardData="cardData"/>
<!--      test-->
      <br>
      <Counter />


      <!--      card component end -->

    </main>

    <div class="flex flex-col justify-center items-center">
      <button v-if="!toggle" class="bg-green-500" @click="addCard">Add Card</button>
      <div v-else>
        <div class="flex text-start flex-col justify-center item-center">
          <label for="idCard">card id</label>
          <input v-model="idCardModel" class="w-28" type="number" placeholder="id" id="idCard">

        </div>
        <div class="flex text-start flex-col justify-center item-center">
          <label for="textCard">card text</label>
          <input v-model="textCardModel" class="w-28" type="text" id="textCard" placeholder="text">

        </div>

        <div class="flex text-start flex-col justify-center item-center">
          <label for="titleCard">card text</label>
          <input v-model="titleCardModel" class="w-28" type="text" id="titleCard" placeholder="title">

        </div>
        <div class="flex text-start flex-col justify-center item-center">
          <label for="titleText">card text</label>
          <input v-model="titleTextModel" class="w-28" type="text" id="titleText" placeholder="titleText">

        </div>

        <button v-if="toggle" class="bg-green-500" @click="submitCard">Submit Card</button>

      </div>
    </div>
  </section>

</template>

<script>
import cardData from '@/mock/cardData'
import CardMain from '@/components/MainCard.vue'
import Counter from '@/components/Counter.vue'


export default {
  components:{
    CardMain,
    Counter,
  },
  data() {
    return {
      cardData,
      toggle: false,
      idCardModel: 0,
      textCardModel: '',
      titleCardModel: '',
      titleTextModel: ''
    }
  },
  methods: {
    addCard() {

      this.toggle = !this.toggle

    },
    cardClick(item) {
      console.log('item', item)
      sessionStorage.setItem('card', JSON.stringify(item))
      this.$router.push({
        path: `/about/${item.id}`
      })

    },
    submitCard() {

      let params = {
        id: 0,
        title: '',
        h: '',
        text: ''
      }
      params.id = this.idCardModel
      params.title = this.textCardModel
      params.h = this.titleCardModel
      params.text = this.titleTextModel
      params.img = this.titleTextModel

      this.cardData.card.push(params)
      this.toggle = !this.toggle
    }
  }
}
</script>

<style>
</style>