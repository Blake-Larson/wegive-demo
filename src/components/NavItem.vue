<template>
  <li
    :class="[
      activeTab === name ? 'pb-6 w-full text-custom-grey' : 'border-b-2 border-primary pb-6 ',
      'w-full'
    ]"
    @click="($event) => $emit('tab-nav', name)"
  >
    {{ name }}
  </li>
</template>

<script>
export default {
  name: 'NavItem',
  props: {
    activeTab: {
      type: String
    },
    name: {
      type: String
    }
  }
}
</script>
