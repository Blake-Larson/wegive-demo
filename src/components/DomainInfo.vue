<script setup>
import IconChevronRight from './icons/IconChevronRight.vue'
</script>

<template>
  <div
    @click="toggleAuthDomain"
    :class="[
      this.showAuthDomain ? 'border-primary border-b-0 rounded-b-none border' : '',
      'w-full flex items-center gap-4 py-8 px-6 rounded-2xl relative hover:cursor-pointer'
    ]"
  >
    <div class="flex gap-4 items-center py-4 px-14 w-full">
      <div
        class="rounded-full border border-slate-950 w-6 h-6 flex justify-center items-center text-lg"
      >
        1
      </div>
      <h5 class="font-bold">Authenticate domain</h5>
    </div>

    <div class="absolute right-6 flex gap-14">
      <div
        :class="[
          this.showAuthDomain ? 'rotate-90' : '',
          'text-custom-grey transition-all duration-200'
        ]"
      >
        <IconChevronRight />
      </div>
    </div>
  </div>

  <div
    v-if="this.showAuthDomain"
    class="border border-primary border-t-0 rounded-2xl rounded-t-none flex flex-col"
  >
    <div v-if="this.showAuthDomain" class="h-[1px] w-11/12 bg-slate-200 self-center"></div>
    <div class="p-5">Authenticate domain information...</div>
  </div>
  <div class="flex gap-4 items-center py-4 px-14 w-full">
    <div
      class="rounded-full border border-slate-950 w-6 h-6 flex justify-center items-center text-lg"
    >
      2
    </div>
    <h5 class="font-bold">Manage custom addresses</h5>
  </div>
</template>

<script>
export default {
  name: 'DomainInfo',
  props: {
    domain: {
      type: Object
    }
  },
  data() {
    return {
      showAuthDomain: false,
      showCustomAddresses: false
    }
  },
  components: { IconChevronRight },
  methods: {
    toggleAuthDomain() {
      this.showAuthDomain = !this.showAuthDomain
    },
    toggleCustomAddresses() {
      this.showCustomAddresses = !this.showCustomAddresses
    }
  }
}
</script>
