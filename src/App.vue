<template>
  <div id="app">
	<player
		v-bind:src="'menuettm.mp3'"></player>
  </div>
</template>

<script>
import PlayerComponent from './components/player.vue'

export default {
  name: 'app',
  components: {
	player: PlayerComponent
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
