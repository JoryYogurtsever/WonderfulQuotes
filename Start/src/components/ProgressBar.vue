<template>
    <div>
        <h2>Quotes Added</h2>
        <div class="bar">
            <div class="bar" style="background-color: dodgerblue; margin: 0; color: white; text-align: center" :style="{width: quoteCount * 10 + '%'}"> {{ quoteCount }} / 10 </div>
        </div>
    </div>
</template>

<script>
    export default {

        props: {
            quoteCount:{
                type: Number,
                default: 1

            }
        }
    }
</script>

<style scoped>
    h2 {
        font-weight: bold
    }
    /*   .bar {
           width: 80%;
           height: 40px;
           background-color: #eee;
           margin: auto;
           transition: width 500ms;
       }*/
    .bar {
        height: 1.4em;
        width: 100%;
        background-color: #eee;
        border-radius: 5px
    }
</style>