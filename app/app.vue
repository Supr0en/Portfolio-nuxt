<template>
   <div class="blueprint"></div>
   <div id="app">
      <Header />
      <nuxt-page />
      <Footer />
   </div>
</template>

<script>
import Header from '~/components/Header.vue';
import Footer from '~/components/Footer.vue';

export default {
  components: {
    Header,
    Footer
  }
};
</script>
<style>
#app {
   font-family: 'Nunito', sans-serif;
   position: relative;
   z-index: 1;
}
.blueprint {
   position: fixed;
   top: 0;
   left: 0;
   width: 100%;
   height: 100%;
   background-image: linear-gradient(to right, rgba(0, 0, 0, 0.1) 1px, transparent 1px),
                     linear-gradient(to bottom, rgba(0, 0, 0, 0.1) 1px, transparent 1px);
   background-size: 50px 50px; /* Spacing of lines */
   z-index: 0;
}
</style>
