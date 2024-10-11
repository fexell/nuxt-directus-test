<script setup>
  const { $directus, $readItems } = useNuxtApp()

  const { data } = await useAsyncData('index', () => {
    return $directus.request($readItems('index'))
  })

  console.log(data)
</script>

<template>
  <NuxtLink to='/'>Home</NuxtLink>
  <NuxtLink to='/about'>About</NuxtLink>
</template>