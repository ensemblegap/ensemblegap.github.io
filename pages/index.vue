<template>
  <div class="max-w-7xl mx-auto p-4">
    <h1>Home</h1>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import NuxtLogo from '~/components/NuxtLogo.vue'

export default Vue.extend({
  components: { NuxtLogo },
  asyncData() {
    return {
      rendering: process.server ? 'sesrver' : 'client'
    }
  }
})
</script>
