<template>
    <div class="block" v-if="delayClick" @click="stopTimer">
        click Me
    </div>  
</template>


<script>
export default {
    props: ['delay'],
    data(){
        return{
            delayClick : false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted(){
        setTimeout(()=>{
            this.delayClick = true;
            this.startTimer();
        }, this.delay)
    },
    methods: {
        startTimer(){
            this.timer= setInterval(()=>{
                this.reactionTime += 10;
            },10)
        },
        stopTimer(){
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    },

    updated() {
        console.log("updated")
    },
}
</script>

<style>
.block{
    width: 400px;
    border-radius: 20px;
    background: lightcyan;
    color: cadetblue;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto; 
}
</style>