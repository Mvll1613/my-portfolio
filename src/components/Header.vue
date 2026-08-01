<template>
  <header class="flex w-full justify-between items-center pt-6 pb-6 pr-20 pl-20 background-black fixed z-100">
    <img
      src="/logo-white.png"
      alt="logo"
      class="w-12 h-12"
    >

    <nav class="flex gap-16 text-white">
      <a
        href="#home"
        :class="['text-2xl hover:text-blue-400 transition-colors duration-200 ease-in-out', { 'text-blue-400': activeSection === 'home' }]"
      >
        Home
      </a>
      <a
        href="#about"
        :class="['text-2xl hover:text-blue-400 transition-colors duration-200 ease-in-out', { 'text-blue-400': activeSection === 'about' }]"
      >
        About
      </a>
      <a
        href="#projects"
        :class="['text-2xl hover:text-blue-400 transition-colors duration-200 ease-in-out', { 'text-blue-400': activeSection === 'projects' }]"
      >
        Projects
      </a>
      <a
        href="#contact"
        :class="['text-2xl hover:text-blue-400 transition-colors duration-200 ease-in-out', { 'text-blue-400': activeSection === 'contact' }]"
      >
        Contact
      </a>
    </nav>
  </header>
</template>

<script setup lang="ts">
  import { ref, onMounted, onBeforeUnmount } from 'vue'

  const activeSection = ref('home')

  const handleScroll = () => {
    const sections = ['home', 'about', 'projects', 'contact']
    const scrollPosition = window.scrollY + 100 // 100 is the number of the approx Header's height

    for (const section of sections) {
      const element = document.getElementById(section)
      if (element) {
        const { offsetTop, offsetHeight } = element
        if (scrollPosition >= offsetTop && scrollPosition < offsetTop + offsetHeight) {
          activeSection.value = section
          break
        }
      }
    }
  }

  onMounted(() => {
    window.addEventListener('scroll', handleScroll)
    handleScroll()
  })

  onBeforeUnmount(() => {
    window.removeEventListener('scroll', handleScroll)
  })
</script>
