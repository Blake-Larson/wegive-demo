<script setup>
import NavBar from './components/NavBar.vue'
import OrganizationTab from './components/OrganizationTab.vue'
</script>

<template>
  <main class="px-5 py-7 flex flex-col bg-slate-100 gap-2 h-screen">
    <h3 class="text-2xl font-bold">Settings</h3>
    <div class="flex flex-col bg-white rounded-2xl px-7 py-3">
      <NavBar />
      <OrganizationTab />
    </div>
  </main>
</template>

<script>
export default {
  name: 'OrganizationTab',
  components: {
    NavBar,
    OrganizationTab
  }
}
</script>
