<template>
  <div>
    <h1>Welcome to the Home Page</h1>

    <BaseButton customClass="custom-margin" color="primary">
      BaseButton with primary color
    </BaseButton>

    <BaseButton customClass="custom-margin" color="warn">
      BaseButton with color props
    </BaseButton>

    <BaseButton customClass="custom-margin" color="danger">
      BaseButton with color props
    </BaseButton>

    <BaseButton :disabled="true" customClass="custom-margin">
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
