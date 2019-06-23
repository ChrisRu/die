<template>
  <div :class="['dice-container', className]">
    <dice-wrapper
      v-on:click="rollCube"
      :spinTime="spinTime"
      :xRand="xRand"
      :yRand="yRand"
    ></dice-wrapper>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import DiceWrapper from './DiceWrapper.vue'

function sleep(ms: number) {
  return new Promise(resolve => setTimeout(resolve, ms))
}

export default Vue.extend({
  name: 'dice',
  components: {
    DiceWrapper,
  },
  props: {
    spinTime: {
      default: 4,
      type: Number,
    },
    spins: {
      default: 2,
      type: Number,
    },
    className: String,
  },
  data() {
    return {
      xRand: 0,
      yRand: 0,
    }
  },
  methods: {
    async rollCube() {
      const diceRoll = this.getRandomDiceThrow()

      // Make it spinnn
      this.xRand = Math.floor(Math.random() * 6 * this.spins) * 4
      this.yRand = Math.floor(Math.random() * 6 * this.spins) * 4

      // Make it orientate
      switch (diceRoll) {
        case 2:
          this.xRand++
          break
        case 3:
          this.yRand--
          break
        case 4:
          this.yRand++
          break
        case 5:
          this.xRand--
          break
        case 6:
          this.xRand -= 2
          break
      }

      this.$emit('rolling')

      await sleep(this.spinTime * 1000)

      this.$emit('roll', diceRoll)
    },

    getRandomDiceThrow() {
      return Math.floor(Math.random() * (6 - 1 + 1) + 1)
    },
  },
})
</script>

<style lang="sass" scoped>
.dice-container
  width: 200px
  height: 200px
  position: relative
  margin: 0 auto
  perspective: 1000px
  perspective-origin: 50% 100%
</style>
