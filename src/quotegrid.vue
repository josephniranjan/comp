<template>
 <div class="row">
 <appQuote v-for="(quote,key) in quotes" :key="quote.id"  @click.native="deleteQuote(key)"> {{ quote }} </appQuote>
 </div>

</template>

<script>
import quote from './quotes.vue';
export default {
  props : ['quotes'],
 components:{
  appQuote: quote
  },
   methods: {
            deleteQuote(key) {
                this.$emit('quoteDeleted', key);
            }
        }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
