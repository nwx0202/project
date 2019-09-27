<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5>简单 / 易用 / 便捷</h5>
    <transForm v-on:formSubmit="TransText"></transForm>
    <transOutput v-text="translatedText"></transOutput>
  </div>
</template>

<script>
import TransForm from './components/transForm' 
import TransOutput from './components/transOutput'

export default {
  name: 'App',
  data: function() {
    return {
      translatedText: ''
    }
  },
  components: {
    TransForm,
    TransOutput
  },
  methods: {
    TransText: function (text, language) {
      // console.log(text);
      this.$http.get(`https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190927T144327Z.9306c631531e2293.5272139a5975be97b3b4921cd8b9c5f25c2d0852
      &lang=${language}&text=${text}`).then((response) => {
        this.translatedText = response.body.text[0];
      });
    }
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
