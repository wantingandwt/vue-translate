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
  width:300px;
  height:500px;
  border:1px solid #ddd;
  margin:30px auto;
  padding:30px;
}
</style>
