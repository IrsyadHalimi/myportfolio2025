<template>
  <section id="projects" class="py-16 bg-gray-100 text-black dark:bg-slate-800 dark:text-white">
    <div class="container bg-white dark:bg-slate-800 mx-auto">
      <h2 class="text-3xl font-bold text-center mb-8">My Projects</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="project in projects" :key="project.id" class="bg-white p-6 rounded shadow">
          <h3 class="text-xl font-bold">{{ project.title }}</h3>
          <p class="mt-2 text-gray-700">{{ project.description }}</p>
          <a :href="project.link" target="_blank" class="text-blue-500 mt-4 inline-block">
            View Project
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        { id: 1, title: "Project 1", description: "Description for project 1", link: "#" },
        { id: 2, title: "Project 2", description: "Description for project 2", link: "#" },
        { id: 3, title: "Project 3", description: "Description for project 3", link: "#" },
      ]
    }
  }
}
</script>