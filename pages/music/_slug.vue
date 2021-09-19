<template>
  <main>
    <article class="max-w-7xl mx-auto">
      <h1 class="text-4xl">{{ music.title }}</h1>
      <div class="p-4">
        <img :src="music.top_image" alt="">
      </div>
      <NuxtContent :document="music"/>
    </article>
  </main>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  async asyncData({$content, params}) {
    const slug = params.slug
    return {
      music: await $content('music/' + slug).fetch()
    }
  }
})
</script>
