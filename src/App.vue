<template>
  <div id="app">
    <h1 class="app-index"><img src="./assets/logo.png"><br/>在线翻译</h1>
		<h5>高效 / 快捷 / 方便</h5>
		<Tranform v-on:formText="formTextto"></Tranform>
		<Tranbody v-text="tranresult"></Tranbody>
		<div class="footer">
     技术支持：sedlice
		</div>
  </div>
</template>

<script>
import Tranform from './components/tranform'
import Tranbody from './components/tranbody'
import md5 from 'js-md5'
export default {
  name: 'App',
  components: {
     Tranform,
	 Tranbody
  },
  data:function(){
     return{
	    tranresult:''
	 }
  },
  methods:{
    formTextto:function(text,lang){
	   let str1 = '你的id'+text+'12345678'+'你的key';
	   let signt=md5(str1);
	   this.$http.jsonp('http://api.fanyi.baidu.com/api/trans/vip/translate',{
								params:{
									q:text,
									from:'auto',
									to:lang,
									appid:'你的id',
									salt:'12345678',
									sign:signt
								}
		}).then(resp=>{
				this.tranresult=resp.data.trans_result[0].dst;
			},response => {
				console.log("发送失败"+response.status+","+response.statusText);
			});

	  
	}
  }
}
</script>

<style>
body{
	padding:0;
	margin:0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
.app-index img{
   width:50%;
}
.app-index{
	margin:20px 0 10px;
}
h5{
	margin:10px 0 20px;
}
.footer{
	position: fixed;
	width:100%;
	bottom:0;
	height:40px;
	line-height: 40px;
	background: #666;
	color:#e5e5e5;

}
</style>
