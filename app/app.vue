<template>
   <div :class="currentClass">
      <img src="./assets/owlglow.svg" alt="owl svg" class="w-[100px] h-[200px] absolute top-[20%] left-[80%] lg:left-[89%]" :class="{ hidden: !nightMode }"/>
      <img src="./assets/customstarsglow.svg" alt="cluster of stars" class="w-[200px] h-[200px] absolute top-[10%] left-[5%] lg:left-[74%]" :class="{ hidden: !nightMode }" />
      <img src="./assets/Suproentextglow.svg" alt="Supr0en text" class="w-[350px] h-[150px] absolute top-[76%] left-[6%]" :class="{hidden: !nightMode}" />
   </div>
   <div id="app">
      <Header />
      <nuxt-page :nightMode="nightMode"/>
      <button @click="toggleNightMode" class="fixed top-[92.4%] lg:top-[92.7%] lg:top-[93.7%] xl:top-[94.7%] left-[87.2%] sm:left-[89.2%] md:left-[90.2%] lg:left-[94.2%] xl:left-[97.2%] w-[50px] h-[50px] border rounded-full"><img :src="buttonSideImageSrc" /></button>
      <Footer :nightMode="nightMode" />
   </div>
</template>

<script>
import Header from '~/components/Header.vue';
import Footer from '~/components/Footer.vue';
import dayImage from '@/assets/daymodebutton.svg';
import nightImage from '@/assets/nightmodebutton.svg';
export default {
   components: {
      Header,
      Footer
   },
   data() {
      return {
         nightMode: false,
      };
   },
   computed: {
      currentClass() {
         return this.nightMode ? 'blueprint-nightmode' : 'blueprint';
      },
      buttonSideImageSrc() {
         return this.nightMode ? dayImage : nightImage; 
      }
   },
   methods: {
      toggleNightMode() {
         this.nightMode = !this.nightMode;
      } 
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
   pointer-events: none;
}
.blueprint-nightmode {
   position: fixed;
   top: 0;
   left: 0;
   width: 100%;
   height: 100%;
   background-color: #0d0d24;
   background-image: linear-gradient(to right, rgba(255, 255, 255, 0.1) 1px, transparent 1px),
                     linear-gradient(to bottom, rgba(255, 255, 255, 0.1) 1px, transparent 1px);
   background-size: 50px 50px;
   z-index: 0;
   pointer-events: none;
}
::-webkit-scrollbar {
   width: 3px;
   height: 3px;
}
::-webkit-scrollbar-track {
   background: transparent;
}
::-webkit-scrollbar-thumb {
   background: rgba(0, 0, 0, 0.2);
   border-radius: 10px;
}
::-webkit-scrollbar-thumb:hover {
   background: rgba(0, 0, 0, 0.5);
}
</style>
