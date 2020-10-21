<template>
  <div class="bg-gray-100 font-family-karla flex">
    <aside
      class="relative bg-sidebar bg-blue-700 h-screen w-64 hidden sm:block shadow-xl"
    >
      <div class="p-6">
        <a
          href="index.html"
          class="text-white text-3xl font-semibold uppercase hover:text-gray-300"
          >KAPS</a
        >
      </div>
      <nav class="text-white text-base font-semibold pt-3">
        <SidebarLink
          v-for="sidebarItem in menu"
          :url="sidebarItem.url"
          :name="sidebarItem.name"
          :key="sidebarItem.name"
          :icon="sidebarItem.icon"
        />
      </nav>
    </aside>

    <div class="relative w-full flex flex-col h-screen overflow-y-hidden">
      <div class="w-full h-screen overflow-x-hidden border-t flex flex-col">
        <main class="w-full flex-grow p-6">
          <nuxt />
          <!-- Content goes here! 😁 -->
        </main>
      </div>
    </div>
  </div>
</template>


<script>
import SidebarLink from '@/components/SidebarLink'

const menu = [
  {
    url: '#',
    name: 'Dashboard',
    icon: 'fas fa-tachometer',
  },
  { url: '#', name: 'Users' },
  { url: '#', name: 'Leave' },
  { url: '#', name: 'Vehicles' },
]

export default {
  components: {
    SidebarLink,
  },
  data() {
    return {
      menu,
    }
  },
}
</script>