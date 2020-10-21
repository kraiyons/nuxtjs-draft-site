<template>
  <nuxt-link
    v-bind:to="url"
    class="flex items-center text-white py-4 pl-6 nav-item hover:border-gray-300"
  >
    <i class="icon" />
    {{ name }}
  </nuxt-link>
</template>

<script>
export default {
  name: 'sidebar-link',
  props: {
    url: String,
    name: String,
    icon: String,
  },
}
</script>