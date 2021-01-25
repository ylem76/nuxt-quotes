<template>
  <form action="">
    <label for="">Quote</label>
    <textarea
      id="quote"
      v-model="addQuote"
      class="form-control"
      name="quote"
      rows="10"
    ></textarea>
    <button @click.prevent="addNewQuote">Add Quote</button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      addQuote: '',
    }
  },
  methods: {
    addNewQuote() {
      this.$emit('adding', this.addQuote)
      this.addQuote = ''
    },
  },
}
</script>
