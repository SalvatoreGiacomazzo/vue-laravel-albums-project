
<script>

import axios from 'axios';

export default {
  name: "AlbumsList",

  data(){
    return {
        albumsList : [],

    }

    },  methods:{
getAlbumsList(){
    axios.get('http://127.0.0.1:8000/api/albums')
  .then ((response) =>{
      
          this.albumList = response.data.results
  
   
  })
  .catch(function (error) {
   
    console.log(error);
  })




}


}, mounted(){
    this.getAlbumsList();
}



};
</script>

<template>
  <div>
    <h1>Hello MainContent!</h1>
  </div>
</template>

<style lang="scss">
h1 {
  color: red;
}
</style>