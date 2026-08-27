<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const navItems = [
  { name: 'Home', href: '#', active: true },
  { name: 'Program', href: '#program', active: false },
  { name: 'Partners', href: '#partners', active: false },
  { name: 'Incentives', href: '#register', active: false }
]

const closeMenu = () => { isMobileMenuOpen.value = false }
</script>

<template>
  <!-- Navbar -->
  <header class="fixed top-[20px] xl:top-[37px] left-1/2 -translate-x-1/2 w-[95vw] xl:w-[1040px] z-50">
    <div class="w-full h-[70px] xl:h-[80px] bg-white/5 backdrop-blur-xl border border-white/10 rounded-full flex items-center justify-between px-5 xl:px-[32px]">

      <!-- Logo -->
      <a href="#" aria-label="ICT Week 2026 Home">
        <img src="../assets/ict_week_2026.svg" alt="ICT Week 2026" class="h-[32px] xl:h-[42px] object-contain" />
      </a>

      <!-- Desktop Nav -->
      <nav aria-label="Main navigation" class="hidden lg:flex items-center h-[52px] bg-white/5 border border-white/10 rounded-full px-[6px] gap-[6px]">
        <a
          v-for="item in navItems"
          :key="item.name"
          :href="item.href"
          class="h-full flex items-center px-[24px] rounded-full text-[16px] font-medium leading-[22px] transition-all duration-200"
          :class="item.active
            ? 'bg-[#01141A] border border-[#84FFC1] text-white font-semibold'
            : 'text-[#B5B2B1] hover:text-white'"
        >{{ item.name }}</a>
      </nav>

      <!-- Desktop CTA -->
      <div class="hidden lg:flex items-center gap-3">
        <button class="h-[52px] px-6 rounded-full bg-white/5 flex items-center gap-2 text-[#B5B2B1] text-[16px] font-medium hover:bg-white/10 transition-colors">
          English
          <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
            <path d="M4 6L8 10L12 6" stroke="#B5B2B1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
        <a
          href="#register"
          class="h-[52px] px-[24px] rounded-full bg-gradient-to-b from-[#84FFC1] to-[#459B6F] text-[#121B26] text-[16px] font-semibold flex items-center hover:opacity-90 hover:scale-[1.02] transition-all duration-200 shadow-[0_0_0_0_rgba(132,255,193,0.4)] hover:shadow-[0_0_20px_rgba(132,255,193,0.4)]"
        >Register now</a>
      </div>

      <!-- Hamburger -->
      <button
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        class="lg:hidden text-white p-2"
        :aria-expanded="isMobileMenuOpen"
        aria-label="Toggle menu"
      >
        <svg v-if="!isMobileMenuOpen" width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M3 12H21M3 6H21M3 18H21" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
        </svg>
        <svg v-else width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M18 6L6 18M6 6L18 18" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <Transition name="fade">
      <div
        v-if="isMobileMenuOpen"
        class="lg:hidden fixed inset-0 top-0 bg-[#010D12]/97 backdrop-blur-2xl pt-24 px-8 z-40 flex flex-col"
      >
        <nav class="flex flex-col gap-6 mt-8">
          <a
            v-for="item in navItems"
            :key="item.name"
            :href="item.href"
            @click="closeMenu"
            class="text-3xl font-bold transition-colors"
            :class="item.active ? 'text-[#84FFC1]' : 'text-white/70 hover:text-white'"
          >{{ item.name }}</a>
        </nav>
        <div class="mt-auto mb-12 flex flex-col gap-4">
          <a
            href="#register"
            @click="closeMenu"
            class="w-full h-[56px] rounded-full bg-gradient-to-b from-[#84FFC1] to-[#459B6F] text-[#121B26] text-xl font-bold flex items-center justify-center"
          >Register now</a>
        </div>
      </div>
    </Transition>
  </header>
</template>

<style scoped>
.fade-enter-active, .fade-leave-active { transition: opacity 0.2s; }
.fade-enter-from, .fade-leave-to { opacity: 0; }
</style>
