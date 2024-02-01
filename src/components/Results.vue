<template>
    <p>Reaction time: {{ score }} ms</p>
    <p>{{ rank }}</p>
</template>

<script>
    export default {
        props: ['score'],
        data() {
            return {
                rank: null
            }
        },
        mounted() {
            if(this.score <= 250) {
                this.rank = 'Fast hands'
            } else if (this.score <= 450) {
                this.rank = 'Mid'
            } else {
                this.rank = 'Slow Men!'
            }
        }
    }

</script>

<style scoped>

</style>
