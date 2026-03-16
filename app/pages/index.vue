<script setup lang="ts">
// 引入会话管理
const { loggedIn } = useUserSession()

// 在组件挂载前直接判断并跳转
onBeforeMount(() => {
  if (loggedIn.value) {
    // 已登录，去控制台
    navigateTo('/dashboard')
  } else {
    // 未登录，去登录页
    navigateTo('/dashboard/login')
  }
})
</script>

<template>
  <div class="flex h-screen w-full items-center justify-center bg-background">
    <div class="flex flex-col items-center gap-2">
      <div class="h-8 w-8 animate-spin rounded-full border-4 border-primary border-t-transparent"></div>
      <p class="text-sm text-muted-foreground">正在跳转...</p>
    </div>
  </div>
</template>
