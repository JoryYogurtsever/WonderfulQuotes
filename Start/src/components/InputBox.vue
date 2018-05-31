<template>
    <div>
        <h4>Quotes</h4>
        <form>
            <div class="form-group">
                <textarea class="inbox form-control" placeholder="write a quote!" v-model="quote"></textarea><br>
                <input type="submit" @click.prevent="addedQuote(event)" value="Add Quote"> <!--@click="counterUp()"-->
            </div>
        </form>
    </div>
</template>

<script>
    import {eventBus} from '../main.js'
    export default {
        data: function(){
            return {
                quote:''
            }
        },
        props: {
            quoteCount:{
                type: Number,
                default: 1

            }
        },
        methods: {
            addedQuote(){
                if (this.quoteCount <= 9){
                    console.log(this.quote);
                    eventBus.$emit('addedQuote', this.quote);
                    this.$emit('counterUp');
                    this.quote = ''
                } else {
                   this.prevent()
                }
//            },
  //          counterUp(){
    //            this.$emit('counterUp')
            }
        }
    }
</script>

<style scoped>
    .inbox {
        height: 70px;
        width: 500px;
    }
</style>