<template>
	<div id="player">
		<div id="play" v-if="isPlay == false"
			@click="play()">再生
		</div>
		<div id="stop" v-else
			@click="stop()">停止
		</div>
		<div id="status">
			{{currentTime}}/{{duration}}
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
		return {
			audio: new Audio(),
			isPlay: false,
			duration: 0,
			currentTime: 0
		}
	},
	mounted: function () {
		this.audio.src = this.src;
		this.audio.load();
		this.audio.addEventListener('canplay', () => {
			this.duration = this.audio.duration;
		});
		this.audio.addEventListener('timeupdate', () => {
			this.currentTime = this.audio.currentTime;
		});
	},
	methods: {
		play: function () {
			this.audio.play();
			this.isPlay = true;
		},
		stop: function () {
			this.audio.pause();
			this.isPlay = false;
		}
	}
}
</script>

<style scoped>
</style>
