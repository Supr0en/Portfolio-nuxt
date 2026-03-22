<template>
   <div class="flex flex-col xl:flex-row xl:gap-[80px] xl:mt-10 justify-center items-center">
      <nuxt-link id="button" class="sticky xl:absolute px-4 py-1 rounded border-2 border-solid boder-gray-400 xl:mt-20 m-4 top-4 hover:border-black" :class="{'text-white': nightMode}" to="/">Back</nuxt-link>
      <div class="h-fit w-[100vw] sm:h-[1123px] sm:w-[794px] shadow flex flex-col py-4 px-12 sm:py-8 sm:px-24 mb-10 mt-4 bg-white" :class="{'shadow-white': nightMode}">
         <div id="header" class="sm:grid sm:grid-cols-2 sm:grid-rows-4">
            <p class="text-xl font-bold">Ruotsalaienen Erik Alexander</p>
            <p class="sm:text-right hidden sm:block">Ryytimaantie</p>
            <p>Software Developer</p>
            <div class="sm:text-right"><p class="block sm:hidden">Ryytimaantie, Vantaa</p><p class="hidden sm:block">Vantaa</p></div>
            <p></p>
            <p class="sm:text-right">erik.ruotsalainen1@gmail.com</p>
            <p></p>
         </div>
         <hr class="border-1 border-black">
         <div id="profile">
            <p class="text-md font-bold">Profile</p>
            <p>I am 21 years old Software Developer from Vantaa. I am interested in learning
               more in my field and i get easily along with new group and others. I graduated as 
               Software Developer (Information- and communication undergraduate degree) at 
               Business College Helsinki in 2.6.2023. Currently I am 2nd year student at Haaga
               Helia University of Applied Sciences. My previous hobbies have been Volleyball 
               for 5 years and Floorball for one season before quitting to focus on last years of 
               school. <br> <br>
               LinkedIn profiili: <a class="underline text-blue-500" href="https://www.linkedin.com/in/erikruotsalainen/" target="_blank">https://www.linkein.com/in/erikruotsalainen/</a> <br>
               Github Profiili: <a class="underline text-blue-500" href="https://github.com/Supr0en">https://github.com/Supr0en</a> <br> 
            </p>
            <br>
         </div>
         <hr class="border-1 border-black">
         <div id="devstack">
            <p class="text-md font-bold">Software Development languages & libraries </p>
            <div class="lg:w-[60%] ml-1/2 float-right">
               <p>JavaScript & TypeScript, NodeJs, React/React 
               Native, Express, HTML, CSS, SQL/NoSQL and 
               Java/Spring Boot, tailwindcss, Python (course on 
               going) and little experience with C# and .net. </p>
               <br>
            </div>
         </div>
         <br>
         <hr class="border-1 border-black">
         <div id="work-experience">
            <p class="text-md font-bold">Work experience</p>
            <div class="lg:w-[60%] ml-1/2 float-right">
               <p class="text-md font-bold">Komu homes </p><br> 
               <p class="text-sm font-bold">Date: 11.01.2023 – 19.05.2023 </p><br>
               <p>While working at Komu home, my duties 
               included part of the Full Stack open course, 
               implementing and publishing the Webhook 
               executor project to GitHub and npm. Work also 
               included testing and development of the Komu 
               application. Software Development languages 
               and techniques used in the work: JavaScript & 
               TypeScript, React & React Native, NodeJs and 
               Express. Github, Firebase, MongoDB, Expo, 
               Linear, Slack, Mixpanel.</p>  <br> 
            </div>
         </div>
         <br>
         <hr class="border-1 border-black">
         <p>Date: 22.3.2026</p>
      </div>
      <div class="h-fit w-[100vw] sm:h-[1123px] sm:w-[794px] shadow flex flex-col py-4 px-12 sm:py-8 sm:px-24 mb-10 mt-4 bg-white" :class="{'shadow-white': nightMode}">
         <div id="header" class="sm:grid sm:grid-cols-2 sm:grid-rows-4">
            <p class="text-xl font-bold">Ruotsalaienen Erik Alexander</p>
            <p class="sm:text-right hidden sm:block">Ryytimaantie</p>
            <p>Software Developer</p>
            <div class="sm:text-right"><p class="block sm:hidden">Ryytimaantie, Vantaa</p><p class="hidden sm:block">Vantaa</p></div>
            <p></p>
            <p class="sm:text-right">erik.ruotsalainen1@gmail.com</p>
            <p></p>
         </div>
         <hr class="border-1 border-black">
         <div id="langugaes">
            <p class="text-md font-bold">Languages</p>
            <div class="lg:w-[60%] ml-1/2 float-right grid grid-cols-2 mb-3">
               <p>Finnish</p>             <p>- Mothertongue</p>
               <p>English</p>             <p>- Good</p>
               <p>Swedish</p>             <p>- Mediocre</p> 
            </div>
            <br>
         </div>
         <br>
         <hr class="border-1 border-black">
         <div id="Education">
            <p class="text-md font-bold">Educations</p>
            <div class="lg:w-[60%] ml-1/2 float-right lg:grid lg:grid-cols-2 mb-3">
               <p>Primary School</p>             <p>- Otalammen peruskoulu</p>
               <p>Vocational school </p>             <p>- Business College Helsinki</p>
               <p>University of Applied Sciences</p>             <p>- Haaga-Helia University of Applied Sciences</p> 
            </div>
         </div>
         <br>
         <hr class="border-1 border-black">
         <p>Date: 22.3.2026</p>
      </div>
   </div>

</template>

<script>
export default  {
   head() {
      return {
         title: 'CV'
      };
   },
   props: {
      nightMode: {
         type: Boolean,
         require: true,
      }
   },
}
</script>

<style>
#button {
   backdrop-filter: blur(1px);
   transform: scale(1px);
}
</style>
