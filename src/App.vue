<template>
  <!-- Don't drop "q-app" class -->
  <div id="q-app">
    <grounding></grounding>
  </div>
</template>

<script>
import Grounding from 'components/Grounding'
export default {
  name: 'app',
  components: {
    Grounding
  }
}
</script>

<style>
  body, #q-app {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    display: flex;
    flex-flow: column;
    margin: 0;
  }
</style>
