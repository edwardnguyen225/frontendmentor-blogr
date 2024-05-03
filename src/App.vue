<script setup lang="ts">
import TheHeader from './components/TheHeader.vue'
import TheFooter from './components/TheFooter.vue'
import ThirdSection from './components/ThirdSection.vue'
import FirstSection from './components/FirstSection.vue'
import SecondSection from './components/SecondSection.vue'
</script>

<template>
  <TheHeader />

  <main>
    <FirstSection />
    <SecondSection />
    <ThirdSection />
  </main>

  <TheFooter />
</template>

<style scoped>
main {
  padding-top: 100px;
  padding-bottom: 100px;
  overflow: hidden;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  main {
    padding-top: 200px;
  }

  footer {
    margin-top: 123px;
  }
}
</style>
