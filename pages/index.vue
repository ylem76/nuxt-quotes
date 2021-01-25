<template>
  <section>
    <the-header
      :quote-count="quotes.length"
      :max-quotes="maxQuotes"
    ></the-header>
    <add-quote @adding="addNewQuote"></add-quote>
    <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid>
    <div class="info-text">
      <p>Info : Click on a Quote to delete it!</p>
    </div>
  </section>
</template>

<script>
import AddQuote from '../components/AddQuote.vue'
import QuoteGrid from '../components/QuoteGrid.vue'
import TheHeader from '../components/TheHeader.vue'

export default {
  components: { AddQuote, QuoteGrid, TheHeader },
  data() {
    return {
      quotes: [
        { id: 1, quote: 'Just a Quote to see something' },
        { id: 2, quote: 'testQuote 2' },
        { id: 3, quote: 'testQuote 3' },
        { id: 4, quote: 'testQuote 4' },
      ],
      maxQuotes: 9,
    }
  },
  methods: {
    addNewQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert('최대 개수 초과됐습니다. 먼저 지우세요')
      }
      const quoteItem = {
        id: new Date().toISOString(),
        quote,
      }

      this.quotes.push(quoteItem)
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1)
    },
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.info-text {
  text-align: center;
  width: 90%;
  margin: 5%;
  border-radius: 10px;
  background-color: #eee;
  padding: 3%;
}
</style>
