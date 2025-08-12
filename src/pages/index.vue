<script setup lang="ts">
const config = useRuntimeConfig()
const { data, error, pending } = await useFetch(
  () => `${config.public.apiBaseUrl}/api/hello`,
  { server: false }
)
</script>

<template>
  <main style="padding:24px">
    <h1>Nuxt ⇄ Laravel 疎通テスト</h1>
    <p v-if="pending">Loading...</p>
    <p v-else-if="error">Error: {{ error.message }}</p>
    <p v-else>Message: {{ data?.message }}</p>
  </main>
</template>
