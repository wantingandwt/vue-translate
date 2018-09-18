<template>
  <div id="tranbody">
     <h2>{{tranresult}}</h2>
  </div>
</template>

<script>
export default {
  name: 'tranbody',
  props:[
     "tranresult"
  ]
}
</script>

<style scoped>
#tranbody{
  width:90%;
  min-height:100px;
  border:1px solid #ddd;
  margin:30px auto;
  padding:10px;
  text-align: left;
  box-sizing: border-box
}
</style>
