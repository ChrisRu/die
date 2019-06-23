<template>
  <die-face transform="rotateX(-90deg) translateZ(100px)">
    <die-dot :top="45" :left="45"></die-dot>
    <die-dot :top="125" :left="125"></die-dot>
  </die-face>
</template>

<script>
import Vue from 'vue'
import DieDot from '../DieDot.vue'
import DieFace from '../DieFaceWrapper.vue'

export default Vue.extend({
  name: 'die-face-two',
  components: {
    DieDot,
    DieFace,
  },
})
</script>
