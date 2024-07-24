<script setup>
import TheHeader from '@/components/TheHeader.vue'
import HeroSection from '@/components/HeroSection.vue'
import HistorySection from '@/components/HistorySection.vue'
import BenefitsSection from '@/components/BenefitsSection.vue'
import PartnersSection from '@/components/PartnersSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import TheFooter from '@/components/TheFooter.vue'
</script>

<template>
  <TheHeader />
  <main>
    <HeroSection />
    <HistorySection />
    <BenefitsSection />
    <PartnersSection />
    <ContactSection />
  </main>
  <TheFooter />
</template>

<style scoped></style>
