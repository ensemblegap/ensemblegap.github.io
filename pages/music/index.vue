<template>
  <div class="max-w-7xl mx-auto">

    <!-- component -->
    <div class="insta-clone">
      <!--profile data-->
      <div class="bg-gray-100 h-auto">

        <!--post icon and title-->
        <div class="flex flex-row pt-4 justify-center mx-16">
          <div class="flex text-gray-700 text-center py-2 m-2 pr-5">
            <div class="inline-flex">
              <button
                class="border-transparent text-gray-800 rounded-full hover:text-blue-600 focus:outline-none focus:text-gray-600"
                aria-label="Notifications"
              >
                <svg
                  class="h-6 w-6"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M17 14v6m-3-3h6M6 10h2a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v2a2 2 0 002 2zm10 0h2a2 2 0 002-2V6a2 2 0 00-2-2h-2a2 2 0 00-2 2v2a2 2 0 002 2zM6 20h2a2 2 0 002-2v-2a2 2 0 00-2-2H6a2 2 0 00-2 2v2a2 2 0 002 2z"
                  />
                </svg>
              </button>
            </div>
            <div class="inline-flex ml-2 mt-1">
              <h3 class="text-sm font-bold text-gray-800 mr-2 uppercase">movie</h3>
            </div>
          </div>

          <div class="flex text-gray-700 text-center py-2 m-2 pr-5">
            <div class="inline-flex">
              <button
                class="border-transparent text-gray-600 rounded-full hover:text-blue-600 focus:outline-none focus:text-gray-600"
                aria-label="Notifications"
              >
                <svg
                  class="h-6 w-6"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                  />
                </svg>
              </button>
            </div>
            <div class="inline-flex ml-2 mt-1">
              <h3 class="text-sm font-medium text-gray-700 mr-2 uppercase">picture</h3>
            </div>
          </div>
        </div>

        <!--post images-->

        <div class="flex pt-4">
          <div v-for="article of articles" :key="article.slug">
            <div @click="openModal(article)" class="cursor-pointer">
              <div class="flex-1 text-center px-4 py-2 m-2">
                <img class="w-full" :src="article.top_image" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <transition name="modal">
      <Modal
        :val="item"
        v-if="showModal"
        @close="closeModal"
      />
    </transition>
  </div>
</template>
<script>
import Modal from '~/components/Modal.vue'
  export default {
  components: { Modal },
    async asyncData({ $content, params }) {
      const articles = await $content('music')
        // .only(['title', 'description', 'top_img', 'slug', 'author', 'created_at'])
        .sortBy('created_at', 'asc')
        .fetch()
      return {
        articles
      }
    },
    data() {
      return {
        item: '',
        showModal: false,
      }
    },
    methods: {
      openModal(item) {
        this.item = item;
        this.showModal = true;
        document.documentElement.style.overflow = 'hidden';
      },
      closeModal() {
        this.showModal = false;
        document.documentElement.style.overflow = 'auto';
      }
    }
  }
</script>

<style>
.modal-enter-active {
  transition: opacity 0.50s;
}
.modal-leave-active {
  transition: opacity 0.50s;
}
.modal-enter, .modal-leave-to{
    opacity: 0;
}
</style>
