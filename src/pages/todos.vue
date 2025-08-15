<script setup lang="ts">
const config = useRuntimeConfig()
const { data: todos, error, pending } = await useFetch(
  () => `${config.public.apiBaseUrl}/api/todos`,
  { server: false }
)
</script>

<template>
  <main style="padding:24px">
    <h1>ToDo リスト（Laravel API）</h1>
    <p v-if="pending">Loading...</p>
    <p v-else-if="error">Error: {{ error.message }}</p>
    <ul v-else>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.title }} <span v-if="todo.completed">✅</span>
      </li>
    </ul>
  </main>
</template>
