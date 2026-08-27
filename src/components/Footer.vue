<script setup>
// "Our Partners" + Registration Form combined section
// Partners: 1280x518, title "Our Partners", 2 rows of partner cards
// Form: 1280x817, "Register for ICTWEEK Uzbekistan 2026"

const partnerRows = [
  ['IT Park Uzbekistan', 'Ministry of IT', 'UzbekTelecom', 'Epam'],
  ['Google for Startups', 'Microsoft', 'Amazon AWS', 'SAP'],
]

import { ref } from 'vue'
const form = ref({
  firstName: '', lastName: '', email: '', company: '',
  position: '', country: '', phone: '', message: '',
  consent: false
})
const isSubmitted = ref(false)

const handleSubmit = () => {
  isSubmitted.value = true
}
</script>

<template>
  <!-- Our Partners Section -->
  <section class="w-full py-[20px] xl:py-[0px]" aria-label="Our Partners section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <!-- Card: 1280x518, rgba(18,27,38,0.4), borderRadius 24px -->
      <div class="w-full bg-[#121B26]/40 rounded-[24px] pt-[36px] pb-[60px]">
        <!-- Title: "Our Partners", 48px/700, #EDEDF2, centered -->
        <h2 class="text-[#EDEDF2] text-[28px] xl:text-[48px] font-bold leading-[58px] text-center">
          Our Partners
        </h2>

        <!-- 2 rows of partner cards: 1168px wide, left/right 56px margin, mt=114px from top in Figma -->
        <!-- Row 1: 4 cards 268x140. Row 2: 3 cards 368x140 -->
        <div class="mt-[36px] xl:mt-[60px] px-[20px] xl:px-[56px] flex flex-col gap-[32px]">
          <div class="grid grid-cols-2 xl:grid-cols-4 gap-4 xl:gap-[32px]">
            <div
              v-for="(partner, idx) in partnerRows[0]"
              :key="idx"
              class="logo-card h-[100px] xl:h-[140px] flex items-center justify-center"
            >
              <span class="text-white/50 font-semibold text-sm xl:text-base text-center px-2">{{ partner }}</span>
            </div>
          </div>
          <div class="grid grid-cols-2 xl:grid-cols-3 gap-4 xl:gap-[32px]">
            <div
              v-for="(partner, idx) in partnerRows[1].slice(0,3)"
              :key="idx"
              class="logo-card h-[100px] xl:h-[140px] flex items-center justify-center"
            >
              <span class="text-white/50 font-semibold text-sm xl:text-base text-center px-2">{{ partner }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Registration Form Section -->
  <section class="w-full py-[20px] xl:py-[0px]" id="register" aria-label="Registration form section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <!-- Card: 1280x817, rgba(18,27,38,0.4), borderRadius 24px, padding 36px 56px 56px -->
      <div class="w-full bg-[#121B26]/40 rounded-[24px] flex flex-col items-center gap-[32px] p-[28px] xl:p-[36px_56px_56px]">

        <!-- Header: 894x122, flex column, gap 16px -->
        <div class="flex flex-col gap-[16px] items-center text-center max-w-[894px]">
          <!-- Title: 48px/700, #EDEDF2 -->
          <h2 class="text-[#EDEDF2] text-[26px] xl:text-[48px] font-bold leading-[58px]">
            Register for ICTWEEK Uzbekistan 2026
          </h2>
          <!-- Subtitle: 20px, rgba(255,255,255,0.7), centered, lineHeight 24px -->
          <p class="text-[rgba(255,255,255,0.7)] text-[16px] xl:text-[20px] text-center leading-[24px] max-w-[740px]">
            Join global tech leaders, enterprise delegates, and investors in Tashkent. Complete your details below to secure your pass.
          </p>
        </div>

        <!-- Success state -->
        <div v-if="isSubmitted" class="w-full text-center py-16">
          <div class="text-[#84FFC1] text-5xl mb-4">✓</div>
          <h3 class="text-white text-2xl font-bold mb-2">Registration Submitted!</h3>
          <p class="text-white/70">A confirmation email is on its way. We'll contact you shortly.</p>
        </div>

        <!-- Form: 1168x567, flex column, gap 32px -->
        <form
          v-else
          @submit.prevent="handleSubmit"
          class="w-full max-w-[1168px] flex flex-col gap-[32px]"
          novalidate
        >
          <!-- Input grid: 2 columns, each 568px -->
          <div class="grid grid-cols-1 xl:grid-cols-2 gap-[32px]">
            <!-- Left column -->
            <div class="flex flex-col gap-[20px]">
              <div class="flex flex-col gap-2">
                <label for="firstName" class="text-white/70 text-[14px] font-medium">First Name *</label>
                <input
                  id="firstName"
                  v-model="form.firstName"
                  type="text"
                  required
                  placeholder="Enter your first name"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors"
                />
              </div>
              <div class="flex flex-col gap-2">
                <label for="email" class="text-white/70 text-[14px] font-medium">Email Address *</label>
                <input
                  id="email"
                  v-model="form.email"
                  type="email"
                  required
                  placeholder="your@email.com"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors"
                />
              </div>
              <div class="flex flex-col gap-2">
                <label for="company" class="text-white/70 text-[14px] font-medium">Company</label>
                <input
                  id="company"
                  v-model="form.company"
                  type="text"
                  placeholder="Your company name"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors"
                />
              </div>
              <div class="flex flex-col gap-2">
                <label for="position" class="text-white/70 text-[14px] font-medium">Position</label>
                <input
                  id="position"
                  v-model="form.position"
                  type="text"
                  placeholder="CEO, CTO, Developer..."
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors"
                />
              </div>
            </div>
            <!-- Right column -->
            <div class="flex flex-col gap-[20px]">
              <div class="flex flex-col gap-2">
                <label for="lastName" class="text-white/70 text-[14px] font-medium">Last Name *</label>
                <input
                  id="lastName"
                  v-model="form.lastName"
                  type="text"
                  required
                  placeholder="Enter your last name"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors"
                />
              </div>
              <div class="flex flex-col gap-2">
                <label for="country" class="text-white/70 text-[14px] font-medium">Country</label>
                <input
                  id="country"
                  v-model="form.country"
                  type="text"
                  placeholder="Your country"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors"
                />
              </div>
              <div class="flex flex-col gap-2">
                <label for="phone" class="text-white/70 text-[14px] font-medium">Phone Number</label>
                <input
                  id="phone"
                  v-model="form.phone"
                  type="tel"
                  placeholder="+1 234 567 8900"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors"
                />
              </div>
              <div class="flex flex-col gap-2">
                <label for="message" class="text-white/70 text-[14px] font-medium">Message</label>
                <textarea
                  id="message"
                  v-model="form.message"
                  rows="3"
                  placeholder="Any specific interests or questions..."
                  class="w-full bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] py-[14px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors resize-none"
                ></textarea>
              </div>
            </div>
          </div>

          <!-- Consent + Submit: flex row, space-between, items-end -->
          <div class="flex flex-col xl:flex-row items-start xl:items-end justify-between gap-6">
            <!-- Checkbox + consent text -->
            <label class="flex items-start gap-[10px] cursor-pointer flex-1 max-w-[980px]">
              <input
                type="checkbox"
                v-model="form.consent"
                id="consent"
                class="mt-[2px] w-[18px] h-[18px] accent-[#84FFC1] cursor-pointer flex-shrink-0"
              />
              <span class="text-white text-[14px] xl:text-[16px] leading-[22px]">
                Yes, I agree that IT Park Uzbekistan team may contact me by e-mail to inquire about my request, and I am aware that my shared personal data will be saved. This consent can be withdrawn at any time.
              </span>
            </label>

            <!-- Submit button: 178x52, #84FFC1, borderRadius 12px -->
            <button
              type="submit"
              class="flex-shrink-0 flex items-center gap-1 h-[52px] w-[178px] px-[20px] pr-[16px] bg-[#84FFC1] text-[#121B26] text-[18px] font-bold rounded-[12px] justify-center hover:bg-white transition-colors disabled:opacity-50"
              :disabled="!form.consent"
              aria-label="Submit registration"
            >
              Register now
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" aria-hidden="true">
                <path d="M7 17L17 7M17 7H7M17 7V17" stroke="#121B26" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </button>
          </div>

        </form>
      </div>
    </div>
  </section>
</template>
