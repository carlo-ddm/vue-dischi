<template>
<div class="cd-card m-2">
  <img :src="cardItem.poster" :alt="cardItem.author">
  <div class="title" >{{cardItem.title}}</div>
  <div>
    <div>{{cardItem.author}}</div>
    <div>{{cardItem.year}}</div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CardComp',
  props: {cardItem: Object}
}
</script>

<style lang="scss" scoped>
@import '../assets/styles/vars';

.cd-card {
  flex-basis: calc(100% / 6);
  height: 300px;
  background-color: $colore-primario;

  img {
    width: 100%;
  }

  .title{
    color: white;
    text-align: center;
    margin: 10px 0;
  }
  div {
    text-align: center;
    color: #605E5D;
  }
}
</style> 