<template>
<div class="box-header">
  <div class="logo">
    <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/file-spotify-logo-png-4.png" alt="Logo Spotify">
  </div>

  <select v-model="option" v-on="$emit('search', inputOption)" class="select">
  <option selected>Seleziona un genere</option>
  <option value="Rock">Rock</option>
  <option value="Pop">Pop</option>
  <option value="Jazz">Jazz</option>
  <option value="Metal">Metal</option>
</select>

</div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      inputOption: ""
    }
  }
    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/general.scss";
@import "../style/vars.scss";
.box-header {
  display: flex;
  justify-content: space-between;
  width: 100%;
  height: 80px;
  background-color:$primo;
  padding: 15px 30px;
    .logo {
      width: 50px;
      height: 50px;
     

        img {
          width: 100%;
          
        }
    }
    
}

</style>
