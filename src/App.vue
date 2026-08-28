<script setup>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Program from './components/Program.vue'
import EnterpriseSummit from './components/EnterpriseSummit.vue'
import StartupsProgram from './components/StartupsProgram.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen w-full bg-[#121B26] font-[Manrope,sans-serif] overflow-x-hidden selection:bg-[#84FFC1] selection:text-[#121B26] bg-[url('./assets/bg-image.png')] bg-cover bg-no-repeat pb-[50px]">
    <Header />
    <main>
      <Hero />
      <div class="flex flex-col gap-4 mt-4">
        <About />
        <Program />
        <EnterpriseSummit />
        <StartupsProgram />
        <Footer />
      </div>
    </main>
  </div>
</template>

<style></style>
