<template>
  <div class="home">
  </div>
</template>

<script>
import Phaser from 'phaser'

export default {
  data () {
    return {
      msg: ''
    }
  },
  created () {
    const config = {
      // eslint-disable-next-line
      type: Phaser.AUTO,
      width: window.innerWidth,
      height: 1720 / 3840 * window.innerWidth,
      physics: {
        default: 'arcade',
        arcade: {
          gravity: { y: 200 }
        }
      },
      scene: {
        preload: preload,
        create: create
      }
    }

    // eslint-disable-next-line
    const game = new Phaser.Game(config)

    function preload () {
      this.load.setBaseURL('http://localhost:8080')
      this.load.image('bg', 'static/bg.png')
      this.load.image('logo', 'static/logo.png')
      this.load.image('particle', 'static/particle.png')
    }

    function create () {
      this.add.image(0, 0, 'bg')

      const particles = this.add.particles('particle')
      const emitter = particles.createEmitter({
        speed: 150,
        scale: { start: 1, end: 0 },
        blendMode: 'ADD'
      })
      const logo = this.physics.add.image(400, 100, 'logo')

      logo.setVelocity(100, 200)
      logo.setBounce(1, 1)
      logo.setCollideWorldBounds(true)

      emitter.startFollow(logo)
    }
  }
}
</script>

<style lang="less">
  *{
    margin: 0;
    padding: 0;
  }
  .home {
    font-size: 12px
  }
</style>
