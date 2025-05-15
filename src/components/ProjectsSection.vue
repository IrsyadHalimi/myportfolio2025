<template>
  <section
    id="projects"
    class="py-16 bg-gray-100 text-black dark:bg-slate-800 dark:text-white pattern-lisbon"
  >
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-12">My Projects</h2>

      <div class="grid gap-8 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
        <div
          v-for="project in projects"
          :key="project.id"
          class="bg-white dark:bg-black rounded-2xl shadow-lg hover:shadow-2xl transition-shadow duration-300 overflow-hidden flex flex-col"
        >
          <!-- Screenshot Project -->
          <img
            :src="project.image"
            :alt="project.title"
            class="w-full h-48 object-cover"
          />

          <div class="p-6 flex flex-col justify-between flex-grow">
            <div>
              <h3 class="text-xl font-semibold mb-2">{{ project.title }}</h3>
              <p class="text-gray-700 dark:text-gray-300 text-sm mb-4">
                {{ project.description }}
              </p>

              <!-- Teknologi Logo -->
              <div class="flex flex-wrap gap-2 mt-2">
                <img
                  v-for="(tech, index) in project.technologies"
                  :key="index"
                  :src="tech.logo"
                  :alt="tech.name"
                  class="w-6 h-6"
                  :title="tech.name"
                />
              </div>
            </div>

            <!-- Link to GitHub -->
            <div class="mt-6">
              <a
                :href="project.link"
                target="_blank"
                class="flex items-center gap-2 text-purple-600 hover:text-purple-800 dark:text-purple-400 dark:hover:text-purple-300 transition-colors text-sm font-medium"
              >
                <svg
                  class="w-5 h-5"
                  fill="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M12 .5C5.648.5.5 5.648.5 12c0 5.087 3.292 9.397 7.861 10.922.574.105.784-.25.784-.555v-2.055c-3.2.698-3.877-1.548-3.877-1.548-.523-1.328-1.278-1.682-1.278-1.682-1.045-.714.079-.699.079-.699 1.155.081 1.762 1.186 1.762 1.186 1.028 1.76 2.698 1.252 3.355.957.103-.745.402-1.253.73-1.54-2.554-.291-5.238-1.277-5.238-5.681 0-1.255.448-2.282 1.182-3.086-.119-.291-.513-1.466.112-3.059 0 0 .965-.31 3.162 1.178a10.88 10.88 0 012.884-.388c.978.004 1.963.132 2.884.388 2.195-1.488 3.158-1.178 3.158-1.178.627 1.593.234 2.768.116 3.059.736.804 1.18 1.831 1.18 3.086 0 4.416-2.688 5.386-5.25 5.671.413.354.781 1.059.781 2.133v3.157c0 .308.208.665.788.553C20.713 21.394 24 17.087 24 12 24 5.648 18.352.5 12 .5z"
                  />
                </svg>
                View on GitHub
              </a>
            </div>
          </div>
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
        {
            id: 1,
            title: "Inventory Management System",
            description: "A full-featured inventory and asset management system.",
            image: "/img/Shift-Scheduler1.png",
            link: "https://github.com/username/inventory-system",
            technologies: [
            { name: "Laravel", logo: "https://www.svgrepo.com/show/353985/laravel.svg" },
            { name: "MySQL", logo: "https://www.svgrepo.com/show/373848/mysql.svg" },
            ],
        },
        {
            id: 2,
            title: "Real-time Chat App",
            description: "A Node.js based chat app with WebSocket support.",
            image: "/img/Shift-Scheduler1.png",
            link: "https://github.com/username/chat-app",
            technologies: [
            { name: "Node.js", logo: "https://www.svgrepo.com/show/354119/nodejs-icon.svg" },
            { name: "PostgreSQL", logo: "https://www.svgrepo.com/show/354200/postgresql.svg" },
            ],
        },
        {
            id: 3,
            title: "SIAKAD Clone",
            description: "Academic information system built with CodeIgniter.",
            image: "/img/Shift-Scheduler1.png",
            link: "https://github.com/username/siakad-clone",
            technologies: [
            { name: "CodeIgniter", logo: "https://www.svgrepo.com/show/353579/codeigniter.svg" },
            { name: "MySQL", logo: "https://www.svgrepo.com/show/373848/mysql.svg" },
            ],
        },
        ]
    }
  }
}
</script>