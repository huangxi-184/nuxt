<template>
  <div>
    <h1>欢迎来到NUXT的第一个页面</h1>
    <NuxtLink to="/list">进入列表页</NuxtLink>

    <strong> 姓名：{{ userInfo.userName }} 性别：{{ userInfo.sex }} </strong>

    <h1>pos: {{ x }}, {{ y }}</h1>

    <a-button @click="handleMessage"> button </a-button>
  </div>
</template>

<script lang="ts" setup>
import { message } from "ant-design-vue"
import { useMyUserStore } from "@/stores/UserStore"

const userInfo = useMyUserStore().userInfo

const { x, y } = useMouse()

const handleMessage = () => {
  message.info("This is a normal message")
}
</script>

<style scoped lang="scss">
body {
  background-color: $bgColor;
  color: $theme;
}
</style>
