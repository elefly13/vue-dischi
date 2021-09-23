<template>
<div>
  <div class="container py-5">
    <div v-if="!loading" class="row gx-5">
      <div v-for="(disco, index) in filtraDischiList" :key="index" class="col-6 col-md-4 col-lg-2 m-3">
       <MainCard :key="index" :info="disco"/>
      </div>
    </div>
    <Loader v-else />
  </div>
  
</div>
</template>

<script>
import axios from 'axios';
import MainCard from './MainCard.vue'
import Loader from './Loader.vue'
export default {
  name: 'Main',
  components: {
    MainCard,
    Loader
  },
  props:[ "genere"],
  data() {
    return {
      APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      dischiList: [],
      loading: true
      
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
            //  setTimeout( () => {this.loading = false; }, 5000);
            this.loading = false;
            
          })
          .catch( err => {
            console.log("Error ", err);
          })
          
    }
  },
  computed: {
    filtraDischiList() {
        if (this.genere === "Seleziona un genere") {
          return this.dischiList;
        }
        let dischiScelti = this.dischiList.filter( item => {
          return item.genre.includes(this.genere);
        })

        return dischiScelti;
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
