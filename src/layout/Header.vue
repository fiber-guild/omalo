<script setup>
defineProps({
  overlay: {
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <header
    :class="
      overlay
        ? 'fixed left-0 top-0 p-4 z-30 p-2  flex items-center justify-between text-sm text-slate-100 w-full'
        : 'mb-8 pb-4'
    "
  >
    <div class="text-2xl">Omalo Fiber Guild</div>
    <nav class="flex items-center gap-2">
      <RouterLink
        to="/"
        class="rounded-md px-3 py-2 text-sm font-semibold text-slate-700 transition hover:bg-slate-100"
        active-class="bg-sky-100 text-sky-700"
      >
        Home
      </RouterLink>
      <RouterLink
        to="/about"
        class="rounded-md px-3 py-2 text-sm font-semibold text-slate-700 transition hover:bg-slate-100"
        active-class="bg-sky-100 text-sky-700"
      >
        About
      </RouterLink>
    </nav>
  </header>
</template>
