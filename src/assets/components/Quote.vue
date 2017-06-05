<template>
    <div class="mdl-cell mdl-cell--3-col mdl-cell--1-col-phone quote" @click="deleteQuote">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        props: ['index'],
        methods: {
            deleteQuote() {
                this.$emit('deleteQuote', this.index);
            }
        }
    }
</script>

<style scoped>
    .quote {
        box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
        float: left;
        border: 1px solid #bfc0c1;
        padding: 20px 20px;
        font-size: 30px;
        font-style: italic;
        cursor: pointer;
    }
</style>