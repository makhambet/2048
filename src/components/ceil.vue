<template>
    <div>
        {{number}}
    </div>
</template>

<script>
    export default {
        props: {
            ceil: {
                type: Number,
                default: 2
            },
        },
        data() {
            return {
                number: 4,
                rand: 0
            }
        },
        computed: {
            newCeil() {
                this.rand = Math.floor((Math.random() * 2) + 1);
                console.log(this.rand)
                return this.rand
            }
        },
    }
</script>

<style scoped>
    div{
        background: rgb(135, 226, 147);
        font-size: 60px;
        width: 100%;
        height: 100%;
        color: #fff;
        position: absolute;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        text-align: justify;
        font-weight: bold;
        z-index: 1;
        border-radius: 7%;
        -webkit-transform: translateZ(0);
    }
</style>