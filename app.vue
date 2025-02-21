<template>
  <div>
    <AppHeader />
    <div class="page-wrap w-6 w-full p-4">
      <NuxtPage />
    </div>
    <AppFooter />
  </div>
</template>

<style>
html,
body {
  @apply bg-stone-900 text-stone-100;
  font-family: "Montserrat", sans-serif;
}

.page-wrap {
  background-color: #131517;
  min-height: 70vh;
  max-width: 100%;
  overflow-x: hidden;
  margin-top: 100px;
}

.page-enter-active,
.page-leave-active {
  transition: all 0.31s;
}
.page-enter-from,
.page-leave-to {
  opacity: 0;
  translate: 50px 0px;
}
</style>
