<template>
  <div id="transForm">
      <form v-on:submit="formSubmit">
          <input type="text" id="" placeholder="请输入要翻译的内容" v-model="textToTrans">
          <select id="" v-model="language">
              <option value="en">English</option>
              <option value="ru">Russian</option>
              <option value="ko">Korean</option>
              <option value="ja">Janpenese</option>
          </select>
          <input type="submit" value="翻译">
      </form>
  </div>
</template>

<script>

export default {
  name: 'transForm',
  data: function () {
      return {
          textToTrans: '',
          language: 'en'
      }
  },
  methods: {
      formSubmit: function (e) {
          e.preventDefault();
          // 向父组件传递数据
          this.$emit('formSubmit', this.textToTrans, this.language);
      }
  }
}
</script>

<style>
</style>
