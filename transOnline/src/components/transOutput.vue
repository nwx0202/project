<template>
  <div id="transOutput">
      <h3>{{translatedText}}</h3>
  </div>
</template>

<script>
export default {
  name: 'transOutput',
  props: [
      'translatedText'
  ]
}
</script>

<style>
</style>
