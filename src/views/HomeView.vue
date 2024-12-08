<script setup>
  import NavbarComponent from "@/components/NavbarComponent.vue";
  import HeroComponent from "@/components/HeroComponent.vue";
  import MovingBar from "@/components/MovingBar.vue";
  import DisplayCategory from "@/components/DisplayCategory.vue";
  import BrownSection from "@/components/BrownSection.vue";
  import ArrivalsComponent from "@/components/ArrivalsComponent.vue";
  import GreenComponent from "@/components/GreenComponent.vue";
  import MinishopComponent from "@/components/MinishopComponent.vue"
  import HeroBanner from "@/components/HeroBanner.vue"
</script>

<template>
  <main class="home-main">
    <NavbarComponent />
    <HeroComponent />
    <MovingBar />
    <DisplayCategory />
    <BrownSection />
    <ArrivalsComponent />
    <GreenComponent />
    <MinishopComponent />
    <HeroBanner />
  </main>
</template>

<style>
 .home-main {
  font-family: 'DM Sans', sans-serif;
 }
</style>
