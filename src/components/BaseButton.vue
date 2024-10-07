<template>
  <button
      :class="[
      'base-button',
      colorClass,
      { 'base-button--disabled': disabled },
      customClass
    ]"
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
      default: 'button',
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
      default: '',
    },
    color: {
      type: String,
      default: 'primary',
      validator(value) {
        return ['primary', 'warn', 'danger'].includes(value);
      }
    }
  },
  computed: {
    colorClass() {
      return `base-button--${this.color}`;
    }
  }
}
</script>

<style scoped>

.base-button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s ease, transform 0.3s ease;
  color: white;
}

.base-button--primary {
  background-color: green;
}

.base-button--primary:hover {
  background-color: #28a745;
}

.base-button--warn {
  background-color: orange;
}

.base-button--warn:hover {
  background-color: #ff9800;
}

.base-button--danger {
  background-color: red;
}

.base-button--danger:hover {
  background-color: #d32f2f;
}

.base-button--disabled {
  background-color: gray;
  cursor: not-allowed;
}

.base-button:disabled {
  background-color: gray;
}
</style>
