<template>
  <div class="container">
    <div class="content">
      <div class="svg">
        <svg width="400" height="300" viewBox="0 0 531.826 329.555" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    	    <defs/>
    	    <path ref="line" class="path" d="M2.24014 116.845C-6.0932 59.8449 12.2401 -39.7551 152.24 17.8449C292.24 75.4449 363.907 249.178 382.24 328.845C483.907 282.178 635.24 181.645 427.24 152.845C219.24 124.045 75.2401 258.178 29.2401 328.845" stroke="#000000"/>
        </svg>
      </div>
    </div>
    <div class="background"></div>
  </div>
</template>

<script lang="ts" setup>
  import { onMounted, ref, nextTick } from "vue";
  const line = ref();
  onMounted(async () => {
    const path = line.value;
    const len = path.getTotalLength();
    await nextTick();
    path.style.setProperty("--l", len + 1)
  })
</script>

<style lang="less" scoped>
.container {
  width: 100vw;
  height: 100vh;
  position: relative;

  .content {
    position: inherit;
    display: flex;
    justify-content: center;
    z-index: 2;

    .svg {
      margin-top: 20vh;
      .path {
        stroke: #f4dbc9;
        stroke-width: 7;
        stroke-dasharray: 1500;
        stroke-dashoffset: 1500;
        stroke-linecap: round;
        animation: stroke 3s forwards;
      }
      @keyframes stroke {
        60% {
          stroke-dashoffset: 860;
        }
        100% {
          stroke-dashoffset: 0;
        }
      }
    }
  }
  
  .background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url(../assets/background.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    opacity: 0.8;
    z-index: 1;
  }
}
</style>>