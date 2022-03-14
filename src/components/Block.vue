<template>
  <div class="block" v-if="showBlock">click Here {{delay}} </div>
</template>

<script>
export default {
    props:['delay'],
    data() {
        return {
            showBlock:false
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showBlock = true;
        },this.delay);
    },
    updated() {
        console.log("data updated");
    },
    unmounted() {
        console.log('component ummounted');
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