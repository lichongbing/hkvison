<template>
  <div>
    <div ref="videoContainer"></div>
    <button @click="play">Play</button>
    <button @click="pause">Pause</button>
    <button @click="stop">Stop</button>
  </div>
</template>

<script>
export default {
  mounted () {
    this.initVideoPlayer()
  },
  methods: {
    initVideoPlayer () {
      const container = this.$refs.videoContainer
      // eslint-disable-next-line no-undef
      const player = new WebVideoCtrl.IVSPlayer(container)
      player.init({
        cameraIndexCode: 'camera1',
        url: 'http://example.com/video.mp4'
      })
      this.player = player
    },
    play () {
      if (this.player) {
        this.player.play()
      }
    },
    pause () {
      if (this.player) {
        this.player.pause()
      }
    },
    stop () {
      if (this.player) {
        this.player.stop()
      }
    }
  }
}
</script>
