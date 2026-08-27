<script setup>
// Section: "Save your spot today!" — 1280x484
// Left: headline+text+button (603px), Right: image (567x412)
</script>

<template>
  <section class="w-full py-[20px] xl:py-[0px]" aria-label="Save your spot section">
    <div class="max-w-[1440px] mx-auto px-5 xl:px-[80px]">
      <!-- Card: rgba(18,27,38,0.4), border-radius 24px, padding 36px 36px 36px 42px -->
      <div class="w-full bg-[#121B26]/40 rounded-[24px] flex flex-col xl:flex-row gap-8 xl:gap-[32px] items-start p-[28px] xl:p-[36px_36px_36px_42px]">

        <!-- Left: Headline block (603x412) -->
        <div class="flex flex-col gap-[24px] justify-between flex-1 min-h-[auto] xl:min-h-[412px]">
          <h2 class="text-[#EDEDF2] text-[32px] xl:text-[48px] font-bold leading-[1.2] xl:leading-[58px]">
            Save your spot today!
          </h2>

          <!-- Description from Figma: 18px/500, rgba(255,255,255,0.7), lineHeight 29px -->
          <p class="text-[rgba(255,255,255,0.7)] text-[16px] xl:text-[18px] font-medium leading-[1.6] xl:leading-[29px]">
            Every unicorn starts as a single star. <br class="hidden xl:block"/>
            Together they become the Northern Lights.<br class="hidden xl:block"/>
            Welcome to Uzbekistan, where visionary government support and a thriving innovation ecosystem help founders turn bold ideas into global ventures. <br class="hidden xl:block"/>
            Here, startups and tech companies don't just become part of the Northern Lights—they discover their North Star and follow it all the way to international success.
          </p>

          <!-- Button: 178x52, bg #84FFC1, borderRadius 12px -->
          <a
            href="#register"
            class="inline-flex items-center gap-1 h-[52px] w-fit px-[20px] pr-[16px] bg-[#84FFC1] text-[#121B26] text-[18px] font-bold rounded-[12px] hover:bg-white transition-colors"
            aria-label="Register for ICT Week 2026"
          >
            Register now
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M7 17L17 7M17 7H7M17 7V17" stroke="#121B26" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </a>
        </div>

        <!-- Right: Image 567x412, borderRadius 12px -->
        <div class="w-full xl:w-[567px] h-[280px] xl:h-[412px] rounded-[12px] overflow-hidden flex-shrink-0">
          <img
            src="../assets/save_spot.png"
            alt="ICT Week 2026 event atmosphere"
            class="w-full h-full object-cover"
            loading="lazy"
          />
        </div>

      </div>
    </div>
  </section>
</template>
