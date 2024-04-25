<script setup>
import { ref } from 'vue'

const count = ref(0)

function increment() {
  count.value++
}
</script>

<template>
    <p> Hello {{ count }}</p>
</template>

<style scoped>
</style>
