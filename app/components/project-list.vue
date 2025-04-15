<template>
  <div>
    Projects
  </div>
  <p class="mb-10">This is my Github projects!</p>
  <section v-if="pending">
    <p>Loading...</p>
  </section>
  <section v-else-if="error">
    <p>Error: {{ error.message }}</p>
  </section>
  <section v-else>
    <ul class="grid grid-cols-1 gap-4">
      <li v-for="repository in data" :key="repository.id"
        class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono">
        <a :href="repository.html_url" target="_blank">
          <div class="font-semibold">
            {{ repository.name }}
          </div>
        </a>
      </li>
    </ul>
  </section>
</template>

<script lang="ts" setup>
const { data, pending, error } = await useFetch('https://api.github.com/users/yntedero/repos');
</script>

<style></style>
