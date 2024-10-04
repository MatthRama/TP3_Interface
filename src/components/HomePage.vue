<template>
  <div>
    <h1>Welcome to the Home Page</h1>

    <!-- Button with custom margin -->
    <BaseButton customClass="custom-margin">
      BaseButton with custom margin
    </BaseButton>

    <!-- Disabled button -->
    <BaseButton :disabled="true">
      BaseButton disabled
    </BaseButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue'

export default {
  name: 'HomePage',
  components: {
    BaseButton
  }
}
</script>

<style scoped>
.custom-margin {
  margin: 20px;
}
</style>
