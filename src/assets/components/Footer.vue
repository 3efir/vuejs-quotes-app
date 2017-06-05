<template>
    <md-bottom-bar>
        <h6 class="md-center">Info: {{info}}</h6>
    </md-bottom-bar>
</template>

<script>
    export default {
        data() {
            return {
                info: 'Click on a Quote to Delete it.'
            };
        }
    }
</script>

<style scoped>
    .md-theme-default.md-bottom-bar.md-fixed {
        text-align: center;
        background-color: #68ccff;
    }
</style>