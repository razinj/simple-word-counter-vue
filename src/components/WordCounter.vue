<script setup lang="ts">
import { computed, ref, type Ref } from 'vue'

const userInput: Ref<string | undefined> = ref(undefined)

const charactersCount = computed(() => {
  return userInput.value?.length ?? 0
})

const wordsCount = computed(() => {
  return userInput.value?.split(/\s/).filter((value: string) => value.trim() !== '').length ?? 0
})
</script>

<template>
  <div class="wrapper">
    <div class="card">
      <div class="header">
        <div class="item-wrapper">
          <span>words</span> <span>{{ wordsCount }}</span>
        </div>
        <div class="item-wrapper">
          <span>characters</span> <span>{{ charactersCount }}</span>
        </div>
      </div>
      <div class="body">
        <textarea v-model="userInput" placeholder="Enter your text here" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
  border-radius: 5px;
  border: 1px solid black;
  box-shadow: 5px 5px;
  width: 80vw;
}

.card {
  display: flex;
  flex-direction: column;
  width: 100%;
  gap: 10px;
  padding: 10px;
}

.header {
  display: flex;
  flex: 1;
  gap: 10px;
  height: 50px;
}

.item-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 5px;
  border-radius: 5px;
  background-color: #f8f8f8;
}

.item-wrapper span:first-child {
  user-select: none;
  color: gray;
  font-size: 12px;
  text-transform: uppercase;
}

.item-wrapper span:last-child {
  font-size: 16px;
  font-weight: bold;
}

.item-wrapper .card,
.header,
.body,
textarea {
  width: 100%;
}

.body textarea {
  height: 250px;
  padding: 10px;
  outline-style: none;
  border: 2px solid #ccc;
  border-radius: 5px;
  background-color: #f8f8f8;
  resize: none;
}

@media only screen and (min-width: 1024px) {
  .wrapper {
    width: 50vw;
  }

  .card {
    padding: 25px;
  }

  .card,
  .header {
    gap: 25px;
  }
}
</style>
