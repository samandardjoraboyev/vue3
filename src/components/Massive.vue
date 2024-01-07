<template>
  <section>

    <main class="flex justify-center mt-5 flex-wrap">
        <div v-for="card in dataArr" :key="card.id" class="border-2 mx-2 my-4 border-sky-500 w-80 p-4">
        <div class="flex justify-center">
          <div class="flex flex-col">
            <div class="font-bold">{{ card.title }}</div>
            <h2 class="font-bold">{{card.h}}</h2>
            <div>{{ card.text }}</div>
          </div>
          <div class="h-full">
            <img width=" " :src="card.img" alt="default image">
          </div>
          <router-link to="/about"></router-link>

        </div>
      </div>

    </main>


  </section>

</template>



<script>


export default {
  name:'Card item',
  props:['card-items'],
  components: {
    Card
  },
  data() {
    return {
      card: [
        {
          id: 1,
          title: 'card 1',
          h: 'Nature',
          img: 'https://picsum.photos/1000/1000',
          text: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ab, repellat'
        },
        {
          id: 2,
          title: 'card 2',
          h: 'Country',
          img: 'https://picsum.photos/1000/1000',
          text: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ab, repellat'
        },
        {
          id: 3,
          title: 'card 3',
          h: 'Village',
          img: 'https://picsum.photos/1000/1000',
          text: 'Lorem ipsum , dolor sit amet consectetur adipisicing elit. Ab, repellat'
        },
        {
          id: 4,
          title: 'card 4',
          h: 'Picture',
          img: 'https://picsum.photos/1000/1000',
          text: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ab, repellat'
        },
        {
          id: 5,
          title: 'card 5',
          h: 'State',
          img: 'https://picsum.photos/1000/1000',
          text: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ab, repellat'
        }
      ]

    }
  },


</script>