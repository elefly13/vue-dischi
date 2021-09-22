<template>
<div>
  <div class="container py-5">
    <div class="row gx-5">
      <div v-for="(disco, index) in dischiList" :key="index" class="col-6 col-md-4 col-lg-2 m-3">
       <MainCard :info="disco"/>
      </div>
    </div>
  </div>

</div>
</template>

<script>
import axios from 'axios';
import MainCard from './MainCard.vue'
export default {
  name: 'Main',
  components: {
    MainCard
  },
  data() {
    return {
      APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      dischiList: []
      
    }
  },
  created() {
    this.getDischi();
  },
  methods: {
    getDischi() {
      axios
          .get(this.APIUrl)
          .then( resp => {
            // console.log(resp.data);
            this.dischiList = resp.data.response;
            
          })
          
    }
  }

}  

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
div {
  color: black;
}
</style>
