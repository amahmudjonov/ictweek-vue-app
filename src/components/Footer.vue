<script setup>
// "Our Partners" + Registration Form combined section
// Partners: 1280x518, title "Our Partners", 2 rows of partner cards
// Form: 1280x817, "Register for ICTWEEK Uzbekistan 2026"

import aws from '../assets/aws.svg'
import startupblink from '../assets/StartupBlink.svg'
import startupworldcup from '../assets/startupworldcup.svg'
import difc from '../assets/difc.png'
import pegasus from '../assets/pegasus.svg'
import jetro from '../assets/Jetro.svg'
import ignyte from '../assets/ignyte.svg'

const partnerRow1 = [
  { src: aws, alt: 'AWS' },
  { src: startupblink, alt: 'StartupBlink' },
  { src: startupworldcup, alt: 'Startup World Cup' },
  { src: difc, alt: 'DIFC Innovation Hub' },
]
const partnerRow2 = [
  { src: pegasus, alt: 'Pegasus Tech Ventures' },
  { src: jetro, alt: 'JETRO' },
  { src: ignyte, alt: 'iGNYTE' },
]

import { ref } from 'vue'

const form = ref({
  fullName: '', email: '', company: '', position: '',
  country: '', phone: '', attendingAs: '', tracks: '',
  hearAbout: '', focalPoint: '', consent: false
})
const isSubmitted = ref(false)
const hearAboutOpen = ref(false)

const hearAboutOptions = [
  'Online Advertisement (Instagram, Facebook, LinkedIn, Google)',
  'Partner Network',
  'IT Park Representative',
  'Organic Search / Website',
]

const selectHearAbout = (opt) => {
  form.value.hearAbout = opt
  hearAboutOpen.value = false
}

const handleSubmit = () => {
  isSubmitted.value = true
}
</script>

