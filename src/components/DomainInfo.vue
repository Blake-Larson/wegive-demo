<script setup>
import DomainInfoExt from './DomainInfoExt.vue'
import EditCustomAddresses from './EditCustomAddresses.vue'
import AddButton from './buttons/AddButton.vue'
</script>

<template>
  <div class="flex flex-col gap-4">
    <DomainInfoExt
      title="Authenticate domain"
      number="1"
      desc="Authenticate domain information..."
    />
    <DomainInfoExt
      title="Manage custom addresses"
      number="2"
      desc="Custom addresses can be used as ”from” and ”reply-to” addresses when you send emails. This
          is useful if you'd like certain outbound emails to appear as coming from a team, or if
          you'd like to change how your name appears in email clients."
    >
      <EditCustomAddresses />
      <AddButton
        class="self-end"
        @btn-click="($event) => $emit('toggle-add-domain')"
        text="Add a custom address"
        color="bg-primary"
      />
    </DomainInfoExt>
  </div>
</template>

<script>
export default {
  name: 'DomainInfo',
  components: { DomainInfoExt, EditCustomAddresses, AddButton }
}
</script>
