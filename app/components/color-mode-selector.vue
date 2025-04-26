<template>
  <div class="flex space-x-2 items-center">
    <div class="text-gray-800 dark:text-gray-200 text-xs" v-if="showLabel">
      Change to {{ nextMode }}
    </div>
    <button class="px-2 py-1" @click="toggleMode" @mouseenter="showLabel = true" @mouseleave="showLabel = false">
      {{ nextModeIcon }}
    </button>
  </div>
</template>

<script setup>
const showLabel = ref(false)
const colorMode = useColorMode()

const modes = [
  'system',
  'light',
  'dark'
]

const nextModeIcons = {
  system: '🌓',
  light: '🌕',
  dark: '🌑'
}

const nextMode = computed(() => {
  const currentModeIndex = modes.indexOf(colorMode.preference)
  let nextModeIndex = null

  if (currentModeIndex + 1 === modes.length) {
    nextModeIndex = 0
  } else {
    nextModeIndex = currentModeIndex + 1
  }

  return modes[nextModeIndex]
})

const nextModeIcon = computed(() => nextModeIcons[nextMode.value])

const toggleMode = () => colorMode.preference = nextMode.value
</script>
