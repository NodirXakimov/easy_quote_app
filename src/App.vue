<template>
  <div id="app" class="text-center mt-3 container">
    <h1>Quoter App</h1>
    <app-header :maxQuote="maxQuotes" :quotesCount="quotes.length"></app-header>
    <app-new-quote @quoteAdded="quoteAdded"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="quoteDeleted"></app-quote-grid>
    <div class="row justify-content-center">
      <div class="col-sm-12 col-md-8 col-lg-6">
        <div class="alert alert-info" role="alert">
          Info: Click a quote to delete it !!!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'
import Header from './components/Header.vue'

export default {
  data () {
    return {
      quotes: ['Initial cool quote', 'Second pretty quote', 'Some new quote else', 'I like digging holes and hiding things inside them', 'When I grow old I hope I won\'t forget to find them'],
      maxQuotes: 10,
    }
  },
  methods: {
    quoteAdded(quote){
      if(quote == ''){
        return alert('Please fill out the field');
      }
      if(this.quotes.length >= 10){
        return alert(`Delete quote first to add new one !!!`);
      }
      this.quotes.push(quote);
    },
    quoteDeleted(index){
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header,
  }
}
</script>
<style>
  h1 {
    font-family: 'MonteCarlo', cursive;
  }
</style>