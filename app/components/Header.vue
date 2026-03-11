<template>
   <div class="max-w-screen h-22 flex justify-between items-center p-4 bg-gray-100">
      <h1 class="text-3xl sm:text-5xl">Erik Ruotsalainen</h1>
      <div class="flex gap-5">
         <nuxt-link class="px-4 py-1 rounded border-2 border-solid border-gray-400 hover:bg-gray-200" to="/cv">CV</nuxt-link>
      </div>
   </div>
</template>

<script>
export default {
   name: 'Header'
};
</script>


