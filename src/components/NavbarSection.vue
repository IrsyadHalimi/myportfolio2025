<template>
<nav class="fixed top-0 w-full z-50 bg-white text-black dark:bg-black dark:text-white shadow-md py-4">
    <div class="container mx-auto flex justify-between items-center">
      <button
        @click="toggleMenu"
        type="button"
        class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white sm:hidden"
        aria-controls="mobile-menu"
        :aria-expanded="isMenuOpen"
      >
        <span class="sr-only">Open main menu</span>
        <svg v-if="!isMenuOpen" class="block size-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
        </svg>
        <svg v-else class="size-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
          <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
        </svg>
      </button>

      <div class="flex shrink-0 items-center">
        <img class="h-8 w-auto" src="https://tailwindui.com/plus/img/logos/mark.svg?color=indigo&shade=500" alt="Your Company">
      </div>

      <div class="hidden sm:block">
        <div class="flex space-x-4">
            <label class="inline-flex items-center cursor-pointer">
                    <input type="checkbox" @click="toggleDarkMode" value="" class="sr-only peer">
                    <div class="relative w-11 h-6 bg-gray-200 ring-purple-300 dark:ring-gray-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full rtl:peer-checked:after:-translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:start-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-purple-600"></div>
                    <span class="text-sm ml-2 font-medium dark:text-gray-300 text-gray-900" :class="{ 'hidden': isDarkMode, 'block': !isDarkMode }">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.72 9.72 0 0 1 18 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 0 0 3 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 0 0 9.002-5.998Z" />
                    </svg>
                    </span>
                    <span class="text-sm ml-2 font-medium dark:text-gray-300 text-gray-900" :class="{ 'block': isDarkMode, 'hidden': !isDarkMode }">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386-1.591 1.591M21 12h-2.25m-.386 6.364-1.591-1.591M12 18.75V21m-4.773-4.227-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0Z" />
                    </svg>

                    </span>
                </label>
          <a href="#hero" class="nav-link" :class="{ active: currentSection === 'hero' }">Home</a>
          <a href="#about" class="nav-link" :class="{ active: currentSection === 'about' }">About</a>
          <a href="#projects" class="nav-link" :class="{ active: currentSection === 'projects' }">Projects</a>
          <a href="#contact" class="nav-link" :class="{ active: currentSection === 'contact' }">Contact</a>
        </div>
      </div>
    </div>

    <div v-show="isMenuOpen" class="sm:hidden" id="mobile-menu">
      <div class="space-y-1 px-2 pb-3 pt-2">
        <a href="#hero" class="block nav-link" @click="smoothScroll('hero')">Home</a>
        <a href="#about" class="block nav-link" @click="smoothScroll('about')">About</a>
        <a href="#projects" class="block nav-link" @click="smoothScroll('projects')">Projects</a>
        <a href="#contact" class="block nav-link" @click="smoothScroll('contact')">Contact</a>
        <label class="inline-flex items-center cursor-pointer">
        <input type="checkbox" @click="toggleDarkMode" value="" class="sr-only peer">
        <div class="relative w-11 h-6 bg-gray-200 ring-purple-300 dark:ring-gray-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full rtl:peer-checked:after:-translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:start-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-purple-600"></div>
        <span class="text-sm ml-2 font-medium dark:text-gray-300 text-gray-900" :class="{ 'hidden': isDarkMode, 'block': !isDarkMode }">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.72 9.72 0 0 1 18 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 0 0 3 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 0 0 9.002-5.998Z" />
        </svg>
        </span>
        <span class="text-sm ml-2 font-medium dark:text-gray-300 text-gray-900" :class="{ 'block': isDarkMode, 'hidden': !isDarkMode }">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386-1.591 1.591M21 12h-2.25m-.386 6.364-1.591-1.591M12 18.75V21m-4.773-4.227-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0Z" />
        </svg>

        </span>
    </label>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
    data() {
        return {
            isMenuOpen: false,
            currentSection: "hero",
            isDarkMode: localStorage.theme === 'dark' || window.matchMedia('(prefers-color-scheme: dark)').matches,
        };
    },
    mounted() {
        this.setupSmoothScroll();
        this.observeSections();
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
        tooggleMenu() {
            this.isMenuOpen = !this.isMenuOpen;
        },
        smoothScroll(sectionId) {
            const target = document.getElementById(sectionId);
            if (target) {
                target.scrollIntoView({ behavior: "smooth", block: "start" });
            }
            this.isMenuOpen = false;
        },
        setupSmoothScroll() {
            document.querySelectorAll(".nav-link").forEach((link) => {
                link.addEventListener("click", (event) => {
                    event.preventDefault();
                    const targetId = link.getAttribute("href").substring(1);
                    this.smoothScroll(targetId);
                });
            });
        },
        observeSections() {
            const options = {
                root: null,
                rootMargin: "-50% 0px -50% 0px",
                threshold: 0,
            };

            const observer = new IntersectionObserver((entries) => {
                entries.forEach((entry) => {
                    if (entry.isIntersecting) {
                        this.currentSection = entry.target.id;
                    }
                });
            }, options);

            document.querySelectorAll("section").forEach((section) => {
                observer.observe(section);
            });
        },
    },
};
</script>
<style scoped>
    .nav-link {
        cursor: pointer;
        padding: 8px 12px;
        font-weight: 500;
        color: #333;
        text-decoration: none;
        transition: color 0.3s ease;
    }

    .nav-link.active {
        color: #007bff;
        font-weight: bold;
        border-bottom: 2px solid #007bff;
    }
</style>