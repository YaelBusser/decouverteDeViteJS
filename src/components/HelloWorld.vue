<script setup lang="ts">
import {ref} from 'vue'
import {useGeolocation} from '@vueuse/core'

defineProps<{ msg: string }>()


// Déclaration d'une variable « observé » de type Int
const count = ref(0)

// Déclaration d'une variable « observé » de type String
const input = ref('Votre nom')
const {coords, locatedAt, error, resume, pause} = useGeolocation()
import { useMouse, usePreferredDark, useLocalStorage } from '@vueuse/core'

// tracks mouse position
const { x, y } = useMouse()

// is user prefers dark theme
const isDark = usePreferredDark()
</script>

<template>
  <h1>{{ msg }}</h1>
  <div class="card">
    <button type="button" @click="count--">--</button>
    <button type="button">{{ count }}</button>
    <button type="button" @click="count++">++</button>
    <p>{{ coords.latitude }}</p>
    <p>{{ coords.longitude }}</p>
  </div>

  <div class="card">
    <h2>hello « {{ input }} »</h2>
    <input v-model="input"/>
  </div>
  {{ x }}, {{ y }}
  <div v-if="isDark">Dark mode</div>
  <div v-else>Light mode</div>
</template>

<style scoped>
.card {
  background: #595959;
  border: 1px solid #ccc;
  border-radius: 2px;
  margin: 10px;
}
</style>