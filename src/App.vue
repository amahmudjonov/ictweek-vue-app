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
  <div class="min-h-screen w-full bg-[#121B26] font-[Manrope,sans-serif] overflow-x-hidden selection:bg-[#84FFC1] selection:text-[#121B26]">
    <Header />

    <main>
      <!-- Section 1: Hero (full-bleed background) -->
      <Hero />

      <!-- All subsequent content sections — each has mt-4 (16px gap) to replicate Figma spacing  -->
      <div class="flex flex-col gap-4 mt-4">
        <!-- Section 2: "Save your spot today!" -->
        <About />

        <!-- Section 3: "Past Attendees Include" -->
        <Program />

        <!-- Section 4: "Enterprise Uzbekistan Summit" (tabs) -->
        <EnterpriseSummit />

        <!-- Section 5: "Digital Startups Program" -->
        <StartupsProgram />

        <!-- Section 6+7: "Our Partners" + Registration Form -->
        <Footer />
      </div>
    </main>

    <!-- Page bottom padding -->
    <div class="h-16 xl:h-20"></div>
  </div>
</template>

<style>
html { scroll-behavior: smooth; }
</style>
