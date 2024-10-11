<script setup>
  const { $directus, $readItem } = useNuxtApp()
  const route = useRoute()

  const { data } = await useAsyncData(route.params.slug, () => {
    return $directus.request($readItem('pages', route.params.slug))
  })

  console.log(data)
</script>

<template>
  <NuxtLink to='/'>Home</NuxtLink>
  <NuxtLink to='/about'>About</NuxtLink>
</template>