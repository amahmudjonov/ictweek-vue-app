<script setup>
import websummit from '../assets/websummit.svg'
import plugandplay from '../assets/plugandplay.svg'
import mit from '../assets/MIT.svg'
import googleStartups from '../assets/Google_for_Startups_logo.svg'
import aws from '../assets/aws.svg'
import alchemist from '../assets/AlchemistWhitehorizontal.svg'
import dealroom from '../assets/dealroom.svg'
import startupblink from '../assets/StartupBlink.svg'
import dominoventures from '../assets/dominoventures.png'
import genome from '../assets/genome.svg'
import accesa from '../assets/accesa.svg'
import sturgeoncapital from '../assets/sturgeoncapital.svg'
import salesforce from '../assets/salesforce.svg'
import ey from '../assets/ey.svg'
import globalstartup from '../assets/GLOBALSTATUSAWARD.png'
import gbtp from '../assets/gbtp.svg'
import polyavalent from '../assets/polyavalent.svg'
import goldengateventures from '../assets/goldengateventures.svg'
import spscommerce from '../assets/svgexport.svg'

const logoRows = [
  [
    { src: websummit, alt: 'Web Summit' },
    { src: plugandplay, alt: 'Plug and Play' },
    { src: mit, alt: 'MIT' },
    { src: googleStartups, alt: 'Google for Startups' },
    { src: aws, alt: 'AWS' },
  ],
  [
    { src: alchemist, alt: 'Alchemist Accelerator' },
    { src: dealroom, alt: 'dealroom.co' },
    { src: startupblink, alt: 'StartupBlink' },
    { src: dominoventures, alt: 'Domino Ventures' },
    { src: genome, alt: 'Startup Genome' },
  ],
  [
    { src: accesa, alt: 'Accesa' },
    { src: sturgeoncapital, alt: 'Sturgeon Capital' },
    { src: salesforce, alt: 'Salesforce.org' },
    { src: ey, alt: 'EY' },
    { src: globalstartup, alt: 'Global Startup Awards' },
  ],
]

const wideRow = [
  { src: gbtp, alt: 'GBTP' },
  { src: polyavalent, alt: 'Polyvalent' },
  { src: goldengateventures, alt: 'Golden Gate Ventures' },
  { src: spscommerce, alt: 'SPS Commerce' },
]
</script>

<template>
  <section class="w-full py-[20px] xl:py-[0px]" id="partners" aria-label="Past attendees section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <div class="w-full bg-[#121B26]/40 rounded-[24px] pt-[36px] pb-[60px] stat-card">
        <h2 class="text-[#EDEDF2] text-[28px] xl:text-[48px] font-bold leading-[58px] text-center">
          Past Attendees Include
        </h2>

        <div class="mt-[40px] xl:mt-[60px] px-[20px] xl:px-[56px] flex flex-col gap-4 xl:gap-[24px]">

          <div
            v-for="(row, rowIdx) in logoRows"
            :key="rowIdx"
            class="grid grid-cols-2 sm:grid-cols-3 xl:grid-cols-5 gap-4 xl:gap-[24px]"
          >
            <div
              v-for="(logo, logoIdx) in row"
              :key="logoIdx"
              class="h-[80px] xl:h-[120px] flex items-center justify-center stat-card rounded-[12px] px-4"
            >
              <img :src="logo.src" :alt="logo.alt" class="max-h-[48px] xl:max-h-[60px] max-w-full object-contain" />
            </div>
          </div>

          <div class="grid grid-cols-2 xl:grid-cols-4 gap-4 xl:gap-[24px]">
            <div
              v-for="(logo, idx) in wideRow"
              :key="idx"
              class="h-[80px] xl:h-[120px] flex items-center justify-center stat-card rounded-[12px] px-4"
            >
              <img :src="logo.src" :alt="logo.alt" class="max-h-[48px] xl:max-h-[60px] max-w-full object-contain" />
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>
