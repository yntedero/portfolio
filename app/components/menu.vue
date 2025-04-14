<template>
  <div>
    <nav class="font-mono">
      <ul class="flex space-x-4">
        <li>
          <NuxtLink to="/" class="link">Main</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/about" class="link">About</NuxtLink>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script lang="ts" setup>
</script>

<style scoped>
.link {
  @apply p-1 hover:bg-gray-200 rounded;
}
</style>
