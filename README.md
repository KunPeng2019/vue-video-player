<<<<<<< HEAD
# vue-video
适用于Vue.js的HTML5视频播放器组件
=======
[![GitHub stars](https://img.shields.io/github/stars/surmon-china/vue-video-player.svg?style=flat-square)](https://github.com/surmon-china/vue-video-player/stargazers)
[![Build Status](https://travis-ci.org/surmon-china/vue-video-player.svg?branch=master)](https://travis-ci.org/surmon-china/vue-video-player)
[![GitHub issues](https://img.shields.io/github/issues/surmon-china/vue-video-player.svg?style=flat-square)](https://github.com/surmon-china/vue-video-player/issues)
[![GitHub forks](https://img.shields.io/github/forks/surmon-china/vue-video-player.svg?style=flat-square)](https://github.com/surmon-china/vue-video-player/network)
[![GitHub last commit](https://img.shields.io/github/last-commit/google/skia.svg?style=flat-square)](https://github.com/surmon-china/vue-video-player)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](https://github.com/surmon-china/vue-video-player)
[![Twitter](https://img.shields.io/twitter/url/https/github.com/surmon-china/vue-video-player.svg?style=flat-square)](https://twitter.com/intent/tweet?url=https://github.com/surmon-china/vue-video-player)

[![NPM](https://nodei.co/npm/vue-video-player.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/vue-video-player/)
[![NPM](https://nodei.co/npm-dl/vue-video-player.png?months=9&height=3)](https://nodei.co/npm/vue-video-player/)


# Vue-Video-Player

[video.js](https://github.com/videojs/video.js) player component for Vue.

适用于 Vue 的 [video.js](https://github.com/videojs/video.js) 播放器组件。


# Example

[Demo Page](https://surmon-china.github.io/vue-video-player)



### SPA

``` vue
<template>
  <video-player  class="video-player-box"
                 ref="videoPlayer"
                 :options="playerOptions"
                 :playsinline="true"
                 customEventName="customstatechangedeventname"

                 @play="onPlayerPlay($event)"
                 @pause="onPlayerPause($event)"
                 @ended="onPlayerEnded($event)"
                 @waiting="onPlayerWaiting($event)"
                 @playing="onPlayerPlaying($event)"
                 @loadeddata="onPlayerLoadeddata($event)"
                 @timeupdate="onPlayerTimeupdate($event)"
                 @canplay="onPlayerCanplay($event)"
                 @canplaythrough="onPlayerCanplaythrough($event)"

                 @statechanged="playerStateChanged($event)"
                 @ready="playerReadied">
  </video-player>
</template>

<script>
  // Similarly, you can also introduce the plugin resource pack you want to use within the component
  // import 'some-videojs-plugin'
  export default {
    data() {
      return {
        playerOptions: {
          // videojs options
          muted: true,
          language: 'en',
          playbackRates: [0.7, 1.0, 1.5, 2.0],
          sources: [{
            type: "video/mp4",
            src: "https://cdn.theguardian.tv/webM/2015/07/20/150716YesMen_synd_768k_vp8.webm"
          }],
          poster: "/static/images/author.jpg",
        }
      }
    },
    mounted() {
      console.log('this is current player instance object', this.player)
    },
    computed: {
      player() {
        return this.$refs.videoPlayer.player
      }
    },
    methods: {
      // listen event
      onPlayerPlay(player) {
        // console.log('player play!', player)
      },
      onPlayerPause(player) {
        // console.log('player pause!', player)
      },
      // ...player event

      // or listen state event
      playerStateChanged(playerCurrentState) {
        // console.log('player current update state', playerCurrentState)
      },

      // player is ready
      playerReadied(player) {
        console.log('the player is readied', player)
        // you can use it to do something...
        // player.[methods]
      }
    }
  }
</script>
```



# Issues

[videojs-contrib-hls - e is not defined](https://github.com/surmon-china/vue-video-player/issues/90)


# API
- component api:
  * `events` : `[ Array, default: [] ]` : custom videojs event to component
  * `playsinline` : `[ Boolean, default: false ]` : set player not full-screen in mobile device
  * `crossOrigin` : `[ String, default: '' ]` : set crossOrigin to video
  * `customEventName` : `[ String, default: 'statechanged' ]` : custom the state change event name

- video.js api
  * [video.js options](http://docs.videojs.com/tutorial-options.html)
  * [video.js docs](http://docs.videojs.com/)


# videojs plugins

- [videojs-resolution-switcher](https://github.com/kmoskwiak/videojs-resolution-switcher)
- [videojs-contrib-hls](https://github.com/videojs/videojs-contrib-hls)
- [videojs-youtube](https://github.com/videojs/videojs-youtube)
- [videojs-vimeo](https://github.com/videojs/videojs-vimeo)
- [videojs-hotkeys](https://github.com/ctd1500/videojs-hotkeys)
- [videojs-flash](https://github.com/videojs/videojs-flash)
- [videojs-contrib-ads](https://github.com/videojs/videojs-contrib-ads)
- [more plugins...](https://github.com/search?o=desc&q=videojs+plugin&s=stars&type=Repositories&utf8=%E2%9C%93)


# Author
[Surmon](https://surmon.me)
>>>>>>> first commit
