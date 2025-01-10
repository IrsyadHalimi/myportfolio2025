<template>
  <nav class=" bg-gray-900 text-white dark:bg-white dark:text-black py-4">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-2xl font-bold">My Portfolio</h1>
      <ul class="flex space-x-6">
        <li>
          <label class="inline-flex items-center cursor-pointer">
            <input type="checkbox" @click="toggleDarkMode" value="" class="sr-only peer">
            <div class="relative w-11 h-6 bg-gray-200 ring-purple-300 dark:ring-gray-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full rtl:peer-checked:after:-translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:start-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-purple-600"></div>
            <span class="text-sm ml-2 font-medium dark:text-gray-900 text-gray-300" :class="{ 'hidden': isDarkMode, 'block': !isDarkMode }">Dark Mode</span>
            <span class="text-sm ml-2 font-medium dark:text-gray-900 text-gray-300" :class="{ 'block': isDarkMode, 'hidden': !isDarkMode }">Light Mode</span>
          </label>
        </li>
        <li><a href="#hero" class="hover:text-blue-400">Home</a></li>
        <li><a href="#projects" class="hover:text-blue-400">Projects</a></li>
        <li><a href="#about" class="hover:text-blue-400">About</a></li>
        <li><a href="#contact" class="hover:text-blue-400">Contact</a></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isDarkMode: localStorage.theme === 'dark' || window.matchMedia('(prefers-color-scheme: dark)').matches,
    };
  },
  mounted() {
    this.applyTheme();
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      this.applyTheme();
    },
    applyTheme() {
      if (this.isDarkMode) {
        localStorage.theme = 'dark';
        document.documentElement.classList.add('dark');
      } else {
        localStorage.theme = 'light';
        document.documentElement.classList.remove('dark');
      }
    },
  },
};
</script>