<template>
  <div
    class="cube"
    v-on:click="$emit('click')"
    :style="{
      'transition-duration': spinTime + 's',
      transform: `rotateX(${xRand * 90}deg) rotateY(${yRand * 90}deg)`,
    }"
  >
    <die-face-one></die-face-one>
    <die-face-two></die-face-two>
    <die-face-three></die-face-three>
    <die-face-four></die-face-four>
    <die-face-five></die-face-five>
    <die-face-six></die-face-six>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import DieFaceOne from './DieFaces/DieFaceOne.vue'
import DieFaceTwo from './DieFaces/DieFaceTwo.vue'
import DieFaceThree from './DieFaces/DieFaceThree.vue'
import DieFaceFour from './DieFaces/DieFaceFour.vue'
import DieFaceFive from './DieFaces/DieFaceFive.vue'
import DieFaceSix from './DieFaces/DieFaceSix.vue'

export default Vue.extend({
  name: 'die-wrapper',
  components: {
    DieFaceOne,
    DieFaceTwo,
    DieFaceThree,
    DieFaceFour,
    DieFaceFive,
    DieFaceSix,
  },
  props: ['spinTime', 'xRand', 'yRand'],
})
</script>

<style lang="sass" scoped>
.cube
  width: 100%
  height: 100%
  position: absolute
  cursor: pointer
  transform-style: preserve-3d
  transition-property: transform
</style>
