<script setup>
import AppLayout from '@/components/layout/AppLayout.vue'

AppLayout
</script>

<template>
  <app-layout>
    <template #content>
      <v-row class="d-flex justify-center">
        <v-col cols="12" md="5" class="pt-16">
          <v-card class="mx-auto">
            <v-card-title class="text-center">
              <h3 class="font-weight-black text-center">GBW GYM</h3>
              <p class="text-subtitle-2">Log in Form</p>
            </v-card-title>

            <v-card-text class="bg-surface-light pt-4">
              <v-divider class="my-5"></v-divider>
              <v-form fast-fail @submit.prevent>
                <v-text-field
                  label="Email"
                  variant="outlined"
                  prepend-inner-icon="mdi-email"
                ></v-text-field>

                <v-text-field
                  label="Password"
                  variant="outlined"
                  prepend-inner-icon="mdi-lock-outline"
                />

                <v-btn class="mt-2" type="submit" block prepend-icon="mdi-login">Log in</v-btn>
              </v-form>
              <v-divider class="my-5"></v-divider>
              <h5 class="text-center">
                Don't have account?<router-link class="text-primary" to="/register"
                  >Register</router-link
                >
              </h5>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </template>
  </app-layout>
</template>
