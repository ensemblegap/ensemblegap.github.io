<template>
  <header class="border-b border-gray-100">
    <nav class="max-w-7xl w-full mx-auto flex items-center p-4 flex-wrap">
      <a href="/" class="inline-flex items-center mx-auto md:mx-0">
        <img src="~assets/img/logo.svg" alt="Ensemble G.A.P" class="w-8 h-8 mr-2">
        <span class="text-xl font-bold tracking-wide">Ensemble G.A.P</span>
      </a>
      <div id="navigation" class="w-full md:inline-flex md:items-center md:flex-grow md:w-auto">
        <div :class="[isOpen ? 'block' : 'hidden', 'md:inline-flex md:flex-row md:ml-auto']">
          <nuxt-link to="/" class="md:inline-flex md:w-auto px-3 py-1 rounded text-gray-600 hover:text-gray-900">
            <span>Home</span>
          </nuxt-link>
          <nuxt-link v-if="false" to="/about" class="md:inline-flex md:w-auto px-3 py-1 rounded text-gray-600 hover:text-gray-900">
            <span>About</span>
          </nuxt-link>
          <nuxt-link to="/music" class="md:inline-flex md:w-auto px-3 py-1 rounded text-gray-600 hover:text-gray-900">
            <span>Music</span>
          </nuxt-link>
          <nuxt-link v-if="false" to="/member" class="md:inline-flex md:w-auto px-3 py-1 rounded text-gray-600 hover:text-gray-900">
            <span>Member</span>
          </nuxt-link>
          <nuxt-link to="/contact" class="md:inline-flex md:w-auto px-3 py-1 rounded text-gray-600 hover:text-gray-900">
            <span>Contact</span>
          </nuxt-link>
        </div>
      </div>
    </nav>
    <nav class="md:hidden fixed h-16 bottom-0 inset-x-0 flex items-center justify-between text-xs text-gray-600 bg-gray-100">
      <nuxt-link to="/" active-class="text-gray-900 bg-gray-300" exact class="h-full w-full block p-2 text-center">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
        </svg>
        Home
      </nuxt-link>
      <nuxt-link v-if="false" to="/about" active-class="text-gray-900 bg-gray-300" class="h-full w-full block p-2 text-center">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M10 6H5a2 2 0 00-2 2v9a2 2 0 002 2h14a2 2 0 002-2V8a2 2 0 00-2-2h-5m-4 0V5a2 2 0 114 0v1m-4 0a2 2 0 104 0m-5 8a2 2 0 100-4 2 2 0 000 4zm0 0c1.306 0 2.417.835 2.83 2M9 14a3.001 3.001 0 00-2.83 2M15 11h3m-3 4h2" />
        </svg>
        About
      </nuxt-link>
      <nuxt-link to="/music" active-class="text-gray-900 bg-gray-300" class="h-full w-full block p-2 text-center">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M9 19V6l12-3v13M9 19c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zm12-3c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zM9 10l12-3" />
        </svg>
        Music
      </nuxt-link>
      <nuxt-link v-if="false" to="/member" active-class="text-gray-900 bg-gray-300" class="h-full w-full block p-2 text-center">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
        </svg>
        Member
      </nuxt-link>
      <nuxt-link to="/contact" active-class="text-gray-900 bg-gray-300" class="h-full w-full block p-2 text-center">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
        </svg>
        Contact
      </nuxt-link>
    </nav>
  </header>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    toggle() {
      this.isOpen = !this.isOpen
    }
  }
})
</script>
