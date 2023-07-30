<template>
  <div @click="toLogin">登录</div>
</template>
<script lang="ts" setup>
import { useRouter } from 'vue-router'

const router = useRouter()
function toLogin(){
  router.push({
      name: 'index'
  })
}
</script>

