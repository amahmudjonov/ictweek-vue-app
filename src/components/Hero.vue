<script setup>
// Hero Section - 1280x955 content + stats bar
// Main title, video card (781x500), info card (483x500), stats bar (1280x182)
</script>

<template>
  <section class="relative w-full overflow-hidden" aria-label="Hero section">
    <!-- <div class="absolute inset-0 z-0 overflow-hidden">
      <img
        src="../assets/bg_northern_lights.png"
        class="absolute inset-0 w-full h-full object-cover mix-blend-screen opacity-80"
        alt=""
        aria-hidden="true"
      />
      <img
        src="../assets/bg_gemini_generated.png"
        class="absolute top-0 left-1/2 -translate-x-1/2 w-[2420px] h-auto object-cover mix-blend-screen pointer-events-none"
        alt=""
        aria-hidden="true"
      />
      <div class="absolute inset-0 bg-gradient-to-b from-[#010D12] via-[#010D12]/60 to-transparent pointer-events-none"></div>
      <div class="absolute bottom-0 left-0 right-0 h-[300px] bg-gradient-to-t from-[#121B26] to-transparent pointer-events-none"></div>
    </div> -->

    <!-- Content wrapper: 1440px full-bleed, 80px side padding, content 1280px -->
    <div class="relative z-10 w-full pt-[150px] xl:pt-[191px] pb-[60px] xl:pb-[80px]">
      <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">

        <!-- Main Title: 944px wide, centered within 1280px -->
        <h1 class="text-white font-bold text-[38px] sm:text-[52px] xl:text-[70px] leading-[1.0] text-center mx-auto max-w-[944px] mb-[40px] xl:mb-[56px] tracking-[-0.5px]">
          Unlock the World's Fastest Growing Ecosystem
        </h1>

        <!-- Two columns: 781px video + 16px gap + 483px info card = 1280px -->
        <div class="flex flex-col xl:flex-row gap-4 w-full">

          <!-- Video Card: 781px, height 500px -->
          <div class="w-full xl:w-[781px] h-[280px] sm:h-[380px] xl:h-[500px] relative rounded-[24px] backdrop-blur-[25px] flex-shrink-0 overflow-hidden">
            <!-- Inner video frame: 769x488, 6px inset -->
            <div class="absolute inset-[6px] rounded-[17px] overflow-hidden bg-[#121B26]/30">
              <video
                src="../assets/Highlights_ICT_Week_Uzbekistan_2025_One_Vision,_One_Future_97mb (1).mp4"
                alt="ICT Week 2026 - Summit preview video"
                autoplay
                muted
                loop
                class="w-full h-full object-cover"
                loading="eager"
              ></video>
              <!-- Play button overlay: centered, 69x69 -->
              <button
                class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[69px] h-[69px] rounded-full bg-[#121B26]/30 border border-white/20 backdrop-blur-md flex items-center justify-center hover:bg-[#84FFC1]/20 hover:border-[#84FFC1]/40 transition-all group"
                aria-label="Play summit preview video"
              >
                <!-- Gradient border ring -->
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" class="ml-[3px]">
                  <path d="M7 3L21 12L7 21V3Z" fill="white"/>
                </svg>
              </button>
            </div>
          </div>

          <!-- Info Card: 483px, height 500px - rgba(18,27,38,0.3), borderRadius 24px -->
          <div class="w-full xl:w-[483px] xl:h-[500px] bg-[#121B26]/30 rounded-[24px] flex flex-col justify-between p-[24px] flex-shrink-0">
            <div class="flex flex-col gap-4">
              <!-- Inner image placeholder (from Figma: 435x187, border-radius 16px) -->
              <div class="w-full h-[140px] xl:h-[187px] rounded-[16px] overflow-hidden bg-gradient-to-br from-[#84FFC1]/10 to-transparent relative">
                <div class="absolute inset-0 bg-gradient-to-r from-[#155B7F]/30 to-[#1BDB86]/10"></div>
              </div>

              <!-- Subtitle text from Figma: 22px/500 weight, white -->
              <p class="text-white text-[18px] xl:text-[22px] font-medium leading-[26px]">
                Learn everything about the thriving Uzbek tech ecosystem — in just one week
              </p>

              <!-- Buttons row: 178px "Register now" + 167px "Full agenda" -->
              <div class="flex flex-col sm:flex-row gap-4 mt-2">
                <a
                  href="#register"
                  class="flex items-center justify-center gap-1 h-[52px] px-[20px] pr-[16px] bg-[#84FFC1] text-[#121B26] text-[18px] font-bold rounded-[12px] hover:bg-white transition-colors"
                >
                  Register now
                  <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                    <path d="M7 17L17 7M17 7H7M17 7V17" stroke="#121B26" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                  </svg>
                </a>
                <button
                  class="flex items-center justify-center gap-2 h-[52px] px-[20px] border border-[#84FFC1] text-[#84FFC1] text-[18px] font-bold rounded-[12px] hover:bg-[#84FFC1]/10 transition-colors"
                >
                  Full agenda
                  <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
                    <path d="M5 10H15M15 10L10 5M15 10L10 15" stroke="#84FFC1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                  </svg>
                </button>
              </div>
            </div>

            <!-- Stats row - 3 stat blocks at bottom -->
            <div class="grid grid-cols-3 gap-4 mt-6 xl:mt-0 pt-6 border-t border-white/10">
              <div class="flex flex-col gap-1">
                <span class="text-[#84FFC1] text-[24px] xl:text-[28px] font-bold leading-none">100+</span>
                <span class="text-[#B5B2B1] text-[13px]">Speakers</span>
              </div>
              <div class="flex flex-col gap-1">
                <span class="text-[#84FFC1] text-[24px] xl:text-[28px] font-bold leading-none">50+</span>
                <span class="text-[#B5B2B1] text-[13px]">Partners</span>
              </div>
              <div class="flex flex-col gap-1">
                <span class="text-[#84FFC1] text-[24px] xl:text-[28px] font-bold leading-none">10k+</span>
                <span class="text-[#B5B2B1] text-[13px]">Attendees</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Stats Bar: 1280x182 - rgba(18,27,38,0.4), borderRadius 24px, padding 16px 28px 16px 23px -->
        <div class="mt-4 w-full bg-[#121B26]/40 rounded-[24px] flex flex-col md:flex-row items-center gap-6 md:gap-[32px] p-[20px] md:p-[23px_28px_16px_23px]">
          <!-- Speaker avatar: 150x150 -->
          <img
            src="../assets/speaker.png"
            alt="Summit Speaker"
            class="w-[100px] h-[100px] xl:w-[150px] xl:h-[150px] object-cover rounded-full flex-shrink-0"
          />
          <!-- Stats: 3 groups -->
          <div class="flex flex-col md:flex-row gap-6 md:gap-6 flex-1 w-full">
            <div class="flex flex-col gap-2 flex-1">
              <span class="text-[#84FFC1] text-[32px] xl:text-[40px] font-bold leading-none">70+</span>
              <span class="text-white/70 text-[15px] leading-[20px]">Global Speakers from tech, government & venture capital</span>
            </div>
            <div class="hidden md:block w-[1px] bg-white/10 self-stretch"></div>
            <div class="flex flex-col gap-2 flex-1">
              <span class="text-[#84FFC1] text-[32px] xl:text-[40px] font-bold leading-none">5+</span>
              <span class="text-white/70 text-[15px] leading-[20px]">Specialized business tracks across industries</span>
            </div>
            <div class="hidden md:block w-[1px] bg-white/10 self-stretch"></div>
            <div class="flex flex-col gap-2 flex-1">
              <span class="text-[#84FFC1] text-[32px] xl:text-[40px] font-bold leading-none">September 23, 2026</span>
              <span class="text-white/70 text-[15px] leading-[20px]">CAEx, Tashkent, Uzbekistan — in-person & online</span>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>
