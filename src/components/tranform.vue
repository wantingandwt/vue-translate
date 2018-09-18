<template>
  <div id="tranform">
    <form v-on:submit="submitForm">
	   <textarea  v-model="text" placeholder="请输入需要翻译的内容"></textarea>
		 <div class="tranform-input">
			<span>选择翻译语言：</span>
			<select v-model="lanage">
					<option value="en">英语</option>
					<option value="kor">韩语</option>
					<option value="fra">法语</option>
					<option value="jp">日语</option>
					<option value="yue">粤语</option>
					<option value="wyw">文言文</option>
					<option value="spa">西班牙语</option>
					<option value="th">泰语</option>
					<option value="ru">俄语</option>
					<option value="de">德语</option>
					<option value="it">意大利语</option>
			</select>
			<input type="submit" value="翻译" class="tranform">
		 </div>
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
textarea{
	width:90%;
	border: 1px solid #ddd;
	height: 100px;
	padding:10px;
	box-sizing: border-box
}
.tranform-input{
	margin-top:20px;
}
.tranform{
	background:#3c7fef;
	font-size:16px;
  padding:6px 15px;
	color:#fff;
	border:0;
	margin-left:10px;
	border-radius: 5px;
}
select{
	height:30px;
	line-height: 30px;
	width:30%;
}
</style>
