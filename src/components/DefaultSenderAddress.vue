<template>
  <div class="flex flex-col gap-2 max-w-xl">
    <h5 class="font-bold">Default sender address</h5>
    <form>
      <div class="flex flex-col gap-4">
        <div class="flex flex-col gap-2">
          <div class="flex gap-3">
            <input
              type="radio"
              id="weGive"
              value="weGive"
              v-model="organization.senderAddress"
              class="w-5 accent-primary"
            />
            <label for="weGive">Use a WeGive email address</label>
          </div>
          <p class="text-sm">
            Emails and notifications will send from firstname.lastname@companyname.wegive.org
          </p>
        </div>
        <div class="flex flex-col gap-2">
          <div class="flex gap-3">
            <input
              type="radio"
              id="custom"
              value="custom"
              v-model="organization.senderAddress"
              class="w-5 accent-primary"
            />
            <label for="custom">Use a custom email address</label>
          </div>
          <p class="text-sm">
            Emails and notifications will send from the address each teammate signed up with, and
            appear as they're coming from your company domain.
          </p>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'DefaultSenderAddress',
  data() {
    return {
      // mock data
      organization: {
        senderAddress: 'custom'
      }
    }
  },
  methods: {
    // could add a method to submit a request to the API to update the organization's senderAddress
  }
}
</script>
