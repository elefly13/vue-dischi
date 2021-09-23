<template>
  <div id="app">
    <Header @search="selectOption"/>
    <Main :genere="opzioneSelezionata"/>
  </div>
</template>

<script>
import Main from './components/Main.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  
  components: {
    Main,
    Header
  },
  data() {
    return {
      opzioneSelezionata: "",

    }
  },
  methods: {
    selectOption(scelta) {
      console.log(scelta)
      this.opzioneSelezionata = scelta;

      
    }
  }

}
</script>

<style lang="scss">
@import "./style/general.scss";
@import "./style/vars.scss";
 
</style>
