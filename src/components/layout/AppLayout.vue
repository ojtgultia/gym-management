<script setup>
import { ref, watch, onMounted } from 'vue'

const theme = ref('light')

onMounted(() => {
  const saved = localStorage.getItem('theme')
  if (saved) theme.value = saved
})

watch(theme, (newTheme) => {
  localStorage.setItem('theme', newTheme)
})

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3 bg-light-green-lighten-1">
        <v-spacer></v-spacer>

        <v-btn
          class="bg-grey-darken-2"
          :icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          variant="elevated"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main class="bg-grey-darken-2">
        <v-container>
          <slot name="content" />
        </v-container>
      </v-main>

      <v-footer border app class="bg-light-green-lighten-1 text-caption font-weight-bold"
        >Copyright © 2025 GBW GYM - All Rights Reserved</v-footer
      >
    </v-app>
  </v-responsive>
</template>
