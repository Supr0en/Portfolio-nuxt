<script>
   const projects = [
      { id: 1, name: "Prokress", github: "https://github.com/Git-Happens-HH", group: true, type: 'group', progress: 'In progress', technologies: ['Java', 'Spring Boot', 'React', 'Tailwind'] }, 
      { id: 2, name: "Portfolio-nuxt", github: "https://github.com/Supr0en/Portfolio-nuxt", group: false, type: 'personal', progress: 'Completed', technologies: ['Vue', 'Tailwind', 'Nuxt'] },
      { id: 3, name: "Kyselypalvelu", github: "https://github.com/Fantastic-6", group: true, type: 'group', progress: 'Completed', technologies: ['Java', 'Spring Boot', 'React'] },
      { id: 4, name: "Game of Life Dashboard", github: "https://github.com/Supr0en/GameOfLifeDashboard", "group": false, type: 'personal', progress: 'Paused', technologies: ["Kotlin"]}
   ]
   export default {
      data() {
         return {
            filterOptions: ['all', 'group', 'personal'],
            currentFilterIndex: 0,
            projects: projects,
         }
      },
      computed: {
         filteredItems() {
            if (this.currentFilter === 'all') {
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
      <h1 class="text-4xl">Highlight projects</h1>
      <button class="bg-gray-400 text-white px-4 py-1 rounded m-2 hover:bg-gray-200" @click="cycleFilter" >{{ currentFilter }}</button>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-[50px] lg:gap-[52px]">
         <div v-for="project in filteredItems" :key="project.id" >
            <a :href="project.github" target="_blank" >
               <div :title="project.github" class="bg-gray-100 p-4 xl:ml-[-2px] w-[300px] h-[200px] border-2 border-solid rounded flex flex-col justify-between" :class="project.group === true ? 'border-blue-500' : 'border-green-500'">
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
