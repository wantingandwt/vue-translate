<template>
  <div id="tranform">
    <form v-on:submit="submitForm">
	   <input type="text" v-model="text" placeholder="请输入需要翻译的内容">
	   <select v-model="lanage">
	      <option value="en">英语</option>
		  <option value="kor">韩语</option>
		  <option value="fra">法语</option>
		  <option value="jp">日语</option>
	   </select>
	   <input type="submit" value="翻译">
	</form>
  </div>
</template>

<script>
export default {
  name: 'tranform',
  data () {
    return {
      text:'',
	  lanage:'en'
    }
  },
  methods:{
      submitForm:function(e){
	     this.$emit("formText",this.text,this.lanage);
		 e.preventDefault();//禁止刷新
	  }
  }
}
</script>

<style scoped>

</style>
