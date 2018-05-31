<template>
    <div class="quote" @click="destroyer()" v-if="shower">
        <slot>

        </slot>
    </div>
</template>

<script>
    import { eventBus } from '../main.js'

    export default{
        data: function(){
            return{
                shower: true
            }
        },
        methods:{
            destroyer() {
                this.shower = false;
                eventBus.$emit('destroyed')
            }
        }
    }

</script>

<style scoped>
    .quote {
        font-family: 'Arizonia', sans-serif;
        font-size: 2em;
        height: 110px;

        float: left;
        border: 1px solid black;
        padding: 5%;
        text-align: center
    }
</style>