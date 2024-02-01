<template>
    <div class="blocks" v-if="showBlocks" @click="stopTime">
        click me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlocks: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlocks = true
            this.startTime()
        }, this.delay)
    },
    methods: {
        startTime() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTime() {
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    }
}
</script>

<style scoped>
    .blocks {
        display: block;
        width: 200px;
        height: 300px;
        background: green;
        color: white;
        margin: 1rem auto
    }

</style>