<template>
  <header>
    <div class="cd-container d-flex justify-content-between">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 167.5 167.5" class="spotify-logo"><title>Spotify</title><path fill="#2e994a" d="M83.7 0C37.5 0 0 37.5 0 83.7c0 46.3 37.5 83.7 83.7 83.7 46.3 0 83.7-37.5 83.7-83.7S130 0 83.7 0zM122 120.8c-1.4 2.5-4.6 3.2-7 1.7-19.8-12-44.5-14.7-73.7-8-2.8.5-5.6-1.2-6.2-4-.2-2.8 1.5-5.6 4-6.2 32-7.3 59.6-4.2 81.6 9.3 2.6 1.5 3.4 4.7 1.8 7.2zM132.5 98c-2 3-6 4-9 2.2-22.5-14-56.8-18-83.4-9.8-3.2 1-7-1-8-4.3s1-7 4.6-8c30.4-9 68.2-4.5 94 11 3 2 4 6 2 9zm1-23.8c-27-16-71.6-17.5-97.4-9.7-4 1.3-8.2-1-9.5-5.2-1.3-4 1-8.5 5.2-9.8 29.6-9 78.8-7.2 109.8 11.2 3.7 2.2 5 7 2.7 10.7-2 3.8-7 5-10.6 2.8z"/></svg>
      <select
      v-model="genereSelezionato"
      @change="$emit('selezioneGenere', genereSelezionato)" name="" id="">
        <!-- <option v-for="(album, index) in newSelect" :key="`generi_${index}`" value="album.genre">{{newSelect.genre}}</option> -->
        <option value="">Seleziona Genere</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data(){
    return {
      genereSelezionato: ''
      // newSelect: [],
    }
  },

  props: {
    albums: Array
  },

  methods: {
    // genresPush (){
    //   this.albums.forEach(album => {
    //     if(!this.newSelect.includes(album.genre)){
    //       this.newSelect.push(album.genre)
    //     } 
    //   });
    //   console.log('stocazzo',this.newSelect);
    // }
  },

  mounted() {
    // this.genresPush()
  },

}


</script>

<style lang="scss" scoped>
@import '../assets/styles/_vars.scss';
.cd-container {
  width: 100%;
  height: 6vh;
  background-color: $colore-primario;

  svg {
    margin: 10px;
  }

  select {
    margin: 10px;
    padding: 5px;
    color: gray;
    border-radius: 5px;
    font-size: 15px;
  }
}

</style>