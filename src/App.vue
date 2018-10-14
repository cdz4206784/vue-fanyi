<template>
  <div id="app" class="container">
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单 / 易用 / 便捷</h5>
    <translateForm v-on:formSubmit="translateText"></translateForm>
    <translateOutput v-text="translatedText"></translateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'App',
  data(){
    return {
      translatedText: ""
    }
  },
  methods: {
    translateText(text,language){
      this.$http.get("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181014T114739Z.5917a74efd5cfcfc.fd4c9576f6391223384b77e8463b2c72bb24853f&lang="+ language +"&text=" + text).then(res=>{
        // console.log(res.body.text[0])
        this.translatedText = res.body.text[0]
      })
    }
  },
  components: {
    TranslateForm,TranslateOutput
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
