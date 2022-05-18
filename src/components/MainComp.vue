<template>
<div class="cd-container">
  <HeaderComp @selezioneGenere="riceviGenere" :albums="cardContainer" />
  <main class="d-flex justify-content-center align-items-center">
    <div class="container">
      <div class="cd-container d-flex justify-content-between flex-wrap">
        <CardComp v-for="(card,index) in filterGenres" :key="`card_${index}`"
        :cardItem="card"/>
      </div>
    </div>
  </main>

</div>
</template>

<script>

import axios from 'axios';

import CardComp from './CardComp.vue'
import HeaderComp from './HeaderComp.vue';
export default {
    name: "MainComp",
    data() {
        return {
            baseUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            cardContainer: [],
            genereSelezionato: ''
        };
    },

    components: { CardComp, HeaderComp },

    mounted() {
      this.getApi();
    },

    methods: {
      getApi(){
        axios.get(this.baseUrl)
        .then(r => {
          this.cardContainer = r.data.response;
          console.log(this.cardContainer);
        })
      },

      riceviGenere(genereSelezionato){
        this.genereSelezionato = genereSelezionato;
      },
    },

    computed: {
      filterGenres(){
        let cardContainerFiltered = [];
        if(this.genereSelezionato === ''){
          cardContainerFiltered = this.cardContainer
        } else {
          cardContainerFiltered = this.cardContainer.filter(el => {
            return el.genre.includes(this.genereSelezionato)
          })
        }
        

        return cardContainerFiltered
      }
    }
    
}

</script>

<style lang="scss" scoped>
main {
  height: 100vh;
  background-color: #17212C;

  .container {
    height: 650px; //da de bug
  }
}

</style>