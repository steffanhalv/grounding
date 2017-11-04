<template>
  <div id="papir-grounding">
    <div class="papir-viewbox-top"></div>
    <div class="papir-viewbox-left"></div>
    <div class="papir-workspace">
      <div class="papir-workspace-top-left"></div>
      <div class="papir-workspace-top-right"></div>
      <div class="papir-workspace-bottom-left"></div>
      <div class="papir-workspace-bottom-right"></div>
    </div>
    <div class="papir-viewbox-right"></div>
    <div class="papir-viewbox-bottom"></div>
  </div>
</template>

<script>
  export default {
    name: 'grounding'
  }
</script>

<style>
  #papir-grounding {
    flex: 1 1 auto;
    background: #333;
  }
  .papir-workspace {
    position: absolute;
    width: calc(100% - 40px);
    height: calc(100% - 40px);
    top: 20px;
    left: 20px;
    background: #777;
  }
  .papir-viewbox-top {
    position: absolute;
    width: 100%;
    height: 20px;
    background: #444;
    border-bottom: 1px solid #555;
  }
  .papir-viewbox-left {
    position: absolute;
    top: 20px;
    width: 20px;
    height: calc(100% - 40px);
    background: #444;
    border-right: 1px solid #555;
  }
  .papir-viewbox-right {
    position: absolute;
    top: 20px;
    right: 0;
    width: 20px;
    height: calc(100% - 40px);
    background: #444;
    border-right: 1px solid #555;
  }
  .papir-viewbox-bottom {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 20px;
    background: #444;
    border-top: 1px solid #555;
  }
</style>