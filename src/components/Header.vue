<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const navItems = [
  { name: 'Home', href: '#', active: true },
  { name: 'Program', href: '#program', active: false },
  { name: 'Partners', href: '#partners', active: false },
  { name: 'Incentives', href: '#register', active: false }
]

const closeMenu = () => { isMobileMenuOpen.value = false }
</script>

<template>
  <!-- Navbar -->
  <header class="site-header">
    <div class="header-pill">

      <!-- Logo -->
      <!-- <a href="#" aria-label="ICT Week 2026 Home" class="logo-link">
        <img src="../assets/ict_week_2026.svg" alt="ICT Week 2026" class="logo-img" />
      </a> -->

      <!-- Desktop Nav -->
      <nav aria-label="Main navigation" class="desktop-nav">
        <a
          v-for="item in navItems"
          :key="item.name"
          :href="item.href"
          class="nav-link"
          :class="item.active ? 'nav-link--active' : 'nav-link--inactive'"
        >{{ item.name }}</a>
      </nav>

      <!-- Desktop CTA -->
      <div class="desktop-cta">
        <button class="lang-btn">
          English
          <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
            <path d="M4 6L8 10L12 6" stroke="#B5B2B1" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
        <a href="#register" class="register-btn">Register now</a>
      </div>

      <!-- Hamburger -->
      <button
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        class="hamburger-btn"
        :aria-expanded="isMobileMenuOpen"
        aria-label="Toggle menu"
      >
        <svg v-if="!isMobileMenuOpen" width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M3 12H21M3 6H21M3 18H21" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
        </svg>
        <svg v-else width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M18 6L6 18M6 6L18 18" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <Transition name="fade">
      <div v-if="isMobileMenuOpen" class="mobile-menu">
        <nav class="mobile-nav">
          <a
            v-for="item in navItems"
            :key="item.name"
            :href="item.href"
            @click="closeMenu"
            class="mobile-nav-link"
            :class="item.active ? 'mobile-nav-link--active' : 'mobile-nav-link--inactive'"
          >{{ item.name }}</a>
        </nav>
        <div class="mobile-cta">
          <a href="#register" @click="closeMenu" class="mobile-register-btn">Register now</a>
        </div>
      </div>
    </Transition>
  </header>
</template>

<style scoped>
/* ---------- Header shell ---------- */
.site-header {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: 95vw;
  z-index: 50;
}
@media (min-width: 1280px) {
  .site-header { top: 37px; width: 1040px; }
}

.header-pill {
  width: 100%;
  height: 70px;
  background: rgba(255, 255, 255, 0.05);
  -webkit-backdrop-filter: blur(24px);
  backdrop-filter: blur(24px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 9999px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
}
@media (min-width: 1280px) {
  .header-pill { height: 80px; padding: 0 32px; }
}

/* ---------- Logo ---------- */
.logo-link { display: flex; align-items: center; }
.logo-img { height: 32px; object-fit: contain; }
@media (min-width: 1280px) {
  .logo-img { height: 42px; }
}

/* ---------- Desktop nav ---------- */
.desktop-nav {
  display: none;
  align-items: center;
  height: 52px;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 9999px;
  padding: 0 6px;
  gap: 6px;
}
@media (min-width: 1024px) {
  .desktop-nav { display: flex; }
}

.nav-link {
  height: 100%;
  display: flex;
  align-items: center;
  padding: 0 24px;
  border-radius: 9999px;
  font-size: 16px;
  font-weight: 500;
  line-height: 22px;
  text-decoration: none;
  transition: all 0.2s ease;
  box-sizing: border-box;
}
.nav-link--active {
  background: #01141A;
  border: 1px solid #84FFC1;
  color: #FFFFFF;
  font-weight: 600;
}
.nav-link--inactive {
  color: #B5B2B1;
  border: 1px solid transparent;
}
.nav-link--inactive:hover { color: #FFFFFF; }

/* ---------- Desktop CTA ---------- */
.desktop-cta { display: none; align-items: center; gap: 12px; }
@media (min-width: 1024px) {
  .desktop-cta { display: flex; }
}

.lang-btn {
  height: 52px;
  padding: 0 24px;
  border-radius: 9999px;
  background: rgba(255, 255, 255, 0.05);
  border: none;
  display: flex;
  align-items: center;
  gap: 8px;
  color: #B5B2B1;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s ease;
}
.lang-btn:hover { background: rgba(255, 255, 255, 0.1); }

.register-btn {
  height: 52px;
  padding: 0 24px;
  border-radius: 9999px;
  background: linear-gradient(to bottom, #84FFC1, #459B6F);
  color: #121B26;
  font-size: 16px;
  font-weight: 600;
  display: flex;
  align-items: center;
  text-decoration: none;
  box-shadow: 0 0 0 0 rgba(132, 255, 193, 0.4);
  transition: opacity 0.2s ease, transform 0.2s ease, box-shadow 0.2s ease;
}
.register-btn:hover {
  opacity: 0.9;
  transform: scale(1.02);
  box-shadow: 0 0 20px rgba(132, 255, 193, 0.4);
}

/* ---------- Hamburger ---------- */
.hamburger-btn {
  display: block;
  color: #FFFFFF;
  background: none;
  border: none;
  padding: 8px;
  cursor: pointer;
}
@media (min-width: 1024px) {
  .hamburger-btn { display: none; }
}

/* ---------- Mobile menu ---------- */
.mobile-menu {
  display: flex;
  flex-direction: column;
  position: fixed;
  inset: 0;
  top: 0;
  background: rgba(1, 13, 18, 0.97);
  -webkit-backdrop-filter: blur(40px);
  backdrop-filter: blur(40px);
  padding: 96px 32px 0;
  z-index: 40;
}
@media (min-width: 1024px) {
  .mobile-menu { display: none; }
}

.mobile-nav {
  display: flex;
  flex-direction: column;
  gap: 24px;
  margin-top: 32px;
}

.mobile-nav-link {
  font-size: 30px;
  font-weight: 700;
  text-decoration: none;
  transition: color 0.2s ease;
}
.mobile-nav-link--active { color: #84FFC1; }
.mobile-nav-link--inactive { color: rgba(255, 255, 255, 0.7); }
.mobile-nav-link--inactive:hover { color: #FFFFFF; }

.mobile-cta {
  margin-top: auto;
  margin-bottom: 48px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.mobile-register-btn {
  width: 100%;
  height: 56px;
  border-radius: 9999px;
  background: linear-gradient(to bottom, #84FFC1, #459B6F);
  color: #121B26;
  font-size: 20px;
  font-weight: 700;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
}

/* ---------- Transition ---------- */
.fade-enter-active, .fade-leave-active { transition: opacity 0.2s; }
.fade-enter-from, .fade-leave-to { opacity: 0; }
</style>