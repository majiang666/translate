<template>
  <div class="transShow">
    <h2>{{ transRes }}</h2>
  </div>
</template>

<script>
export default {
  name: 'transShow',
  props:['transRes']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .transShow{
    margin-top:50px;
  }
  .transShow h2{
    color:#f60;
  }
</style>
