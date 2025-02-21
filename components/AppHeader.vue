<template>
  <div class="header-wrap w-6 w-full p-4">
    <header
      class="bg-zinc-950 text-stone-200 p-4 flex justify-between items-center w-full"
    >
      <div class="flex items-center">
        <img src="assets/images/logo.png" alt="Logo" class="h-10 mr-4" />
        <NuxtLink to="/" class="text-2xl font-bold logo-text">Radheya</NuxtLink>
      </div>
      <nav class="flex space-x-6">
        <NuxtLink
          to="/"
          class="header-link"
          :class="{ '': $route.path === '/' }"
          >Home</NuxtLink
        >
        <NuxtLink
          to="/about"
          class="header-link"
          :class="{ '': $route.path === '/about' }"
          >About</NuxtLink
        >
        <NuxtLink
          to="/bookings"
          class="header-link"
          :class="{
            '': $route.path === '/bookings',
          }"
          >Bookings</NuxtLink
        >
        <NuxtLink
          to="/community"
          class="header-link"
          :class="{
            '': $route.path === '/community',
          }"
          >Community</NuxtLink
        >
        <NuxtLink
          to="/merch"
          class="header-link"
          :class="{ '': $route.path === '/merch' }"
          >Merch</NuxtLink
        >
        <NuxtLink
          to="/music"
          class="header-link"
          :class="{ '': $route.path === '/music' }"
          >Music</NuxtLink
        >
      </nav>
    </header>
  </div>
</template>

<script lang="ts" setup>
// No additional script needed for this simple header
</script>

<style scoped>
.header-wrap {
  background-color: #131517;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10; /* Adjust as needed */
}

.header-link {
  @apply uppercase text-lg px-6 font-bold;
  transition: all 0.3s ease-in-out;
}

.logo-text {
  color: #dd9f2c;
}

.header-link:hover {
  color: #dd9f2c;
}
</style>
