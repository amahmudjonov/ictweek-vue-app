<script setup>
// "DIGITAL STARTUPS PROGRAM" section — 1280x800
// Large background image (CAEx photo), gradient top bar, feature grid, navigation buttons
</script>

<template>
  <section class="w-full py-[20px] xl:py-[0px]" aria-label="Digital Startups Program section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <!-- Card: 1280x800, rgba(18,27,38,0.4), borderRadius 24px, padding 36px, gap 32px -->
      <div class="w-full bg-[#121B26]/40 rounded-[24px] flex flex-col items-center gap-[32px] p-[24px] xl:p-[36px]">

        <!-- Image frame: 1208x624 (inner), borderRadius 16px, overflow hidden -->
        <div class="w-full rounded-[16px] overflow-hidden relative h-[300px] md:h-[450px] xl:h-[624px]">
          <img
            src="../assets/summit_bg.png"
            alt="CAEx Summit venue at night"
            class="w-full h-full object-cover"
            loading="lazy"
          />
          <!-- Top gradient bar: linear-gradient from #84FFC1 to transparent -->
          <div class="absolute top-0 left-0 right-0 h-[58px] bg-gradient-to-r from-[#84FFC1] to-transparent opacity-80"></div>

          <!-- Feature grid overlay -->
          <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-[#204476]/80 to-transparent p-[24px] xl:p-[36px]">
            <div class="grid grid-cols-2 xl:grid-cols-4 gap-3 xl:gap-4">
              <div class="bg-white/10 backdrop-blur-md border border-white/10 rounded-[16px] p-[16px]">
                <span class="text-[#84FFC1] text-[22px] xl:text-[28px] font-bold">$100M+</span>
                <p class="text-white/70 text-[12px] xl:text-[13px] mt-1">Investment opportunities</p>
              </div>
              <div class="bg-white/10 backdrop-blur-md border border-white/10 rounded-[16px] p-[16px]">
                <span class="text-[#84FFC1] text-[22px] xl:text-[28px] font-bold">200+</span>
                <p class="text-white/70 text-[12px] xl:text-[13px] mt-1">Startups participating</p>
              </div>
              <div class="bg-white/10 backdrop-blur-md border border-white/10 rounded-[16px] p-[16px]">
                <span class="text-[#84FFC1] text-[22px] xl:text-[28px] font-bold">50+</span>
                <p class="text-white/70 text-[12px] xl:text-[13px] mt-1">VCs & angels present</p>
              </div>
              <div class="bg-white/10 backdrop-blur-md border border-white/10 rounded-[16px] p-[16px]">
                <span class="text-[#84FFC1] text-[22px] xl:text-[28px] font-bold">3 Days</span>
                <p class="text-white/70 text-[12px] xl:text-[13px] mt-1">Intensive program</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Bottom nav buttons + title (from Figma: 526x72 container) -->
        <div class="flex items-center gap-[24px] self-start">
          <!-- Prev button: 72x72, rgba(18,27,38,0.2) -->
          <button
            class="w-[72px] h-[72px] rounded-full bg-[#121B26]/20 flex items-center justify-center hover:bg-white/10 transition-colors"
            aria-label="Previous"
          >
            <svg width="32" height="32" viewBox="0 0 32 32" fill="none" aria-hidden="true">
              <path d="M20 8L12 16L20 24" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          <!-- Next button: 72x72, bg #84FFC1 -->
          <button
            class="w-[72px] h-[72px] rounded-full bg-[#84FFC1] flex items-center justify-center hover:opacity-90 transition-opacity"
            aria-label="Next"
          >
            <svg width="32" height="32" viewBox="0 0 32 32" fill="none" aria-hidden="true">
              <path d="M12 8L20 16L12 24" stroke="#121B26" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          <!-- Title: 23px/700, white -->
          <h3 class="text-white text-[18px] xl:text-[23px] font-bold leading-[32px] tracking-wider uppercase">
            DIGITAL STARTUPS PROGRAM
          </h3>
        </div>

      </div>
    </div>
  </section>
</template>
