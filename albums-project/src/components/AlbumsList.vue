
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
      
     this.albumsList = response.data.data
  
   
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
 <main>
    <div class="container">
      <div class="row g-2">
        <div
          class="col-4"
          v-for="(album, index) in albumsList"
          :key="index"
        >
          <div class="card bg-dark p-2" style="width: 18rem;">
            <img
              class="card-img-top"
              :src="album.img_Url"
              :alt="`Cover of ${album.album_name}`"
            />
            <div class="card-body">
           
              <h4 class="card-title text-light">{{ album.album_name }}</h4>
              
              <h5 class="card-title text-light">{{ album.band_name }}</h5>
          
              <p class="card-text text-light">
                {{ album.genre }}, {{ album.drop_year }}
              </p>
            
              <a
                :href="`/albums/${album.id}`"
                class="btn btn-primary"
              >
                Show
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss">
main{background-color: rgb(147, 0, 147);}
</style>