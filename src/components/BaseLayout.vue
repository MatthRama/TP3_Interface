<template>
  <div>
    <main>
      <slot></slot>
    </main>
  </div>
</template>

<script>
export default {
  name: 'BaseLayout'
}
</script>

<style scoped>

main {
  margin: 20px;
}
</style>
