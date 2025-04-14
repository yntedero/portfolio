<template>
  <div class="container mx-auto max-w-xl p-2">
    <header class="flex justify-between items-center">
      <div>
        <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200">Yurii Ostapchuk</NuxtLink>
      </div>
      <Menu />
    </header>

    <main class="p-2">
      <slot />
    </main>
  </div>
</template>

<script lang="ts" setup>

useHead({
  titleTemplate: '%s - Yurii Ostapchuk',
  link: [
    {
      rel: 'preconnect',
      href: 'https://fonts.googleapis.com'
    },
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap',
      crossorigin: ''
    }
  ]
})
</script>

<style>
body {
  font-family: 'Roboto', sans-serif;
}
</style>
