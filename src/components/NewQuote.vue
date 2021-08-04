<template>
    <div class="row justify-content-center">
        <div class="mb-3 col-12 col-sm-12 col-md-8 col-lg-6">
            <label for="newQuote" class="form-label">Create a new quote</label>
            <textarea class="form-control" id="newQuote" rows="3" v-model="quote"></textarea>
        </div>
         <div class="col-12">
            <button class="btn btn-primary mb-3" @click.prevent="createQuote">Add quote</button>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            quote: 'New quote'
        }
    },
    methods: {
        createQuote(){
            this.$emit('quoteAdded', this.quote);
            this.quote = '';
        }
    }
}
</script>