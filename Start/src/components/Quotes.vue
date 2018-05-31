<template>
    <div>
        <div v-for="quote in quotes"><quote>{{ quote }}</quote></div>
    </div>
</template>

<script>
    import { eventBus } from '../main.js'
    import quote from './Quote.vue'

    export default {
        data: function(){
            return{
                quotes: ['Just a Quote to start with something']
            }
        },
        components: {
          quote
        },
        created() {
            eventBus.$on('addedQuote', (info) => {this.quotes.push(info)})
        }
    }
</script>


<style scoped>
  /*  .quote {
        width:350px;
        float: left;
        margin: 15px
    }*/
</style>
