<template>
  <div class="colorpicker">
    <div class="colorpicker__rainbow"></div>
  </div>
</template>

<script>
export default {
}
</script>

<style>
.colorpicker{
}
.colorpicker__rainbow{
  width: 20px;
  height: 150px;
  background-image: linear-gradient(
    -180deg,
    #f00 0%,
    #f0f 15%,
    #00f 33%,
    #0ff 49%,
    #0f0 67%,
    #ff0 84%,
    #f00 100%
  );
}
</style>
