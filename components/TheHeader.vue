<template>
  <header>
    <h3>Quotes Added</h3>
    <div class="progress">
      <div
        class="progress-bar"
        :style="{ width: (quoteCount / maxQuotes) * 100 + '%' }"
      >
        {{ quoteCount }} / {{ maxQuotes }}
      </div>
    </div>
  </header>
</template>
<script>
export default {
  props: {
    quoteCount: {
      type: Number,
      default: 0,
    },
    maxQuotes: {
      type: Number,
      default: 10,
    },
  },
}
</script>
<style scoped>
.progress-bar {
  background: green;
  transition: all 0.3s ease;
}
</style>
