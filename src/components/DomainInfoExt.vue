<script setup>
import IconChevronRight from './icons/IconChevronRight.vue'
</script>

<template>
  <div
    :class="[
      this.extendedView ? 'border border-primary pb-8' : '',
      'w-full flex flex-col rounded-2xl  px-5 '
    ]"
  >
    <div
      @click="toggleExtendedView"
      class="flex items-center gap-4 pt-8 pb-4 px-6 relative hover:cursor-pointer"
    >
      <div class="flex gap-4 items-center w-full">
        <div
          class="rounded-full border border-slate-950 w-6 h-6 flex justify-center items-center text-lg"
        >
          {{ number }}
        </div>
        <h5 v-if="title" class="font-bold">{{ title }}</h5>
      </div>

      <div class="absolute right-6 flex gap-14">
        <div
          :class="[
            this.extendedView && 'rotate-90',
            'text-custom-grey transition-all duration-200'
          ]"
        >
          <IconChevronRight />
        </div>
      </div>
    </div>
    <div v-if="this.extendedView" class="px-16 flex flex-col gap-7">
      <p class="text-sm">{{ desc }}</p>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DomainInfoExt',
  props: {
    title: {
      type: String,
      required: true
    },
    number: {
      type: String,
      required: true
    },
    desc: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      extendedView: false
    }
  },
  components: { IconChevronRight },
  methods: {
    toggleExtendedView() {
      this.extendedView = !this.extendedView
    }
  }
}
</script>
