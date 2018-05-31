<template>
    <div class="col-sm-6 col-md-4 col-lg-3" @click="destroyer()" v-if="shower">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot>

                </slot>
            </div>
        </div>
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
    .panel-body{
        font-family: 'Arizonia', cursive;
        font-size: 24px;
        color: #6e6e6e
    }
    .quote {
        cursor: pointer;
    }
    .quote:hover {
        background-color: #ffe2e2;
    }
 /*   .quote {
        font-family: 'Arizonia', sans-serif;
        font-size: 2em;
        height: 110px;

        float: left;
        border: 1px solid black;
        padding: 5%;
        text-align: center
    }*/
</style>