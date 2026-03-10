<script>
   const new_date = new Date(); 
   export default {
      name: 'Footer',
      data() {
         return {
            current_year: new_date.getFullYear()
         };
      }
   };
</script>

<template>
   <footer class="flex flex-col justify-center items-center p-10 mb-0">
      <p>Copyright © {{ current_year }} Erik Ruotsalainen</p>
   </footer>
</template>
