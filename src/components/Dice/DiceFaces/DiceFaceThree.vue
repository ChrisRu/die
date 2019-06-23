<template>
  <dice-face transform="rotateY(90deg) translateZ(100px)">
    <dice-dot :top="45" :left="45"></dice-dot>
    <dice-dot :top="85" :left="85"></dice-dot>
    <dice-dot :top="125" :left="125"></dice-dot>
  </dice-face>
</template>

<script>
import Vue from 'vue'
import DiceDot from '../DiceDot.vue'
import DiceFace from '../DiceFaceWrapper.vue'

export default Vue.extend({
  name: 'dice-face-three',
  components: {
    DiceDot,
    DiceFace,
  },
})
</script>
