<script>
import AlbumsList from './components/AlbumsList.vue';
import Header from './components/partials/Header.vue';
import Footer from './components/partials/Footer.vue';

export default {
  name: "Albums-Project",
  components: {
    AlbumsList, 
    Header,
    Footer
  
},
};




</script>

<template>
 
<Header />

<AlbumsList />

<Footer />

</template>

<style lang="scss">

</style>
