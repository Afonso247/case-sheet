<template>
  <div class="home">
    <Hero />
    <About />
    <Projects />
    <Skills />
    <Contact />
  </div>
</template>

<script>
import Hero from '@/components/sections/Hero.vue'
import About from '@/components/sections/About.vue'
import Projects from '@/components/sections/Projects.vue'
import Skills from '@/components/sections/Skills.vue'
import Contact from '@/components/sections/Contact.vue'

export default {
  name: 'HomeView',
  components: {
    Hero,
    About,
    Projects,
    Skills,
    Contact,
  },
}
</script>

<style scoped>
.home {
  width: 100%;
}
</style>
