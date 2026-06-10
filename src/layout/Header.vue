<script setup>
import { onBeforeUnmount, onMounted, ref } from "vue";

const props = defineProps({
  overlay: {
    type: Boolean,
    default: false,
  },
  contrastTargetId: {
    type: String,
    default: "",
  },
});

const isDarkText = ref(false);
let observer = null;

onMounted(() => {
  if (!props.overlay || !props.contrastTargetId) {
    return;
  }

  const target = document.getElementById(props.contrastTargetId);
  if (!target) {
    return;
  }

  observer = new IntersectionObserver(
    ([entry]) => {
      isDarkText.value = !entry?.isIntersecting;
    },
    {
      threshold: 0,
    },
  );

  observer.observe(target);
});

onBeforeUnmount(() => {
  observer?.disconnect();
});
</script>

<template>
  <header
    :class="
      props.overlay
        ? [
            'fixed left-0 top-0 z-30 flex w-full items-center justify-end p-2 text-sm transition-colors duration-300',
            isDarkText ? 'text-slate-900' : 'text-slate-100',
          ]
        : 'mb-8 pb-4'
    "
  >
    <div class="p-2 text-2xl font-montserrat font-semibold">
      Omalo Fiber Guild
    </div>
    <!-- <nav class="flex items-center gap-2">
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
    </nav> -->
  </header>
</template>
