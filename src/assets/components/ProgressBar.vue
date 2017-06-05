<template>
    <div class="mdl-grid">
        <h5><b>Quotes Added   {{exists}}/{{max}}</b></h5>
        <md-progress :md-progress="progress"></md-progress>
    </div>
</template>

<script>
    export default {
        props: {
            max: {
                type: Number,
                required: true
            },
            exists: {
                type: Number,
                default: 0
            }
        },
        data() {
            return {
                test: "1/10"
            };
        },
        computed: {
            progress() {
                return (this.exists / this.max) * 100; 
            }
        }
    }
</script>

<style scoped>
    .md-progress {
        height: 20px;
    }
</style>