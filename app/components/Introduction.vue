<script>
   const new_date = new Date(); 
   const age = new_date.getFullYear() - 2004;
   export default {
      props: {
         nightMode: {
            type: Boolean,
            require: true,
         }
      },
      data() {
         return {
            age: age,
            email: "erik.ruotsalainen1@gmail.com",
         };
      },
      methods: {
         async copyEmail() {
            try {
               await navigator.clipboard.writeText(this.email);
               alert("Email copied to clipboard");
            } catch (error) {
               alert("Copying email to clipboard failed");
            }
         }
      }
   };
</script>

<template>
   <div class="flex justify-center items-center p-10 xl:mr-[230px] xl:ml-[-52px]">
      <img class="lg:mr-[40px] max-w-[240px] max-h-[360px] rounded hidden lg:block" src="/assets/Photo.jpg" alt="Photo" />
      <div class="min-w-[360px] md:min-w-[660px] lg:max-w-[705px] min-h-[300px] mx-10 shadow-2xl px-5 py-5 rounded flex flex-col bg-white" :class="{
         'shadow-white shadow-lg': nightMode === true
         }">
         <p class="text-2xl">Hello and welcome to my portfolio.</p>
         <hr>
         <div>
            <p class="text-md">
               I am {{ age - 1 }} year-old Software Developer with focus on web development from Vantaa, Finland.
               Currently studying in Haaga-Helia University of Applied Science, before it graduated from Business College Helsinki as Software Developer (Web development) <br>
               and completed military service.
            </p>
            <br>
            <p class="text-md">
               My Software Development experience is mostly in Front-end Development using React, from Haaga-Helia i have gotten experience using Java 
               with Spring Boot to create Back-end services and knowledge of SQL design and development + Software testing.
            </p>
         </div>
         <div class="flex gap-4 justify-center items-center pt-2">
            <a href="https://github.com/Supr0en" target="_blank" >
               <Icon name="uil:github" class="w-10 h-10 bg-black hover:bg-gray-300" title="Open Github profile"/>
            </a>
            <a href="https://www.linkedin.com/in/erikruotsalainen/" target="_blank" >
               <Icon name="uil:linkedin" class="w-10 h-10 bg-[#0077B5] hover:bg-blue-300" title="Open LinkedIn profile"/>
            </a>
            <div @click="copyEmail">
               <Icon name="mdi:email" class="w-10 h-10 bg-gray-400 hover:bg-gray-300" title="Copy Email"/>
            </div>
         </div> 
      </div>
   </div>
</template>
<style>
</style>
