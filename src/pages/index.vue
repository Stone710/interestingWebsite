<template>
  <div class="container">
    <div class="content">
      <div class="pic_svg">
        <svg class="svg" viewBox="0 0 531.826 329.555" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    	    <defs/>
    	    <path ref="line" class="path" d="M2.24014 116.845C-6.0932 59.8449 12.2401 -39.7551 152.24 17.8449C292.24 75.4449 363.907 249.178 382.24 328.845C483.907 282.178 635.24 181.645 427.24 152.845C219.24 124.045 75.2401 258.178 29.2401 328.845" stroke="#000000"/>
        </svg>
        <!-- <vue-typed-js :strings="['123','123123123']">
          <h1 class="typing"></h1>
        </vue-typed-js> -->
      </div>
      <div class="button">
        <a href="#">Button</a>
      </div>
    </div>
    <div class="background"></div>
  </div>
</template>

<script lang="ts" setup>
  import { onMounted, ref } from "vue";
  const line = ref();
  onMounted(() => {
    const path = line.value;
    const len = path.getTotalLength();
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
    z-index: 2;
    position: absolute;
    top: 30vh;
    width: 100%;

    .pic_svg {
      text-align: center;
      .svg {
        width: 600px;
        height: 400px;
        animation: identifier 3s forwards;
        @keyframes identifier {
          66% {
            width: 600px;
            height: 400px;
          }
          100% {
            widows: 200px;
            height: 150px;
          }
        }
        .path {
          stroke: #f4dbc9;
          stroke-width: 7;
          stroke-dasharray: 1500;
          stroke-dashoffset: 1500;
          stroke-linecap: round;
          animation: stroke 2s forwards;
        }
        @keyframes stroke {
          55% {
            stroke-dashoffset: 860;
          }
          100% {
            stroke-dashoffset: 0;
          }
        }
      }
    }

    .button {
      margin-top: 20px;
      text-align: center;
      a {
        position: relative;
        display: inline-block;
        width: 200px;
        height: 60px;
        color: #fff;
        line-height: 60px;
        text-align: center;
        text-decoration: none;
        background: linear-gradient(90deg,
          #03a9f4,
          #f441a5,
          #ffeb3b,
          #03a9f4,
        );
        background-size: 400%;
        border-radius: 10px;
      }

      @keyframes button {
        0% {
          background-position: 0 0;
        }
        100% {
          background-position: 400% 0;
        }
      }

      a:hover {
        animation: button 8s liner infinite;
      }

      a:before {
        content: '';
        position: absolute;
        left: -5px;
        top: -5px;
        right: -5px;
        bottom: -5px;
        z-index: -1;
        background: linear-gradient(90deg,
          #03a9f4,
          #f441a5,
          #ffeb3b,
          #03a9f4,
        );
        background-size: 400%;
        border-radius: 10px;
        opacity: 0;
        transition: all 1s;
      }

      a:hover:before {
        filter: blur(20px);
        opacity: 1;
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