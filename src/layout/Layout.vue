<script setup>
import Header from "./Header.vue";
import Footer from "./Footer.vue";

defineProps({
  overlay: {
    type: Boolean,
    default: false,
  },
  containerClass: {
    type: String,
    default: "",
  },
  mainClass: {
    type: String,
    default: "",
  },
});
</script>

<template>
  <div
    :class="
      containerClass ||
      (overlay
        ? 'min-h-screen w-full text-slate-900'
        : 'mx-auto min-h-screen max-w-5xl bg-white px-4 py-8 text-slate-900')
    "
  >
    <Header :overlay="overlay" />

    <main :class="mainClass">
      <slot />
    </main>

    <Footer />
  </div>
</template>
