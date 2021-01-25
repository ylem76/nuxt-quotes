<template>
  <div class="quote-wrapper">
    <quote-item
      v-for="(item, index) in quotes"
      :key="index"
      :quote="item.quote"
      @click.native="deleteQuote(index)"
    >
      {{ item.quote }}
    </quote-item>
  </div>
</template>
<script>
import QuoteItem from './QuoteItem.vue'
export default {
  components: { QuoteItem },
  props: {
    quotes: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    deleteQuote(index) {
      this.$emit('quoteDeleted', index)
    },
  },
}
</script>
<style scoped>
.panel-body {
  font-size: 24px;
  color: #6e6e6e;
}
.quote {
  cursor: pointer;
}
.puote:hover {
  background-color: #ffe2e2;
}
.quote-wrapper {
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
  width: 90%;
  margin: 5%;
}
</style>
