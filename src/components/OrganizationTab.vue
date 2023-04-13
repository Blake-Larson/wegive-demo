<script setup>
import AddButton from './AddButton.vue'
import DomainItem from './DomainItem.vue'
import IconBook from './icons/IconBook.vue'
</script>

<template>
  <section class="py-7">
    <div class="flex justify-between items-start">
      <div class="flex flex-col gap-1.5">
        <h4 class="text-lg font-bold">Manage custom address</h4>
        <p class="text-lg">
          Verify custom addresses and authenticate their domains to improve your email delivery
          rates
        </p>
        <div class="flex gap-1 items-center py-1 text-primary">
          <IconBook />
          <span class="text-sm font-semibold">How custom addresses work</span>
        </div>
      </div>
      <AddButton @btn-click="toggleAddDomain" text="Add a custom address" color="bg-primary" />
    </div>

    <!-- Add a component called AddDomain, show conditionally if showAddDomain is true -->

    <div class="flex flex-col gap-4 py-5">
      <div v-for="domain in domains" :key="domain.id">
        <DomainItem :domain="domain" />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'OrganizationTab',
  components: {
    AddButton,
    DomainItem,
    IconBook
  },
  data() {
    return {
      showAddDomain: false,
      // mock data
      domains: [
        { id: '1', name: 'domainname.com', status: 'Unathenticated', issue: 'Fix domain Issue' },
        { id: '2', name: 'domainname.com', status: 'Authenticated', issue: '' }
      ]
    }
  },
  methods: {
    toggleAddDomain() {
      this.showAddDomain = !this.showAddDomain
      console.log(this.showAddDomain ? 'AddDomain Shown' : 'AddDomain Hidden')
    }
  }
}
</script>
