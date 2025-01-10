<template>
  <div :class="{'dark': isDarkMode}">
    <NavbarSection />
    <HeroSection />
    <ProjectsSection />
    <AboutSection />
    <ContactSection />
    <FooterSection />
  </div>
</template>

<script>
import NavbarSection from './components/NavbarSection.vue'
import HeroSection from './components/HeroSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import AboutSection from './components/AboutSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'

export default {
  components: {
    NavbarSection,
    HeroSection,
    ProjectsSection,
    AboutSection,
    ContactSection,
    FooterSection,
  }
}
</script>

<style>
</style>
