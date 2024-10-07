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

    <AsyncButton color="primary" @click="handleAsyncButtonClick">
      AsyncButton with increasing delay ({{ clickCount }}s)
    </AsyncButton>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue'
import AsyncButton from './AsyncButton.vue'

export default {
  name: 'HomePage',
  components: {
    BaseButton,
    AsyncButton
  },
  data() {
    return {
      clickCount: 1
    }
  },
  methods: {
    handleAsyncButtonClick() {
      return new Promise((resolve) => {
        setTimeout(() => {
          this.clickCount += 1
          resolve()
        }, this.clickCount * 1000)
      })
    }
  }
}
</script>

<style scoped>
.custom-margin {
  margin: 20px;
}
</style>
