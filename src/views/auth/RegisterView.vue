<script setup>
import { ref } from 'vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          text="Toggle Theme"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
          <v-row class="d-flex justify-center">
            <v-col cols="12" md="4">
              <v-card class="mx-auto" prepend-icon="mdi-dumbbell" subtitle="The #1 Gym in the city">
                <template v-slot:title>
                  <span class="font-weight-black">GBW Gym</span>
                </template>

                <v-card-text class="bg-surface-light pt-4">
                  <v-form fast-fail @submit.prevent>
                    <v-text-field label="First Name" variant="outlined"></v-text-field>
                    <v-text-field label="Last Name" variant="outlined"></v-text-field>
                    <v-text-field label="Email" variant="outlined"></v-text-field>

                    <v-text-field
                      label="Password"
                      type="password"
                      variant="outlined"
                    ></v-text-field>
                    <v-text-field
                      label="Password Confirmation"
                      type="password"
                      variant="outlined"
                    ></v-text-field>

                    <v-btn class="mt-2" type="submit" block>Submit</v-btn>
                  </v-form>
                  <v-divider class="my-5"></v-divider>
                  <h5 class="text-center">
                    Already have account?
                    <router-link class="text-primary" to="/">Log in</router-link>
                  </h5>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>

      <v-footer border app>2025 - All Rights Reserved</v-footer>
    </v-app>
  </v-responsive>
</template>
