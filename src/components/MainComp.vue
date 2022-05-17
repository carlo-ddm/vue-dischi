<template>
  <main class="d-flex justify-content-center align-items-center">
    <div class="container">
      <CardComp />
    </div>
  </main>
</template>

<script>
// import '../assets/data/chiamata/'
import CardComp from './CardComp.vue'
export default {
    name: "MainComp",
    // data() {
    //     return {
    //         chiamata
    //     };
    // },
    components: { CardComp }
}

</script>

<style lang="scss" scoped>
main {
  height: 94vh;
  background-color: #17212C;

  .container {
    border: 2px solid white;
    height: 650px; //da de bug
  }
}

</style>