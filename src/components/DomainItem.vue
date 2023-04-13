<script setup>
import IconChevronRight from './icons/IconChevronRight.vue'
import IconEnvelope from './icons/IconEnvelope.vue'
import IconExclamation from './icons/IconExclamation.vue'
import DomainInfo from './DomainInfo.vue'
</script>

<template>
  <div
    @click="toggleDomainInfo"
    :class="[
      this.showDomainInfo ? 'border-primary border-b-0 rounded-b-none' : 'border-slate-100',
      'w-full flex items-center gap-4 border  py-8 px-6 rounded-2xl relative hover:cursor-pointer'
    ]"
  >
    <div class="text-primary">
      <IconEnvelope />
    </div>
    <div class="font-bold">{{ domain.name }}</div>
    <div
      :class="[
        domain.status === 'Authenticated'
          ? 'bg-success-light text-success'
          : 'bg-warning-light text-warning',
        'px-4 py-0.5 rounded-md text-sm font-semibold'
      ]"
    >
      {{ domain.status }}
    </div>
    <div class="absolute right-6 flex gap-14">
      <div v-if="domain.issue" class="text-warning font-semibold flex gap-1">
        <IconExclamation />
        <span>{{ domain.issue }}</span>
      </div>
      <div
        :class="[
          this.showDomainInfo ? 'rotate-90' : '',
          'text-custom-grey transition-all duration-200'
        ]"
      >
        <IconChevronRight />
      </div>
    </div>
  </div>

  <div
    v-if="this.showDomainInfo"
    class="border border-primary border-t-0 rounded-2xl rounded-t-none flex flex-col"
  >
    <div v-if="this.showDomainInfo" class="h-[1px] w-11/12 bg-slate-200 self-center"></div>
    <div class="m-5">
      <DomainInfo />
    </div>
  </div>
</template>

<script>
export default {
  name: 'DomainItem',
  props: {
    domain: {
      type: Object
    }
  },
  data() {
    return {
      showDomainInfo: false
    }
  },
  components: { IconEnvelope, IconChevronRight, DomainInfo, IconExclamation },
  methods: {
    toggleDomainInfo() {
      this.showDomainInfo = !this.showDomainInfo
    }
  }
}
</script>
