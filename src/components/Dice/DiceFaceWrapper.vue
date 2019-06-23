<template>
  <div class="dice-face" :style="{ transform }">
    <slot></slot>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'dice-face-wrapper',
  props: ['transform'],
})
</script>

<style lang="sass" scoped>
.dice-face
  background: hsla(200, 125%, 30%, .95)
  position: absolute
  width: 200px
  height: 100px
  padding: 50px 0
</style>
