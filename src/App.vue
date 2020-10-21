<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="quoteLimit"></app-header>
        <app-add-quote @quoteAdded="addQuote"></app-add-quote>
        <br>
        <app-quotes :quotes="quotes" @quoteDeleted="deleteQuote"></app-quotes>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import AddQuote from './components/AddQuote.vue'
import Quotes from './components/Quotes.vue'
import {eventBus} from './main'

    export default {
        data: function() {
            return {
                quotes: [
                    "quote"
                ],
                quoteLimit: 10
            }
        },
        methods: {
            deleteQuote(index) {
                this.quotes.splice(index,1)
            },
            addQuote(quote) {
                if (this.quotes.length > this.quoteLimit) {
                    alert("You cannot add more quotes. Please delete one first.")
                } else {
                    this.quotes.push(quote);
                }
            }
        },
        components: {
            appHeader: Header,
            appAddQuote: AddQuote,
            appQuotes: Quotes
        },
    }
</script>

<style scoped>
    h2 {
        font-weight: bold;
    }
        .quote-bar {
        width: 100%;
        border: 1px solid gray;
        border-radius: 5px;
        box-shadow: 1px 1px 2px gray;
    }

    .quote-progress {
        color: white;
        font-weight: bold;
        text-align: center;
        background: rgb(68, 68, 184);
        height: 100%;
        width: 0%;
    }
</style>
