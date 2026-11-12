<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <main class="app-shell">
    <h1>Vue 3 + JavaScript</h1>
    <p>A minimal, extensible project starter.</p>
    <button type="button" @click="count++">
      Count: {{ count }}
    </button>
  </main>
</template>
