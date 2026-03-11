<script>
   const new_date = new Date(); 
   export default {
      name: 'Footer',
      data() {
         return {
            current_year: new_date.getFullYear()
         };
      },
      props: {
         nightMode: {
            type: Boolean,
            require: true,
         }
      },
   };
</script>

<template>
   <footer class="flex flex-col justify-center items-center p-10 mb-0">
      <p :class="{'text-white': nightMode}">Copyright © {{ current_year }} Erik Ruotsalainen</p>
   </footer>
</template>
