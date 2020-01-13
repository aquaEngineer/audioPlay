<template>
	<div id="player">
		<audio preload = "auto" controls="" v-bind:src="src"></audio>
		<div id="play"
			@click="play()">再生
		</div>
	</div>
</template>

<script>
export default {
  name: 'player',
  props: {
	src: String
  },
  data: function () {
	return {audio: new Audio()
	}
		},
  methods: {
		play: function () {
			this.audio.src = this.src;
			this.audio.load();
			this.audio.addEventListener('canplay', () => {
				this.audio.play();
			})
		}
	}
}
</script>

<style scoped>
</style>
