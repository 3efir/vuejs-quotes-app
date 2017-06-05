<template>
    <div class="mdl-grid">
        <div class="mdl-cell mdl-cell--12-col mdl-cell--4-col-phone">
            <progress-bar :max="max" :exists="quotes.length"></progress-bar>
        </div>
        <div class="mdl-cell mdl-cell--12-col mdl-cell--4-col-phone">
            <create-form @createQuote="createQuote($event)"></create-form>
        </div>
        <quote 
            v-for="(quote, index) in quotes" 
            :index="index" 
            :key="index" 
            @deleteQuote="deleteQuote($event)"
        >{{quote}}</quote>
        <div class="mdl-cell mdl-cell--12-col mdl-cell--4-col-phone">
            <my-footer></my-footer>
        </div>
        <md-dialog-alert
            md-title="To many Quotes!"
            md-content="Delete some before adding new ones!"
            ref="dialog">
        </md-dialog-alert>
    </div>
</template>

<script>
    import myFooter from './assets/components/Footer.vue'
    import progressBar from './assets/components/ProgressBar.vue'
    import createForm from './assets/components/CreateForm.vue'
    import quote from './assets/components/Quote.vue'

    export default {
        data() {
            return {
                max: 10,
                quotes: []
            };
        },
        components: {
            myFooter,
            progressBar,
            createForm,
            quote
        },
        methods: {
            createQuote(data) {
                if(this.quotes.length < this.max) {
                    this.quotes.push(data);
                }
                else {
                    this.$refs['dialog'].open();
                }
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>

</style>