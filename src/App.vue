<template>
  <div id="app">
    <dice
      className="dice"
      :spinTime="4"
      :spins="1"
      v-on:rolling="rolling"
      v-on:roll="rolled"
    ></dice>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Dice from './components/Dice/Dice.vue'

export default Vue.extend({
  name: 'app',
  components: {
    Dice,
  },
  methods: {
    rolling() {
      console.log('rolling...')
    },
    rolled(diceValue: number) {
      console.log(diceValue)
    },
  },
})
</script>

<style lang="sass">
body
  background: #000

#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
  margin-top: 60px
  background: #181818
  margin: 100px auto
  padding: 80px 0
  border-radius: 20px
  width: 400px

.dice
  transform: scale(0.7)
</style>