<template>
  <!-- Our Partners Section -->
  <section class="w-full py-[20px] xl:py-[0px]" aria-label="Our Partners section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <!-- Card: 1280x518, rgba(18,27,38,0.4), borderRadius 24px -->
      <div class="w-full bg-[#121B26]/40 rounded-[24px] pt-[36px] pb-[60px] stat-card">
        <!-- Title: "Our Partners", 48px/700, #EDEDF2, centered -->
        <h2 class="text-[#EDEDF2] text-[28px] xl:text-[48px] font-bold leading-[58px] text-center">
          Our Partners
        </h2>

        <!-- 2 rows of partner cards: 1168px wide, left/right 56px margin, mt=114px from top in Figma -->
        <!-- Row 1: 4 cards 268x140. Row 2: 3 cards 368x140 -->
        <div class="mt-[36px] xl:mt-[60px] px-[20px] xl:px-[56px] flex flex-col gap-[24px] xl:gap-[32px]">
          <!-- Row 1: 4 cards -->
          <div class="grid grid-cols-2 xl:grid-cols-4 gap-4 xl:gap-[32px]">
            <div
              v-for="partner in partnerRow1"
              :key="partner.alt"
              class="stat-card h-[100px] xl:h-[140px] flex items-center justify-center rounded-[16px] px-4"
            >
              <img :src="partner.src" :alt="partner.alt" class="max-h-[52px] xl:max-h-[64px] max-w-full object-contain" />
            </div>
          </div>
          <!-- Row 2: 3 cards -->
          <div class="grid grid-cols-2 xl:grid-cols-3 gap-4 xl:gap-[32px]">
            <div
              v-for="partner in partnerRow2"
              :key="partner.alt"
              class="stat-card h-[100px] xl:h-[140px] flex items-center justify-center rounded-[16px] px-4"
            >
              <img :src="partner.src" :alt="partner.alt" class="max-h-[52px] xl:max-h-[64px] max-w-full object-contain" />
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
      <div class="w-full bg-[#121B26]/40 rounded-[24px] flex flex-col items-center gap-[32px] p-[28px] xl:p-[36px_56px_56px] stat-card">

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

        <form
          v-else
          @submit.prevent="handleSubmit"
          class="w-full max-w-[1168px] flex flex-col gap-[24px]"
          novalidate
        >
          <div class="grid grid-cols-1 xl:grid-cols-2 gap-x-[32px] gap-y-[20px]">

            <!-- LEFT: Full name -->
            <div class="flex flex-col gap-[6px]">
              <label for="fullName" class="text-white/70 text-[14px] font-medium">Full name</label>
              <input id="fullName" v-model="form.fullName" type="text" placeholder="e.g. John Doe" required
                class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors" />
            </div>

            <!-- RIGHT: Country -->
            <div class="flex flex-col gap-[6px]">
              <label for="country" class="text-white/70 text-[14px] font-medium">Country</label>
              <div class="relative">
                <select id="country" v-model="form.country"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white/40 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors appearance-none cursor-pointer">
                  <option value="" disabled selected class="bg-[#121B26]">Select country...</option>
                  <option value="uz" class="bg-[#121B26] text-white">Uzbekistan</option>
                  <option value="us" class="bg-[#121B26] text-white">United States</option>
                  <option value="gb" class="bg-[#121B26] text-white">United Kingdom</option>
                  <option value="de" class="bg-[#121B26] text-white">Germany</option>
                  <option value="ae" class="bg-[#121B26] text-white">UAE</option>
                  <option value="other" class="bg-[#121B26] text-white">Other</option>
                </select>
                <svg class="absolute right-4 top-1/2 -translate-y-1/2 pointer-events-none" width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M4 6L8 10L12 6" stroke="white" stroke-opacity="0.4" stroke-width="1.5" stroke-linecap="round"/></svg>
              </div>
            </div>

            <!-- LEFT: Email -->
            <div class="flex flex-col gap-[6px]">
              <label for="email" class="text-white/70 text-[14px] font-medium">Email</label>
              <input id="email" v-model="form.email" type="email" placeholder="e.g. alex@company.com" required
                class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors" />
            </div>

            <!-- RIGHT: Phone number -->
            <div class="flex flex-col gap-[6px]">
              <label for="phone" class="text-white/70 text-[14px] font-medium">Phone number</label>
              <input id="phone" v-model="form.phone" type="tel" placeholder="e.g. +1 (555) 019-2834"
                class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors" />
            </div>

            <!-- LEFT: Company -->
            <div class="flex flex-col gap-[6px]">
              <label for="company" class="text-white/70 text-[14px] font-medium">Company</label>
              <input id="company" v-model="form.company" type="text" placeholder="e.g. Tech Global Inc."
                class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors" />
            </div>

            <!-- RIGHT: Position -->
            <div class="flex flex-col gap-[6px]">
              <label for="position" class="text-white/70 text-[14px] font-medium">Position</label>
              <input id="position" v-model="form.position" type="text" placeholder="e.g. Managing Director"
                class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors" />
            </div>

            <!-- LEFT: I am attending as -->
            <div class="flex flex-col gap-[6px]">
              <label for="attendingAs" class="text-white/70 text-[14px] font-medium">I am attending as</label>
              <div class="relative">
                <select id="attendingAs" v-model="form.attendingAs"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white/40 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors appearance-none cursor-pointer">
                  <option value="" disabled selected class="bg-[#121B26]">Select category...</option>
                  <option value="enterprise" class="bg-[#121B26] text-white">Enterprise Representative</option>
                  <option value="startup" class="bg-[#121B26] text-white">Startup Founder</option>
                  <option value="investor" class="bg-[#121B26] text-white">Investor / VC</option>
                  <option value="government" class="bg-[#121B26] text-white">Government Official</option>
                  <option value="media" class="bg-[#121B26] text-white">Media / Press</option>
                  <option value="other" class="bg-[#121B26] text-white">Other</option>
                </select>
                <svg class="absolute right-4 top-1/2 -translate-y-1/2 pointer-events-none" width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M4 6L8 10L12 6" stroke="white" stroke-opacity="0.4" stroke-width="1.5" stroke-linecap="round"/></svg>
              </div>
            </div>

            <!-- RIGHT: Event track(s) -->
            <div class="flex flex-col gap-[6px]">
              <label for="tracks" class="text-white/70 text-[14px] font-medium">Event track(s) you plan to attend <span class="text-white/40 font-normal">(Select all that apply)</span></label>
              <div class="relative">
                <select id="tracks" v-model="form.tracks"
                  class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white/40 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors appearance-none cursor-pointer">
                  <option value="" disabled selected class="bg-[#121B26]">Select track(s)...</option>
                  <option value="enterprise" class="bg-[#121B26] text-white">Enterprise Summit</option>
                  <option value="startups" class="bg-[#121B26] text-white">Digital Startups Program</option>
                  <option value="investment" class="bg-[#121B26] text-white">Investment Forum</option>
                  <option value="gov" class="bg-[#121B26] text-white">GovTech Track</option>
                </select>
                <svg class="absolute right-4 top-1/2 -translate-y-1/2 pointer-events-none" width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M4 6L8 10L12 6" stroke="white" stroke-opacity="0.4" stroke-width="1.5" stroke-linecap="round"/></svg>
              </div>
            </div>

            <!-- LEFT: How did you hear about us (custom dropdown) -->
            <div class="flex flex-col gap-[6px] relative">
              <label class="text-white/70 text-[14px] font-medium">How did you hear about us?</label>
              <button type="button" @click="hearAboutOpen = !hearAboutOpen"
                class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-left flex items-center justify-between focus:outline-none focus:border-[#84FFC1] transition-colors">
                <span :class="form.hearAbout ? 'text-white' : 'text-white/30'" class="text-[15px] truncate">
                  {{ form.hearAbout || 'Select source...' }}
                </span>
                <svg :class="hearAboutOpen ? 'rotate-180' : ''" class="flex-shrink-0 transition-transform" width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M4 6L8 10L12 6" stroke="white" stroke-opacity="0.4" stroke-width="1.5" stroke-linecap="round"/></svg>
              </button>
              <!-- Dropdown panel -->
              <div v-if="hearAboutOpen"
                class="absolute top-full mt-1 left-0 right-0 z-20 bg-[#121B26] border border-white/10 rounded-[12px] overflow-hidden shadow-2xl">
                <button
                  v-for="opt in hearAboutOptions" :key="opt"
                  type="button"
                  @click="selectHearAbout(opt)"
                  class="w-full flex items-center gap-3 px-[16px] py-[14px] text-white/80 text-[14px] hover:bg-white/5 transition-colors text-left"
                >
                  <span class="w-[18px] h-[18px] rounded-full border-2 flex items-center justify-center flex-shrink-0"
                    :class="form.hearAbout === opt ? 'border-[#84FFC1] bg-[#84FFC1]' : 'border-white/30'">
                    <span v-if="form.hearAbout === opt" class="w-[7px] h-[7px] rounded-full bg-[#121B26]"></span>
                  </span>
                  {{ opt }}
                </button>
              </div>
            </div>

            <!-- RIGHT: Focal point -->
            <div class="flex flex-col gap-[6px]">
              <label for="focalPoint" class="text-white/70 text-[14px] font-medium">Name of focal point in IT Park <span class="text-white/40 font-normal">(if available)</span></label>
              <input id="focalPoint" v-model="form.focalPoint" type="text" placeholder="e.g. Contact person or team member name"
                class="w-full h-[52px] bg-white/[0.05] border border-white/10 rounded-[12px] px-[16px] text-white placeholder-white/30 text-[15px] focus:outline-none focus:border-[#84FFC1] transition-colors" />
            </div>

          </div>

          <!-- Consent + Submit -->
          <div class="flex flex-col xl:flex-row items-start xl:items-center justify-between gap-6">
            <label class="flex items-start gap-[10px] cursor-pointer flex-1">
              <input type="checkbox" v-model="form.consent" id="consent"
                class="mt-[3px] w-[18px] h-[18px] accent-[#84FFC1] cursor-pointer flex-shrink-0" />
              <span class="text-white/70 text-[14px] leading-[22px]">
                Yes, I agree that IT Park Uzbekistan team may contact me by e-mail to inquire about my request, and I am aware that my shared personal data will be saved.
              </span>
            </label>
            <button type="submit"
              class="flex-shrink-0 flex items-center gap-2 h-[52px] px-[28px] bg-[#84FFC1] text-[#121B26] text-[16px] font-bold rounded-[12px] hover:bg-white transition-colors disabled:opacity-40 whitespace-nowrap"
              :disabled="!form.consent">
              Register now
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none"><path d="M5 15L15 5M15 5H5M15 5V15" stroke="#121B26" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </button>
          </div>

        </form>
      </div>
    </div>
  </section>
</template>
