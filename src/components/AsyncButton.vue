<template>
  <base-button
      :disabled="isPending"
      :color="color"
      @click.stop.prevent="handleClick"
      v-bind="$attrs"
  >
  <span v-if="isPending">Loading...</span>
  <slot v-else></slot>
  </base-button>
</template>

<script>
import BaseButton from './BaseButton.vue'

export default {
  name: 'AsyncButton',
  components: { BaseButton },
  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },

  data () {
    return {
      isPending: false
    }
  },

  methods: {
    handleClick() {
      if (this.$attrs.onClick) {  // Use $attrs to check for the parent's @click listener
        this.isPending = true
        // Invoke the parent's click handler and disable the button while it resolves
        this.$attrs.onClick().finally(() => {
          this.isPending = false
        })
      }
    }
  }
}
</script>
