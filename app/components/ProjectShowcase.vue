<script>
   const projects = [
      { id: 1, name: "Prokress", github: "https://github.com/Git-Happens-HH", type: 'Group', progress: 'In progress', technologies: ['Java', 'Spring Boot', 'React', 'Tailwind'] }, 
      { id: 2, name: "Portfolio-nuxt", github: "https://github.com/Supr0en/Portfolio-nuxt", type: 'Personal', progress: 'Completed', technologies: ['Vue', 'Tailwind', 'Nuxt'] },
      { id: 3, name: "Kyselypalvelu", github: "https://github.com/Fantastic-6", type: 'Group', progress: 'Completed', technologies: ['Java', 'Spring Boot', 'React'] },
      { id: 4, name: "Game of Life Dashboard", github: "https://github.com/Supr0en/GameOfLifeDashboard", type: 'Personal', progress: 'Paused', technologies: ["Kotlin"]}
   ]
   export default {
      props: {
         nightMode: {
            type: Boolean,
            require: true,
         }
      },
      data() {
         return {
            filterOptions: ['All', 'Personal', 'Group'],
            currentFilterIndex: 0,
            projects: projects,
            isHovered: false,
         };
      },
      computed: {
         filteredItems() {
            if (this.currentFilter === 'All') {
               return this.projects
            }
            return this.projects.filter(project => project.type === this.currentFilter);
         },
         currentFilter() {
            return this.filterOptions[this.currentFilterIndex];
         },
      },
      methods: {
         cycleFilter() {
            this.currentFilterIndex = (this.currentFilterIndex + 1) % this.filterOptions.length;
         },
      },
   };
</script>

<template>
   <div class="flex flex-col justify-center items-center p-10">
      <h2 class="text-4xl" :class="{'text-white': nightMode === true}">Highlight projects</h2>
      <button class="bg-gray-200 border-2 border-solid border-gray-400 px-4 py-1 rounded m-2 hover:bg-gray-100" @click="cycleFilter" >{{ currentFilter }}</button>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-[50px] lg:gap-[52px]">
         <div v-for="project in filteredItems" :key="project.id" >
            <a :href="project.github" target="_blank" >
               <div :title="project.github" class="bg-gray-100 p-4 xl:ml-[-2px] w-[300px] h-[200px] border-2 border-solid rounded flex flex-col justify-between" :class="{
               'border-blue-500': project.progress === 'In progress',
               'border-green-500': project.progress === 'Completed',
               'border-orange-500': project.progress === 'Paused',
               'shadow-on-hover': true,
               'night-mode-shadow': nightMode,
               }"
               @mouseover="isHovered = true"
               @mosueleave="isHovered = false"
               >
               <p class="text-3xl">{{ project.name }}</p>
               <div>
                  <ul class="flex gap-1 flex-wrap"><li class="px-1 border-2 border-solid rounded" v-for="tecnology in project.technologies" :key="tecnology.id">{{ tecnology }}</li></ul>
                  <p>{{project.progress}}</p> 
               </div>
            </div>
            </a>
         </div>
      </div>
   </div>
</template>

<style>
.shadow-on-hover {
  transition: box-shadow 0.3s; /* Smooth transition */
}

.shadow-on-hover:hover {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3); /* Default shadow for hover */
}

.night-mode-shadow:hover {
  box-shadow: 0 4px 10px rgba(255, 255, 255, 0.5); /* White shadow for night mode */
}
</style>
