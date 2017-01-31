<template>
  <div class="row">
    <appQuote v-for="quote in quotes">
      <p>{{ quote }}</p>
    </appQuote>
  </div>
</template>

<script>
  import Quote from './Quote.vue'
  
  export default {
    props: ['quotes'],
    components: {
      appQuote: Quote
    }
  }
</script>

<style>
  
</style>