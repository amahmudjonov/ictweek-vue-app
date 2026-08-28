<script setup>
import modtru from '../assets/MODTRU.svg'
import itpark from '../assets/ITPark.svg'
import startupbase from '../assets/startupbase.svg'
import qrCode from '../assets/qr_code.svg'

const benefits = [
  [
    { value: '100%', text: 'Reimbursement for patenting and trademark registration' },
    { icon: true,   text: 'Special legal regime "Regulatory Sandbox" for rapid piloting' },
  ],
  [
    { value: '$50K',   text: 'Reimbursement for mentor/trainer costs in acceleration programs' },
    { value: '1+1',   text: 'Co-funding mechanism matching foreign investment dollar-for-dollar' },
  ],
  [
    { value: '$20K',   text: 'Reimbursement of international acceleration program costs' },
    { value: '1 YEAR', text: 'Free access to the massive Digital Data Platform for Startups' },
  ],
  [
    { value: '1 YEAR', text: 'Free dedicated legal and financial consultations with top experts' },
    { value: '$10K',   text: 'Awarding grants directly to winners of national hackathons and ideathons' },
  ],
]
</script>

<template>
  <section class="w-full py-[20px] xl:py-[0px]" aria-label="Digital Startups Program section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <div class="w-full bg-[#121B26]/40 rounded-[24px] flex flex-col gap-[16px] p-[20px] xl:p-[28px] stat-card">

        <!-- Header bar: green gradient bg left to right -->
        <div class="w-full rounded-[14px] flex items-center justify-between px-[20px] py-[14px] bg-gradient-to-r from-[#84FFC1] to-[#459b6f00]">
          <div class="flex items-center gap-[12px]">
            <div class="w-[3px] h-[22px] bg-[#121B26] rounded-full flex-shrink-0"></div>
            <span class="text-[#121B26] font-bold text-[15px] xl:text-[18px] tracking-[0.08em] uppercase">Digital Startups Program</span>
          </div>
          <div class="flex items-center gap-[16px]">
            <img :src="modtru" alt="Ministry of Digital Technologies" class="h-[30px] object-contain opacity-90" />
            <div class="w-[1px] h-[24px] bg-white/20"></div>
            <img :src="itpark" alt="IT Park Uzbekistan" class="h-[30px] object-contain opacity-90" />
          </div>
        </div>

        <!-- 4-row x 2-col benefits grid -->
        <div class="w-full flex flex-col gap-[8px]">
          <div
            v-for="(row, rowIdx) in benefits"
            :key="rowIdx"
            class="grid grid-cols-1 md:grid-cols-2 gap-[8px]"
          >
            <!-- Left card -->
            <div class="stat-card rounded-[12px] flex items-center gap-[16px] px-[18px] py-[14px]">
              <template v-if="!row[0].icon">
                <span class="text-[#84FFC1] text-[20px] xl:text-[24px] font-bold leading-none flex-shrink-0 min-w-[60px]">{{ row[0].value }}</span>
              </template>
              <template v-else>
                <!-- Shield icon -->
                <svg width="36" height="36" viewBox="0 0 36 36" fill="none" class="flex-shrink-0">
                  <path d="M18 3L5 8.5V18C5 25.2 10.8 31.9 18 33C25.2 31.9 31 25.2 31 18V8.5L18 3Z" stroke="#84FFC1" stroke-width="1.5" stroke-linejoin="round"/>
                  <path d="M12 18L16 22L24 14" stroke="#84FFC1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </template>
              <span class="text-white/80 text-[13px] xl:text-[14px] leading-[19px]">{{ row[0].text }}</span>
            </div>

            <!-- Right card -->
            <div class="stat-card rounded-[12px] flex items-center gap-[16px] px-[18px] py-[14px]">
              <template v-if="!row[1].icon">
                <span class="text-[#84FFC1] text-[20px] xl:text-[24px] font-bold leading-none flex-shrink-0 min-w-[60px]">{{ row[1].value }}</span>
              </template>
              <template v-else>
                <svg width="36" height="36" viewBox="0 0 36 36" fill="none" class="flex-shrink-0">
                  <path d="M18 3L5 8.5V18C5 25.2 10.8 31.9 18 33C25.2 31.9 31 25.2 31 18V8.5L18 3Z" stroke="#84FFC1" stroke-width="1.5" stroke-linejoin="round"/>
                  <path d="M12 18L16 22L24 14" stroke="#84FFC1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </template>
              <span class="text-white/80 text-[13px] xl:text-[14px] leading-[19px]">{{ row[1].text }}</span>
            </div>
          </div>
        </div>

        <!-- Bottom: description + Startup Base -->
        <div class="w-full grid grid-cols-1 md:grid-cols-[1fr_auto] gap-[8px]">
          <!-- Description -->
          <div class="stat-card rounded-[12px] px-[18px] py-[16px] flex items-center">
            <p class="text-white/70 text-[13px] xl:text-[14px] leading-[22px]">
              Digital Startups Program – a <b class="text-white">$50 million</b> initiative, launched for promising Uzbek tech startups.
              Funding, mentorship, intellectual property protection and access to the global market – all
              available on one platform – <b class="text-[#84FFC1]">startupbase.uz</b>
            </p>
          </div>

          <!-- Startup Base + QR -->
          <div class="stat-card rounded-[12px] flex items-center gap-[16px] px-[18px] py-[16px]">
            <div class="flex flex-col items-center gap-[6px]">
              <img :src="startupbase" alt="Startup Base" class="h-[28px] object-contain" />
              <span class="text-white/60 text-[11px]">Startup Base</span>
            </div>
            <img :src="qrCode" alt="QR code" class="w-[72px] h-[72px] object-contain rounded-[6px]" />
          </div>
        </div>

        <!-- Bottom nav -->
        <div class="w-full flex items-center justify-center gap-[20px]">
          <button
            class="w-[48px] h-[48px] rounded-full bg-white/10 border border-white/10 flex items-center justify-center hover:bg-white/20 transition-colors flex-shrink-0"
            aria-label="Previous"
          >
            <svg width="18" height="18" viewBox="0 0 18 18" fill="none">
              <path d="M11 4L6 9L11 14" stroke="white" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          <h3 class="text-white text-[13px] xl:text-[16px] font-bold tracking-wider uppercase text-center">
            DIGITAL STARTUPS PROGRAM
          </h3>
          <button
            class="w-[48px] h-[48px] rounded-full bg-[#84FFC1] flex items-center justify-center hover:opacity-90 transition-opacity flex-shrink-0"
            aria-label="Next"
          >
            <svg width="18" height="18" viewBox="0 0 18 18" fill="none">
              <path d="M7 4L12 9L7 14" stroke="#121B26" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </div>

      </div>
    </div>
  </section>
</template>
