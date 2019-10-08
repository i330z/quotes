<template>
    <div class="row">
        <div class="col-md-12">
            <form>
                <div class="col-md-8">
                    <label> Quotes </label>
                    <textarea class="form-control" v-model="quote" rows="10"></textarea>
                </div>
                <div class="col-md-6 col-md-offset-3">
                    <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
import Quote from '@/components/Quotes' 
export default {
    data(){
        return{
            quote: ''
        }
    },
    components:{
        Quote
    },
    methods:{
        createNew(){
            this.$emit('quoteAdded', this.quote);
            this.quote = ""
        }
    }
}
</script>
