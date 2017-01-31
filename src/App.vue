<template>
  <div class="container">
<!-- when listening for emitted event, vue auto passes the $event (the new quote in this case), so don't really need to write in the argument like below, but you can -->
    <!-- <appNewQuote @quoteAdded="newQuote($event)"></appNewQuote> -->
    <appHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes"></appHeader>
    <appNewQuote @quoteAdded="newQuote"></appNewQuote>
    <appQuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"></appQuoteGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue'
  import NewQuote from './components/NewQuote.vue'
  import Header from './components/Header.vue'
 
  export default {
    data: function() {
      return {
        quotes: ['Just a quote'],
        maxQuotes: 10
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    },
    methods: {
      newQuote(quote) {
        this.quotes.push(quote);
      },
      deleteQuote(index) {
        this.quotes.splice(index, 1);
      }
    }
  }
</script>

<style>

</style>
