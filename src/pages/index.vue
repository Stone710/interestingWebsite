<template>
  <div>
    <svg width="670" height="400" viewBox="0 0 531.826 329.555" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
  	  <defs/>
  	  <path ref="line" class="svg" id="矢量 1" d="M2.24014 116.845C-6.0932 59.8449 12.2401 -39.7551 152.24 17.8449C292.24 75.4449 363.907 249.178 382.24 328.845C483.907 282.178 635.24 181.645 427.24 152.845C219.24 124.045 75.2401 258.178 29.2401 328.845" stroke="#000000"/>
    </svg>
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
  .svg{
    stroke: #111111;
    stroke-width: 7;
    stroke-dasharray: val(--l);
    stroke-dashoffset: val(--l);
    stroke-linecap: round;
    animation: stroke 10s forwards;
  }
  @keyframes stroke {
    to {
      stroke-dashoffset: 0;
    }
  }
</style>>