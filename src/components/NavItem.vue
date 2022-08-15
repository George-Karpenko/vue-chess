<script setup lang="ts">
import { RouterLink, useRoute } from "vue-router";
import { computed } from "vue";

const props = defineProps<{
  item: string;
}>();
console.log(useRoute());

const current = computed(() => {
  if (useRoute().name === props.item) {
    return true;
  }
  return false;
});
</script>

<template>
  <router-link
    :to="{ name: item }"
    :class="[
      current
        ? 'bg-gray-900 text-white'
        : 'text-gray-300 hover:bg-gray-700 hover:text-white',
    ]"
    :aria-current="current ? 'page' : undefined"
    >{{ item }}</router-link
  >
</template>
