<template>
    <div class="row">
        <Quote v-for="quote in quotes" :key="quote.index" @click.native="deleteQuote(index)"> {{ quote }} </Quote>
    </div>
</template>

<script>
import Quote from '@/components/Quotes' 
export default {
    props :['quotes'],
    components:{
        Quote
    },
    methods:{
        deleteQuote(index){
            this.$emit("deleteQuote", index)
        }

    }
}
</script>

