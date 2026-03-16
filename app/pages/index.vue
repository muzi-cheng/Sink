<script setup lang="ts">
onMounted(async () => {
  const token =
    localStorage.getItem('site_token') ||
    localStorage.getItem('sink_token') ||
    localStorage.getItem('token')

  await navigateTo(token ? '/dashboard/links' : '/dashboard/login', {
    replace: true,
  })
})
</script>

<template>
  <div />
</template>
