<template>
  <dice-face transform="translateZ(100px)">
    <dice-dot :top="85" :left="85"></dice-dot>
  </dice-face>
</template>

<script>
import Vue from 'vue'
import DiceDot from '../DiceDot.vue'
import DiceFace from '../DiceFaceWrapper.vue'

export default Vue.extend({
  name: 'dice-face-one',
  components: {
    DiceDot,
    DiceFace,
  },
})
</script>
