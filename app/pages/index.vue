<script setup lang="ts">
// 获取用户的登录状态
const { loggedIn } = useUserSession()

// 页面元数据配置：在渲染前进行逻辑跳转
definePageMeta({
  middleware: [
    function () {
      const { loggedIn } = useUserSession()
      
      if (loggedIn.value) {
        // 如果已登录，跳转到仪表盘（后台统计页）
        return navigateTo('/dashboard')
      } else {
        // 如果未登录，跳转到登录页
        return navigateTo('/dashboard/login')
      }
    }
  ]
})
</script>

<template>
  <div class="flex h-screen items-center justify-center">
    <div class="animate-spin rounded-full h-8 w-8 border-b-2 border-primary"></div>
  </div>
</template>
