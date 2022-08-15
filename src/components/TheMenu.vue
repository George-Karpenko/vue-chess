<template>
  <Menu as="div" class="grid grid-rows-5 grid-cols-6 h-screen">
    <MenuItems
      :static="true"
      class="col-start-1 col-end-7 sm:col-start-2 sm:col-end-6 lg:col-start-3 lg:col-span-2 row-start-2 my-auto rounded-md border-solid border-2 border-gray-500 focus:outline-none"
    >
      <div class="py-1">
        <MenuItem v-for="item in navigation" :key="item" v-slot="{ active }">
          <RouterLink
            :to="{ name: item }"
            :class="[
              active ? 'bg-gray-100 text-gray-900' : 'text-gray-700',
              'block px-4 py-2 text-sm',
            ]"
            >{{ item }}</RouterLink
          >
        </MenuItem>
      </div>
    </MenuItems>
  </Menu>
</template>

<script setup lang="ts">
import { RouterLink } from "vue-router";
import { Menu, MenuItem, MenuItems } from "@headlessui/vue";
const navigation = ["settings", "game"];
</script>
