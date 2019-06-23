<template>
  <span class="dot" :style="{ top: top + 'px', left: left + 'px' }"></span>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'die-dot',
  props: ['top', 'left'],
})
</script>

<style lang="sass" scoped>
.dot
  position: absolute
  width: 30px
  height: 30px
  background: #fff
  border-radius: 30px
</style>
