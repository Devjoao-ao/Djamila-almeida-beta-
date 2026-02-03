<template>
  <div class="root-container">
    <CountdownBanner />
    <HeroSection />
    <ProgramSection />
    <WhyParticipate />
    <GlobalFooter />
  </div>
</template>

<script setup>
import CountdownBanner from './components/CountdownBanner.vue'
import HeroSection from './components/HeroSection.vue'
import ProgramSection from './components/ProgramSection.vue'
import WhyParticipate from './components/WhyParticipate.vue'
import GlobalFooter from './components/GlobalFooter.vue'
</script>

<style>
.root-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
