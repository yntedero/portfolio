<template>
  <article>
    <ContentRenderer v-if="page" :value="page" />
  </article>
</template>

<script lang="ts" setup>
// inside Proxy/Target/params we access to id of the page
import {useAsyncData} from "#app";

const route = useRoute();
const { data: page } = await useAsyncData(route.path, () => {
  return queryCollection('blog').path(route.path).first()
})
console.log(route.params.slug);
</script>

<style></style>
