<script setup>
import { defineAsyncComponent, Suspense } from 'vue';
import SplashPage from './components/SplashPage.vue';

const HomePageAsync = defineAsyncComponent(() => new Promise((resolve) => {
  setTimeout(() => {
    resolve(import('./components/HomePage.vue'))
  }, 1000);
}))

</script>

<template>
  <Suspense>
    <template #default>
      <HomePageAsync />
    </template>
    <template #fallback>
      <SplashPage />
    </template>
  </Suspense>
</template>

<style>
html, body, #app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
