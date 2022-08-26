<template>
    <div class="result">
        Your Score is {{score}} ms
        your rank is {{rank}}
    </div>  
</template>

<script>
export default{
    props : ['score'],
    data(){
        return{
            rank : ''
        }
    },
    mounted(){
        if(this.score <250){
            this.rank ="god of click"
        }else{
            this.rank= 'noob as shit'
        }
    }

}
</script>
<style scoped>
.result{
    width: 400px;
    border-radius: 20px;
    background: lightcyan;
    color: cadetblue;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto; 
}
</style>