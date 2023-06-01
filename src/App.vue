<script setup lang="ts">
import Header from './components/Header.vue'
import WordCounter from './components/WordCounter.vue'
</script>

<template>
  <header>
    <Header />
  </header>

  <main>
    <div class="word-counter-wrapper">
      <WordCounter />
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: center;
}

.word-counter-wrapper {
  margin-top: 100px;
}
</style>
