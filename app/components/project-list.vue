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
      <li v-for="repository in repos" :key="repository.id"
        class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono">
        <a :href="repository.html_url" target="_blank">
          <div class="flex items-center justify-between">
            <div class="font-semibold">
              {{ repository.name }}
            </div>
            <div class="text-sm">
              {{ repository.stargazers_count }} ★
            </div>
          </div>
          <p class="text-sm">
            {{ repository.description }}
          </p>
        </a>
      </li>
    </ul>
  </section>
</template>

<script lang="ts" setup>
const { data, pending, error } = await useFetch(
  'https://api.github.com/users/yntedero/repos'
);
const repos = computed(
  () => data.value.filter(repo => repo.description).sort((a, b) => b.stargazers_count - a.stargazers_count)
)
</script>

<style></style>
