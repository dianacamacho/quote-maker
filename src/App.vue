<template>
  <div class="container">
<!-- when listening for emitted event, vue auto passes the $event (the new quote in this case), so don't really need to write in the argument like below, but you can -->
    <!-- <appNewQuote @quoteAdded="newQuote($event)"></appNewQuote> -->
    <appNewQuote @quoteAdded="newQuote"></appNewQuote>
    <appQuoteGrid :quotes="quotes"></appQuoteGrid>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue'
  import NewQuote from './components/NewQuote.vue'
 
  export default {
    data: function() {
      return {
        quotes: ['Just a quote'],
        maxQuotes: 10
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote
    },
    methods: {
      newQuote(quote) {
        this.quotes.push(quote);
      }
    }
  }
</script>

<style>

</style>
