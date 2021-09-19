<template>
  <div>
  <div @click="$emit('close')" class="fixed z-40 inset-0 bg-opacity-90 bg-black">
      <div class="fixed overflow-x-hidden overflow-y-auto inset-0 flex justify-center items-center z-50">
        <div class="relative inline-block rounded-md p-1 bg-white bg-opacity-30 text-left shadow-md transform transition-all align-middle lg:max-w-7xl max-h-screen w-5/6">
          <div class="max-w-full aspect-h-9 aspect-w-16">
            <iframe class="inline" :src="'https://www.youtube.com/embed/' + val.mov_id" title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen></iframe>
          </div>
          <button
            class="absolute right-0 top-0 -mr-4 -mt-4 rounded-full bg-gray-700 hover:bg-opacity-50 text-white font-semibold h-6 w-6"
            @click="$emit('close')">×</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Modal',
  props: {
    val: Object,
  }
})
</script>

<style>
.popup-enter-active {
  transition: all 1.00 ease;
}
.popup-leave-active {
  transition: all 1.00s cubic-bezier(1, 0.5, 0.8, 1);;
}
.popup-enter,
.popup-leave-to {
  opacity: 0;
}
</style>
