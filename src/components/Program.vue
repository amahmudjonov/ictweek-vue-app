<script setup>
// "Past Attendees Include" section — 1280x782
// Title + 4 rows of logo cards with gradient borders

// 15 logo placeholders (3 rows of 5, each 208x120 with gradient border)
// + 1 row of 4 wider cards (268x120)
const logoRows = [
  ['Google', 'Microsoft', 'Amazon', 'Meta', 'Apple'],
  ['Alibaba', 'Huawei', 'Samsung', 'Oracle', 'SAP'],
  ['Cisco', 'IBM', 'NVIDIA', 'Intel', 'Qualcomm'],
]
const wideRow = ['UzbekTelecom', 'IT Park Uzbekistan', 'Navoi MMC', 'Agrobank']
</script>

<template>
  <section class="w-full py-[20px] xl:py-[0px]" id="partners" aria-label="Past attendees section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <!-- Card: 1280x782, rgba(18,27,38,0.4), borderRadius 24px -->
      <div class="w-full bg-[#121B26]/40 rounded-[24px] pt-[36px] pb-[60px]">
        <!-- Title: centered, 48px/700, #EDEDF2 -->
        <h2 class="text-[#EDEDF2] text-[28px] xl:text-[48px] font-bold leading-[58px] text-center">
          Past Attendees Include
        </h2>

        <!-- Logo grid container: 1168px wide, 56px margin sides, mt 150px-36px = 114 from container top -->
        <div class="mt-[40px] xl:mt-[60px] px-[20px] xl:px-[56px] flex flex-col gap-6 xl:gap-[32px]">

          <!-- 3 rows of 5 cards (208x120 each) -->
          <div
            v-for="(row, rowIdx) in logoRows"
            :key="rowIdx"
            class="grid grid-cols-2 sm:grid-cols-3 xl:grid-cols-5 gap-4 xl:gap-[32px]"
          >
            <div
              v-for="(logo, logoIdx) in row"
              :key="logoIdx"
              class="logo-card h-[80px] xl:h-[120px] flex items-center justify-center"
            >
              <span class="text-white/60 text-[13px] xl:text-[15px] font-semibold text-center px-2">{{ logo }}</span>
            </div>
          </div>

          <!-- Last row of 4 wider cards (268x120) -->
          <div class="grid grid-cols-2 xl:grid-cols-4 gap-4 xl:gap-[32px]">
            <div
              v-for="(logo, idx) in wideRow"
              :key="idx"
              class="logo-card h-[80px] xl:h-[120px] flex items-center justify-center"
            >
              <span class="text-white/60 text-[13px] xl:text-[15px] font-semibold text-center px-2">{{ logo }}</span>
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>
