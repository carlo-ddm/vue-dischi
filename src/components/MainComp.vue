<template>
  <main class="d-flex justify-content-center align-items-center">
    <div class="container">
      <div class="cd-container d-flex justify-content-between flex-wrap">
        <CardComp v-for="(card,index) in cardContainer" :key="`card_${index}`"
        :cardItem="card"
        />
      </div>
    </div>
  </main>
</template>

<script>

import axios from 'axios';

import CardComp from './CardComp.vue'
export default {
    name: "MainComp",
    data() {
        return {
            baseUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            cardContainer: []
        };
    },

    components: { CardComp },

    mounted() {
      this.getApi();
    },

    methods: {
      getApi(){
        axios.get(this.baseUrl)
        .then(r => {
          console.log(r.data.response);
          this.cardContainer = r.data.response;
          console.log(this.cardContainer);
        })
      }
    },
    
}

</script>

<style lang="scss" scoped>
main {
  height: 94vh;
  background-color: #17212C;

  .container {
    height: 650px; //da de bug
  }
}

</style>