<script setup>
import IconTrash from './icons/IconTrash.vue'
import IconPencil from './icons/IconPencil.vue'
import IconCheck from './icons/IconCheck.vue'
</script>

<template>
  <div>
    <div class="text-custom-grey font-bold text-sm border-b border-slate-200 grid grid-cols-3 pb-4">
      <span>Name</span>
      <span>Email</span>
      <span>Status</span>
    </div>
    <form @submit.prevent="handleSubmit" v-for="address in addresses" :key="address.id">
      <div class="grid grid-cols-3 text-sm pt-4">
        <div class="flex justify-between items-center">
          <div v-if="edit.itemId !== address.id">{{ address.name }}</div>
          <input
            v-if="edit.itemId === address.id"
            type="text"
            name="name"
            :placeholder="address.name"
            class="border px-2 py-0.5 rounded-md"
            v-model="address.name"
          />
          <div
            v-if="!edit.active"
            @click="($event) => toggleShowForm(address.id, true)"
            class="mr-9 hover:cursor-pointer hover:bg-warning-light rounded-lg p-0.5"
          >
            <IconPencil />
          </div>
          <div
            v-if="edit.active && edit.itemId === address.id"
            @click="handleSave"
            class="mr-9 hover:cursor-pointer hover:bg-success rounded-lg p-0.5"
          >
            <IconCheck />
          </div>
        </div>
        <div>{{ address.email }}</div>
        <div class="flex justify-between items-center">
          <div
            :class="[
              address.status === 'Verified'
                ? 'bg-success-light text-success'
                : 'bg-warning-light text-warning',
              'px-4 py-0.5 rounded-md text-sm font-semibold'
            ]"
          >
            {{ address.status }}
          </div>
          <div class="hover:cursor-pointer hover:bg-warning rounded-lg p-0.5"><IconTrash /></div>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'EditCustomAddresses',
  data() {
    return {
      edit: {
        active: false,
        itemId: null
      },
      // mock data
      addresses: [
        {
          id: '1',
          name: 'Jonathan Beck',
          email: 'jonathanbeck@company.com',
          status: 'Verified'
        },
        {
          id: '2',
          name: 'Blake Larson',
          email: 'Blakelarson@company.com',
          status: 'Unverified'
        }
      ]
    }
  },
  components: {
    IconTrash,
    IconPencil,
    IconCheck
  },
  methods: {
    toggleShowForm(id, status) {
      this.edit = {
        active: status,
        itemId: id
      }
    },
    handleSave() {
      this.handleSubmit()
      this.edit = {
        active: false,
        itemId: null
      }
    },
    handleSubmit() {
      console.log('form submitted')
      this.edit = {
        active: false,
        itemId: null
      }
    }
  }
}
</script>
