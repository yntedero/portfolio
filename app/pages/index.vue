<template>
  <div>
    Hello world there is main page!
  </div>
</template>

<script lang="ts" setup>
useSeoMeta({
  title: 'Main Page',
  description: 'This is the main page app',
  ogTitle: 'Main Page',
  ogDescription: 'This is the main page app',
  ogImage: '[og:image]',
  ogUrl: '[og:url]',
  twitterTitle: 'Main Page',
  twitterDescription: 'This is the main page app',
  twitterImage: '[twitter:image]',
  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'en'
  },
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: '/favicon.png'
    }
  ]
})
</script>

<style>

</style>

