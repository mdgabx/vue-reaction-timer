<template>
    <div class="blocks" v-if="showBlocks">
        click me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlocks: false
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlocks = true
        }, this.delay)
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