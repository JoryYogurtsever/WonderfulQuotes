<template>
    <div class="container">
        <progress-bar :quoteCount="quoteCount"></progress-bar>
        <input-box @input="quoteCount++" class="innie" @counterUp="quoteCount++"></input-box>
        <quotes></quotes>
        <footerz></footerz>
        {{ quoteCount }}
    </div>
</template>

<script>
    import Progress from './components/ProgressBar.vue'
    import InputBox from './components/InputBox.vue'
    import Quotes from './components/Quotes.vue'
    import Footer from './components/Footer.vue'

    import { eventBus } from './main.js'


    export default {
        data: function() {
            return {
                quoteCount: 1
            }
        },
        components:{
            'progressBar': Progress,
            'inputBox': InputBox,
            Quotes,
            'footerz': Footer
        },
        watch: {
            quoteCount: function(){
                if (this.quoteCount >= 10) {
                    alert("Maximum Quotes Reached, please delete some quotes");
                    this.quoteCount = 10
                }
            }
        },
        created() {
            eventBus.$on('destroyed', () => {this.quoteCount--})
        }
    }
</script>

<style>
    .innie {
        padding-left: 25%
    }
</style>
