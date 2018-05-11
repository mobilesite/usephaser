<template>
  <div class="svganimation">
    <svg width="106" height="106" viewport="0 0 100 100" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink">
      <circle stroke-dasharray="1 6" cx="53" cy="53" r="50" stroke="rgba(0,0,0,.2)" stroke-width="6" fill="none"></circle>
      <polygon stroke-dasharray="6" points="53,6 6,106 106,106" stroke="rgba(0,0,0,.2)" stroke-width="1" fill="none"></polygon>
      <line stroke-dasharray="6" x1="53" y1="53" x2="53" y2="100" stroke="rgba(0,0,0,.3)" stroke-width="1"></line>
    </svg>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>

<style lang="less">
  .svganimation{
    line{
      animation: line-anim 10s linear infinite;
      stroke-dashoffset: 100px;
    }
    circle{
      transform-origin: 50% 50%;
      animation: circle-anim 20s linear infinite;
    }
    polygon{
      animation: line-anim 2s linear infinite;
      stroke-dashoffset: 100px;
    }
  }
  @keyframes line-anim{
    0% {
      stroke-dashoffset: 0;
    }
    100% {
      stroke-dashoffset: -100px;
    }
  }
  @keyframes circle-anim{
    0% {
      transform: rotate(0);
    }
    100% {
      transform: rotate(360deg);
    }
  }
</style>
