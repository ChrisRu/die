<template>
  <div
    class="cube"
    v-on:click="$emit('click')"
    :style="{
      'transition-duration': spinTime + 's',
      transform: `rotateX(${xRand * 90}deg) rotateY(${yRand * 90}deg)`,
    }"
  >
    <dice-face-one></dice-face-one>
    <dice-face-two></dice-face-two>
    <dice-face-three></dice-face-three>
    <dice-face-four></dice-face-four>
    <dice-face-five></dice-face-five>
    <dice-face-six></dice-face-six>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import DiceFaceOne from './DiceFaces/DiceFaceOne.vue'
import DiceFaceTwo from './DiceFaces/DiceFaceTwo.vue'
import DiceFaceThree from './DiceFaces/DiceFaceThree.vue'
import DiceFaceFour from './DiceFaces/DiceFaceFour.vue'
import DiceFaceFive from './DiceFaces/DiceFaceFive.vue'
import DiceFaceSix from './DiceFaces/DiceFaceSix.vue'

export default Vue.extend({
  name: 'dice',
  components: {
    DiceFaceOne,
    DiceFaceTwo,
    DiceFaceThree,
    DiceFaceFour,
    DiceFaceFive,
    DiceFaceSix,
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
