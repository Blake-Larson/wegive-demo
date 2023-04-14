<script setup>
import NavItem from './NavItem.vue'
</script>

<template>
  <nav class="pt-6">
    <ul class="flex justify-evenly text-primary font-bold text-center hover:cursor-pointer">
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="My Profile"
      />
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="Organization"
      />
      <NavItem :activeTab="activeTab" @tab-nav="($event) => $emit('tab-nav', $event)" name="Team" />
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="Designations"
      />
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="Tax Receipts"
      />
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="Installation"
      />
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="Payments"
      />
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="Integrations"
      />
      <NavItem
        :activeTab="activeTab"
        @tab-nav="($event) => $emit('tab-nav', $event)"
        name="Text & Email"
      />
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  props: {
    activeTab: {
      type: String,
      default: 'organization'
    }
  },
  components: { NavItem }
}
</script>
