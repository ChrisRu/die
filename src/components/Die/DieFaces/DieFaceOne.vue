<template>
  <die-face transform="translateZ(100px)">
    <die-dot :top="85" :left="85"></die-dot>
  </die-face>
</template>

<script lang="ts">
import Vue from 'vue'
import DieDot from '../DieDot.vue'
import DieFace from '../DieFaceWrapper.vue'

export default Vue.extend({
  name: 'die-face-one',
  components: {
    DieDot,
    DieFace,
  },
})
</script>
