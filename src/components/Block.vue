<template>
  <div class="block">click Here {{delay}} </div>
</template>

<script>
export default {
    props:['delay']
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