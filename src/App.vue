<template>
  <div id="app">
    <die
      className="die"
      :spinTime="4"
      :spins="1"
      v-on:rolling="rolling"
      v-on:roll="rolled"
    ></die>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Die from './components/Die/Die.vue'

export default Vue.extend({
  name: 'app',
  components: {
    Die,
  },
  methods: {
    rolling() {
      console.log('rolling...')
    },
    rolled(dieValue: number) {
      console.log(dieValue)
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

.die
  transform: scale(0.7)
</style>
