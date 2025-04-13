<template>
  <div>
    we are inside a blog
  </div>
  <div>
    Post id is P{{ route.params.id }}
  </div>
</template>

<script lang="ts" setup>
// inside Proxy/Target/params we access to id of the page
const route = useRoute();
</script>

<style></style>
