<template>
  <div class="container">
   <Header :quoteCount="quotes.length" :maxQuotes="maxQuotes"/>
   <NewQuote @quoteAdded="newQuote"/>
   <QuoteGrid :quotes="quotes" @deleteQuote="deleteQuote"/>
   <div class="row">
     <div class="col-12">
        <div class="alert alert-info text-center">
          <p>click to delete</p>
        </div>
     </div>
   </div>
  </div>
</template>


<script>
import QuoteGrid from '@/components/QuoteGrid' 
import NewQuote from '@/components/NewQuote'
import Header from '@/components/Header'
export default {
  components:{
    QuoteGrid,
    NewQuote,
    Header
  },
  data(){
    return{
      quotes: ['Just a quote'],
      maxQuotes : 10
    }
  },
  methods:{
    newQuote(quote){
      if (this.quotes.length >= this.maxQuotes){
        return alert('Please delete quote first')
      }
      this.quotes.push(quote)
    },
    deleteQuote(index){
      this.quotes.splice(index,1);
    }
  }
}
</script>
