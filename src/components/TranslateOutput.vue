<template>
  <div id="translateOutput">
      {{translatedText}}
  </div>
</template>

<script>

export default {
  name: 'translateOutput',
  props: [
    "translatedText"
  ]
}
</script>

<style>
  #translateOutput {
    background: #eee;
  }
</style>
