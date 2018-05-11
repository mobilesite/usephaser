<template>
  <div class="tooltip" :aria-label="text">
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="less">
.tooltip{
  @bg: rgba(0, 0, 0, .7); //背景
  @arrow-width: 5px; //箭头宽度
  @padding-top-bottom: 2px; 
  @padding-left-right: 4px;
  @radius: 2px; //圆角
  @font-size: 14px; //文字大小

  position: relative;

  &:before{
    content: attr(aria-label);
    background: @bg;
    color: #fff;
    padding: @padding-top-bottom @padding-left-right;
    box-sizing: border-box;
    border-radius: @radius;
    font-size: @font-size;
  }

  &:after{
    position: absolute;
    top: 100%;
    left: 50%;
    margin-left: -@arrow-width;
    margin-top: 1px;
    border: @arrow-width solid transparent;
    border-top-color: @bg;
    content: '';
  }
}
</style>
