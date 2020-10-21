<template>
    <div class="container">
        <h3>Quote</h3>
        <textarea class="form-control" name="quote" id="" cols="30" rows="10" v-model="newQuote"></textarea>
        <button class="btn btn-primary" @click="addQuote">Add Quote</button>
    </div>
</template>

<script>
import {eventBus} from '../main'

    export default {
        data() {
            return {
                newQuote: ""
            }
        },
        methods: {
            addQuote() {
                // eventBus.addQuote(this.newQuote)
                this.$emit("quoteAdded", this.newQuote)
                this.newQuote = ""
            }
        }
    }
</script>

<style scoped>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    h3 {
        font-weight: bold;
        width: 50%
    }

    textarea {
        width: 50%;
    }

    button {
        margin: 10px 0;
        font-weight: bold;
    }
</style>
