<template>
  <div id="app">
    <Header @search="selectOption"/>
    <Main/>
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
    selectOption(opzioneSelezionata) {
      console.log(opzioneSelezionata);
    }
  }

}
</script>

<style lang="scss">
@import "./style/general.scss";
@import "./style/vars.scss";
 
</style>
