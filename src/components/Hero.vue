<script setup>
import { ref } from 'vue';

const videoRef = ref(null);
const isPlaying = ref(false);

function togglePlay() {
  if (!videoRef.value) return;
  if (isPlaying.value) {
    videoRef.value.pause();
    isPlaying.value = false;
  } else {
    videoRef.value.play();
    isPlaying.value = true;
  }
}
</script>

<template>
  <section class="relative w-full overflow-hidden" aria-label="Hero section">
    <div class="relative z-10 w-full pt-[150px] xl:pt-[191px] pb-[60px] xl:pb-[80px]">
      <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
        <h1 class="text-white font-bold text-[38px] sm:text-[52px] xl:text-[70px] leading-[1.0] text-center mx-auto max-w-[944px] mb-[40px] xl:mb-[56px] tracking-[-0.5px]">
          Unlock the World's Fastest Growing Ecosystem
        </h1>
        <div class="flex flex-col xl:flex-row gap-4 w-full">
          <div class="w-full xl:w-[781px] h-[280px] sm:h-[380px] xl:h-[500px] relative rounded-[24px] backdrop-blur-[25px] flex-shrink-0 overflow-hidden">
            <div class="absolute inset-[6px] rounded-[17px] overflow-hidden bg-[#121B26]/30">
              <video
                ref="videoRef"
                src="../assets/Highlights_ICT_Week_Uzbekistan_2025_One_Vision,_One_Future_97mb (1).mp4"
                alt="ICT Week 2026 - Summit preview video"
                class="w-full h-full object-cover"
                muted
                loading="eager"
                @ended="isPlaying = false"
              ></video>
              <button
                @click="togglePlay"
                :class="[
                  'absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[69px] h-[69px] rounded-full border backdrop-blur-md flex items-center justify-center transition-all duration-300 group',
                  isPlaying
                    ? 'bg-black/20 border-white/10 opacity-0 hover:opacity-100'
                    : 'bg-[#121B26]/30 border-white/20 hover:bg-[#84FFC1]/20 hover:border-[#84FFC1]/40 opacity-100'
                ]"
                :aria-label="isPlaying ? 'Pause summit preview video' : 'Play summit preview video'"
              >
                <svg v-if="!isPlaying" width="24" height="24" viewBox="0 0 24 24" fill="none" class="ml-[3px]">
                  <path d="M7 3L21 12L7 21V3Z" fill="white"/>
                </svg>
                <svg v-else width="22" height="22" viewBox="0 0 24 24" fill="none">
                  <rect x="5" y="3" width="4" height="18" rx="1" fill="white"/>
                  <rect x="15" y="3" width="4" height="18" rx="1" fill="white"/>
                </svg>
              </button>
            </div>
          </div>

          <div class="w-full xl:w-[483px] xl:h-[500px] bg-[#121B26]/30 rounded-[24px] flex flex-col justify-between p-[24px] flex-shrink-0 stat-card">
            <div class="flex flex-col gap-4">
              <div class="w-full h-[140px] xl:h-[187px] rounded-[16px] overflow-hidden bg-gradient-to-br from-[#84FFC1]/10 to-transparent relative">
                <img src="../assets/Image.png" alt="">
                <div class="absolute inset-0 bg-gradient-to-r from-[#155B7F]/30 to-[#1BDB86]/10"></div>
              </div>

              <p class="text-white text-[18px] xl:text-[22px] font-medium leading-[26px]">
                Learn everything about the thriving Uzbek tech ecosystem — in just one week
              </p>

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

            <div class="grid grid-cols-3 gap-4 mt-6 xl:mt-0 pt-6">
              <div class="flex flex-col gap-1 stat-card px-[28px] py-[20px] rounded-[24px]">
                <span class="text-[#84FFC1] text-[24px] xl:text-[28px] font-bold leading-none">100+</span>
                <span class="text-[#B5B2B1] text-[13px]">Speakers</span>
              </div>
              <div class="flex flex-col gap-1 stat-card px-[28px] py-[20px] rounded-[24px]">
                <span class="text-[#84FFC1] text-[24px] xl:text-[28px] font-bold leading-none">50+</span>
                <span class="text-[#B5B2B1] text-[13px]">Partners</span>
              </div>
              <div class="flex flex-col gap-1 stat-card px-[28px] py-[20px] rounded-[24px]">
                <span class="text-[#84FFC1] text-[24px] xl:text-[28px] font-bold leading-none">10k+</span>
                <span class="text-[#B5B2B1] text-[13px]">Attendees</span>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-4 w-full rounded-[24px] flex flex-col items-center md:flex-row gap-[15px] stat-card px-[14px] py-[20px]">
          <div class="flex items-center justify-center px-[24px] py-[20px]">
            <img
              src="../assets/upscale_resolution_and_remove_watermarks_2026060911521.png"
              alt="Startup's Country of the Year"
              class="w-[100px] h-[100px] xl:w-[110px] xl:h-[110px] object-contain"
            />
          </div>

          <div class="deal-card rounded-[10px] flex gap-[30px] py-[10px] px-[15px] w-[370px] h-full">
            <span class="deal-card__badge">2026</span>
            <div class="flex flex-col gap-[5px]">
              <div class="text-[32px]">$4.3B</div>
              <div class="text-[12px]">
                Startup<br />Ecosystem<br />Valuation
              </div>
            </div>
            <div class="flex flex-col gap-[5px]">
              <div class="text-[32px]">#1</div>
              <div class="text-[12px]">
                In venture<br />investment<br />growth globally
              </div>
            </div>
            <div class="self-end">
              <img src="../assets/dealroom.svg" alt="dealroom" class="h-[21px] object-contain self-start mt-1" />
            </div>
          </div>

          <div class="deal-card rounded-[10px] flex gap-[20px] py-[10px] px-[15px] w-[370px] h-full">
            <span class="deal-card__badge">2026</span>
            <div class="flex flex-col">
              <div class="text-[32px]">#1</div>
              <div class="text-[12px]">
                Ecosystem in the <br />World by Growth<br />Rate
              </div>
            </div>
            <div class="flex flex-col gap-[5px]">
              <div class="text-[32px]">#1</div>
              <div class="text-[12px]">
                Startup Hub in<br />Central Asia<br />(Tashkent)
              </div>
            </div>
            <div class="self-end">
              <img src="../assets/StartupBlink.svg" alt="StartupBlink" class="h-[21px] object-contain self-start mt-1" />
            </div>
          </div>

          <div class="deal-card rounded-[10px] flex justify-between gap-[30px] py-[10px] px-[15px] w-[254px] h-full">
            <span class="deal-card__badge">2026</span>
            <div class="flex flex-col gap-[5px]">
              <div class="flex text-[32px] gap-[10px]">
                <span class="text-whie text-[28px] xl:text-[32px] font-bold leading-none">2</span>
                <img src="../assets/unicorn_icon.svg" alt="Unicorn" class="w-[28px] h-[28px] object-contain" />
              </div>
              <div class="text-[14px]">
                Fintech<br />Unicorns
              </div>
            </div>
            <div class="self-end flex flex-col gap-[15px] mt-[35px]">
              <img src="../assets/uzum_logo.svg" alt="uzum_logo" class="h-[24px] object-contain self-start mt-1" />
              <img src="../assets/tbc_logo.svg" alt="tbc_logo" class="h-[24px] object-contain self-start mt-1" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
