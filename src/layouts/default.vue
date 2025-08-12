<template>
  <VApp>
    <Header />
    <main class="v-main">
      <slot />
    </main>
    <Footer />
  </VApp>
</template>

<script setup lang="ts">
import Header from "~/components/organisms/layout/Header.vue";
import Footer from "~/components/organisms/layout/Footer.vue";
</script>

<style lang="scss" scoped>
</style>
