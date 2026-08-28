<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const navItems = [
  { name: 'Home', href: '#' },
  { name: 'Program', href: '#program' },
  { name: 'Partners', href: '#partners' },
  { name: 'Incentives', href: '#register' }
]

const activeItem = ref('Home')

const closeMenu = () => { isMobileMenuOpen.value = false }
</script>

<template>
  <header class="fixed top-[20px] xl:top-[37px] left-1/2 -translate-x-1/2 w-[95vw] xl:w-[1040px] z-50 ">
    <div class="w-full h-[70px] xl:h-[80px] bg-white/5 backdrop-blur-xl border border-white/10 rounded-full flex items-center justify-between px-5 xl:px-[32px] stat-card">

      <a href="#" aria-label="ICT Week 2026 Home">
        <img src="../assets/ict_week_2026.svg" alt="ICT Week 2026" class="h-[32px] xl:h-[42px] object-contain" />
      </a>

      <nav aria-label="Main navigation" class="hidden lg:flex items-center h-[52px] rounded-full px-[6px] gap-[6px]">
        <a
          v-for="item in navItems"
          :key="item.name"
          :href="item.href"
          class="h-full flex items-center px-[24px] rounded-full text-[16px] font-medium leading-[22px] transition-all duration-200"
          :class="activeItem === item.name
            ? 'pill-btn'
            : 'text-[#B5B2B1] hover:text-white'"
          @click="activeItem = item.name"
        >{{ item.name }}</a>
      </nav>

      <div class="hidden lg:flex items-center gap-3">
        <select 
          class="h-[52px] pl-6 pr-10 rounded-full bg-white/5 text-[#B5B2B1] text-[16px] font-medium hover:bg-white/10 transition-colors cursor-pointer outline-none appearance-none bg-no-repeat"
          style="background-image: url('data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 width=%2212%22 height=%228%22 viewBox=%220 0 12 8%22 fill=%22none%22><path d=%22M1 1L6 6L11 1%22 stroke=%22%23B5B2B1%22 stroke-width=%221.5%22 stroke-linecap=%22round%22 stroke-linejoin=%22round%22/></svg>'); background-position: right 16px center;"
          name="lang" 
          id="lang"
        >
        <option value="uz" class="bg-[#1a1a1a] text-white" selected>Uzbek</option>
          <option value="en" class="bg-[#1a1a1a] text-white">English</option>
          <option value="ru" class="bg-[#1a1a1a] text-white">Russian</option>
        </select>
        <a
          href="#register"
          class="h-[52px] px-[24px] rounded-full bg-gradient-to-b from-[#84FFC1] to-[#459B6F] text-[#121B26] text-[16px] font-semibold flex items-center hover:opacity-90 hover:scale-[1.02] transition-all duration-200 shadow-[0_0_0_0_rgba(132,255,193,0.4)] hover:shadow-[0_0_20px_rgba(132,255,193,0.4)]"
        >Register now</a>
      </div>

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
