<template>
  <div class="row " id="translateForm">
    <div class="neirong">
      	<form class="well form-inline" v-on:submit="formSubmit">
      		<input class="form-control" v-model="textToTranslate" type="text" placeholder="输入翻译的内容">
      		<select class="form-control" v-model="language">
      			<option value="en">English</option>
            <option value="ru">Russian</option>
            <option value="ko">Korean</option>
            <option value="ja">Janpenese</option>         
      		</select>
      		<input class="btn btn-primary" type="submit" value="翻译">
      	</form>
      </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data:function(){
    return{
      textToTranslate:"",
      language:""
    }
  },
  methods:{
  	formSubmit:function(e){
  		//alert(this.textToTranslate);
      console.log(this.language)
      this.$emit("formSubmit",this.textToTranslate,this.language);
      e.preventDefault();
  	}
  },
  created:function(){
    this.language="en";
  }
}
</script>

<style>
.textcenter{ text-align: center; }
.neirong{ display: block; margin:0 auto; }
</style>
