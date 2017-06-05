<template>
    <div class="mdl-grid">
        <div class="mdl-layout-spacer"></div>
        <form class="mdl-cell mdl-cell--8-col mdl-cell--3-col-phone">
            <div class="mdl-textfield mdl-js-textfield mdl-cell mdl-cell--12-col mdl-cell--4-col-phone">
                <textarea class="mdl-textfield__input " type="text" rows= "3" id="quote-input" v-model="newQuote"></textarea>
            </div>
            <md-button class="md-raised md-primary" @click.native="createNewQuote">Add Quote</md-button>
        </form>
        <div class="mdl-layout-spacer"></div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                newQuote: ''
            };
        },
        methods: {
            createNewQuote() {
                if(this.newQuote) {
                    this.$emit('createQuote', this.newQuote);
                    this.newQuote = '';
                }
            }
        }
    }
</script>

<style scoped>
    button {
        display: block;
        left: 45%;
    }
    textarea {
        border: 1px solid #3949ab;
    }
</style>