<template>
<div class="box-header">
  <div class="logo">
    <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/file-spotify-logo-png-4.png" alt="Logo Spotify">
  </div>
  <label >Seleziona un genere
    <select v-model="inputOption" @change="$emit('search', inputOption)" class="select" >
      <!-- <option v-for="(opzione, index)in opzioni" :key="index">{{ opzione[index] }}</option> -->
      <option >Seleziona un genere</option>
      <option >Rock</option>
      <option >Pop</option>
      <option>Jazz</option>
      <option >Metal</option>
    </select>
  </label>
</div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      inputOption: "",
      // opzioni: [
      //   "Rock",
      //   "Pop",
      //   "Jazz",
      //   "Metal"
      // ],
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
  align-items: center;
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
    label {
      color: $quarto;
      
    }
    
}

</style>
