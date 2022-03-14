<template>
  <div class="block" v-if="showBlock" @click="stopTimer">click Here </div>
  
</template>

<script>
export default {
    props:['delay'],
    data() {
        return {
            showBlock:false,
            score:0,
            timer:null
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showBlock = true;
            this.startTimer();
        },this.delay);
    },
    methods: {
        startTimer() {
            this.timer = setInterval(()=>{
                this.score += 50;
            },50)
        },
        stopTimer() {
            clearInterval(this.timer);
            
            this.$emit("endGame",this.score);
        }
    }
}
</script>

<style scoped>
.block{
    color: white;
width : 400px;
height :200px;
text-align: center;
background-color: green;
margin: 30px auto;
padding-top: 60px;
}
</style>