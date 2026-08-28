<script setup>
import { ref } from 'vue'

const tabs = [
  { id: 'enterprise', label: 'Enterprise Uzbekistan', active: true },
  { id: 'startup', label: 'Startup & VC', active: false },
  { id: 'service', label: 'Service Companies', active: false },
  { id: 'bridge', label: 'Global Bridge', active: false },
  { id: 'gamedev', label: 'Gamedev', active: false },
  { id: 'ai', label: 'AI NATIVE', active: false },
]

const activeTab = ref('enterprise')

const bullets = [
  'Zero-tax jurisdiction for tech companies',
  'Special legal framework for global business',
  'Direct access to government officials',
  'IT Park special resident benefits & support',
]
</script>

<template>
  <section class="w-full py-[20px] xl:py-[0px]" id="program" aria-label="Enterprise Uzbekistan Summit section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <div class="w-full bg-[#121B26]/40 rounded-[24px] flex flex-col gap-[32px] p-[24px] xl:p-[40px_40px_48px] stat-card">

        <div class="flex flex-wrap gap-3 xl:gap-[12px]">
          <button
            v-for="tab in tabs"
            :key="tab.id"
            @click="activeTab = tab.id"
            class="h-[44px] px-[18px] rounded-full text-[16px] xl:text-[18px] font-semibold transition-all duration-200"
            :class="activeTab === tab.id
              ? 'bg-[#84FFC1] text-[#121B26] border border-[#84FFC1]'
              : 'bg-white/[0.03] text-white/80 border border-white/10 hover:border-white/30'"
          >{{ tab.label }}</button>
        </div>

        <h2 class="text-white text-[28px] xl:text-[56px] font-bold text-center xl:leading-[62px]">
          Enterprise Uzbekistan Summit
        </h2>

        <div class="w-full bg-white/[0.03] border border-white/10 rounded-[16px] flex flex-col md:flex-row items-start md:items-center gap-4 md:gap-0 px-[20px] py-[14px]">
          <div class="flex items-center gap-[10px] flex-1">
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none" class="text-[#84FFC1] flex-shrink-0" aria-hidden="true">
              <rect x="2" y="3" width="16" height="16" rx="2" stroke="currentColor" stroke-width="1.5"/>
              <path d="M14 1V5M6 1V5M2 9H18" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
            </svg>
            <span class="text-white text-[16px] font-semibold leading-[22px]">September 23, 2026</span>
          </div>
          <div class="hidden md:block w-[1px] h-[24px] bg-white/10 mx-4"></div>
          <div class="flex items-center gap-[10px] flex-1">
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none" class="text-[#84FFC1] flex-shrink-0" aria-hidden="true">
              <circle cx="10" cy="10" r="7" stroke="currentColor" stroke-width="1.5"/>
              <path d="M10 6V10L13 13" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
            </svg>
            <span class="text-white text-[16px] font-semibold leading-[22px]">10:00 - 12:00</span>
          </div>
          <div class="hidden md:block w-[1px] h-[24px] bg-white/10 mx-4"></div>
          <div class="flex items-center gap-[10px] flex-1">
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none" class="text-[#84FFC1] flex-shrink-0" aria-hidden="true">
              <path d="M10 2C7.24 2 5 4.24 5 7C5 11 10 18 10 18C10 18 15 11 15 7C15 4.24 12.76 2 10 2ZM10 9C8.9 9 8 8.1 8 7C8 5.9 8.9 5 10 5C11.1 5 12 5.9 12 7C12 8.1 11.1 9 10 9Z" stroke="currentColor" stroke-width="1.5"/>
            </svg>
            <span class="text-white text-[16px] font-bold leading-[22px]">CAEx, Hall 1</span>
          </div>
        </div>

        <div class="w-full bg-white/[0.03] border border-white/10 rounded-[20px] flex flex-col xl:flex-row gap-[32px] p-[24px] xl:p-[36px] stat-card">

          <div class="w-full xl:w-[420px] h-[250px] xl:h-[370px] rounded-[12px] overflow-hidden flex-shrink-0 relative bg-[#121B26]/50">
            <img
              src="../assets/enterprise_left.png"
              alt="Enterprise Uzbekistan Summit overview"
              class="w-full h-full object-cover"
              loading="lazy"
            />
            <div class="absolute bottom-[24px] left-[24px] h-[46px] w-[162px] bg-[#84FFC1] rounded-[12px] flex items-center justify-center">
              <span class="text-[#121B26] text-[15px] font-bold">Learn more</span>
            </div>
          </div>

          <div class="flex flex-col gap-[20px] flex-1 justify-between">
            <p class="text-white text-[16px] xl:text-[18px] font-semibold leading-[26px]">
              Discover Enterprise Uzbekistan — the country's first dedicated jurisdiction built for global technology business.
            </p>

            <ul class="flex flex-col gap-3">
              <li
                v-for="(bullet, idx) in bullets"
                :key="idx"
                class="flex items-start gap-3"
              >
                <span class="mt-[3px] w-[18px] h-[18px] rounded-full bg-[#84FFC1] flex items-center justify-center flex-shrink-0">
                  <svg width="10" height="10" viewBox="0 0 10 10" fill="none" aria-hidden="true">
                    <path d="M2 5L4.5 7.5L8 3" stroke="#121B26" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                  </svg>
                </span>
                <span class="text-white/80 text-[15px] xl:text-[16px] leading-[24px]">{{ bullet }}</span>
              </li>
            </ul>

            <div class="deal-card rounded-[12px] h-[78px] flex items-center px-[20px] gap-4">
              <div class="w-[4px] h-[28px] bg-[#84FFC1]"></div>
              <span class="text-white/70 text-[18px]">
                Ideal for: <b>global tech companies, investors, legal and financial advisors, and government officials</b>
              </span>
            </div>

          </div>
        </div>

      </div>
    </div>
  </section>
</template>
