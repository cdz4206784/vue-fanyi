<template>
  <div class="row" id="translateForm">
    <div class="col-md-6 offset-4">
      <form class="form form-inline" v-on:submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="输入需要翻译的内容">
        <select class="form-control" v-model="language">
          <option value="en">English</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="ja">Japanese</option>
        </select>
        <input type="submit" class="btn btn-primary" value="翻译">
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate: '',
      language:''
    }
  },
  methods: {
    formSubmit(e){
      e.preventDefault();
      this.$emit("formSubmit",this.textToTranslate,this.language);
      // alert(this.textToTranslate)
    }
  },
  created(){
    this.language = "en"
  }
}
</script>

<style>
  #translateForm {
    padding: 10px;
    border-radius: 5px;
    box-sizing: border-box;
  }
</style>
