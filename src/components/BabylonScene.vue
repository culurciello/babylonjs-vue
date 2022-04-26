<template>
  <canvas ref="renderCanvas" id="renderCanvas"/>
</template>

<script>
import { ref, onMounted } from "@vue/runtime-core";
import { createScene } from "../scenes/MyFirstScene";

export default {
  name: "BabylonScene",
  setup() {
    const renderCanvas = ref(null);

    onMounted(() => {
      if (renderCanvas.value) {
        createScene(renderCanvas.value);
      }
    });

    return {
      renderCanvas,
    };
  },
};
</script>

<style>
#renderCanvas {
    width: 100%;
    height: 70%;
    position: relative;
    touch-action: none;
    z-index: 1;
}
</style>