<template>
  <button
    @click="($event) => $emit('btn-click')"
    :class="[this.color ? this.color : '', 'py-2 px-5 rounded-xl text-white font-bold text-sm']"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'AddButton',
  props: {
    text: String,
    color: String
  }
}
</script>
