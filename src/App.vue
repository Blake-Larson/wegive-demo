<script setup>
import NavBar from './components/NavBar.vue'
import OrganizationTab from './components/OrganizationTab.vue'
</script>

<template>
  <main class="px-5 py-7 flex flex-col bg-slate-100 gap-2 h-screen">
    <h3 class="text-2xl font-bold">Settings</h3>
    <div class="flex flex-col bg-white rounded-2xl px-7 py-3">
      <NavBar @tab-nav="tabNav" :activeTab="activeTab" />
      <div v-if="activeTab === 'My Profile'" class="text-center pt-10 text-2xl font-bold">
        My Profile
      </div>
      <OrganizationTab v-if="activeTab === 'Organization'" />
      <div v-if="activeTab === 'Team'" class="text-center pt-10 text-2xl font-bold">Team</div>
      <div v-if="activeTab === 'Designations'" class="text-center pt-10 text-2xl font-bold">
        Designations
      </div>
      <div v-if="activeTab === 'Tax Receipts'" class="text-center pt-10 text-2xl font-bold">
        Tax Receipts
      </div>
      <div v-if="activeTab === 'Installation'" class="text-center pt-10 text-2xl font-bold">
        Installation
      </div>
      <div v-if="activeTab === 'Payments'" class="text-center pt-10 text-2xl font-bold">
        Payments
      </div>
      <div v-if="activeTab === 'Integrations'" class="text-center pt-10 text-2xl font-bold">
        Integrations
      </div>
      <div v-if="activeTab === 'Text & Email'" class="text-center pt-10 text-2xl font-bold">
        Text & Email
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: 'App',
  components: {
    NavBar,
    OrganizationTab
  },
  data() {
    return {
      activeTab: 'Organization'
    }
  },
  methods: {
    tabNav(tab) {
      this.activeTab = tab
    }
  }
}
</script>
