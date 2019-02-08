<template>
<div>
<headcomp :quoteCount="quotes.length" :maxQuotes="maxQuotes"> </headcomp>
<newcomp @quoteAdded="newQuote"> </newcomp>
<appQuotegrid :quotes ="quotes" @quoteDeleted="deleteQuote"> </appQuotegrid>
 <div class="col-sm-12 text-center">
      <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
  </div>
</div>

</template>

<script>
import quotegrid from './quotegrid.vue'; 
import newcomponent from './newcomponent.vue';
import Header from './Header.vue';
export default {
  data : function () {
    return {
      quotes : ['this is the first quotes'] ,
      maxQuotes: 10
    }
  },
  components:{
  appQuotegrid :quotegrid,
  newcomp: newcomponent,
  headcomp: Header
  },
  methods: {
    newQuote(quote){
    if (this.quote.length >= this.maxQuotes) {
        return alert('Please delete Quotes first!');
                }
    this.quotes.push(quote);
    },
     deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
  },
  }

</script>

<style>

</style>


