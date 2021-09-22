<template>
<div>
  <div class="card p-3" style="width: 230px; height: 380px;">
    <div class="card-img align-center" style="width: 200px; height: 200px;">
      <img :src="info.poster" :alt="info.title" class="card-img-top " style="width: 200px; height: 200px;">
    </div>
    
    <div class="card-body text-center">
      <h5 class="card-title ">{{info.title}}</h5>
      <p class="card-text">{{info.author}}</p>
      <p class="card-text">{{info.year}}</p>
    </div>
</div>

</div>
</template>

<script>
export default {
  name: 'MainCard',
  props: ['info']
    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/vars.scss";
.card {
  background-color: $primo;
    h5 {
      color:$terzo;
      font-weight: 900;
      text-transform: uppercase;
    }
    p {
      color: $quarto;
    }
}

</style>
