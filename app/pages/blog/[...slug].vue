<template>
  <article>
    <ContentDoc />
  </article>
</template>

<script lang="ts" setup>
// inside Proxy/Target/params we access to id of the page
const route = useRoute();
console.log(route.params.slug);
</script>

<style></style>
