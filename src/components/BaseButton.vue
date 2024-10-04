<template>
  <button
      :class="['base-button', { 'base-button--disabled': disabled }, customClass]"
      :disabled="disabled"
      :type="type"
      :role="role"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    type: {
      type: String,
      default: 'button',  // Can be 'button', 'submit', etc.
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    role: {
      type: String,
      default: 'button',
    },
    customClass: {
      type: String,
      default: '',  // Additional class for custom styling
    }
  }
}
</script>

<style scoped>
.base-button {
  background-color: green;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.base-button:hover {
  background-color: #28a745;
  transform: scale(1.05);
}

.base-button:focus {
  outline: none;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
  transform: scale(1.05);
}

.base-button--disabled {
  background-color: gray;
  cursor: not-allowed;
}

.base-button:disabled {
  background-color: gray;
}
</style>
