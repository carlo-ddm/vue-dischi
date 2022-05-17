<template>
<div class="cd-container d-flex justify-content-between flex-wrap">
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>
  <div class="cd-card m-2"></div>

</div>

</template>

<script>
export default {
  name: 'CardComp'
}
</script>

<style lang="scss" scoped>
.cd-card {
  flex-basis: calc(100% / 6);
  height: 300px;
  border: 1px solid white;
}
</style>