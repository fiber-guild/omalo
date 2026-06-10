<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="mt-8 border-t border-slate-200 p-4 text-sm text-slate-500">
    <div class="mx-auto flex flex-wrap items-center justify-between gap-3">
      <div class="flex flex-wrap items-center gap-2">
        <span class="font-montserrat font-semibold text-slate-700"
          >Omalo Fiber Guild</span
        >
        <span aria-hidden="true">•</span>
        <span>Copyright &copy; {{ currentYear }}</span>
      </div>

      <div class="flex items-center gap-4">
        <a
          href="https://www.instagram.com/omalo_fiber_guild/"
          target="_blank"
          rel="noreferrer"
          class="inline-flex items-center gap-2 text-slate-600 transition-opacity hover:opacity-60"
          aria-label="Instagram"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="1.8"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="h-4 w-4"
            aria-hidden="true"
          >
            <rect x="2" y="2" width="20" height="20" rx="5" ry="5" />
            <path d="M16 11.37a4 4 0 1 1-3.37-3.37 4 4 0 0 1 3.37 3.37z" />
            <line x1="17.5" y1="6.5" x2="17.5" y2="6.5" />
          </svg>
          <span>Instagram</span>
        </a>

        <a
          href="mailto:omalofiberguild@gmail.com"
          class="text-slate-600 transition hover:text-slate-900"
          aria-label="Email contact"
        >
          omalofiberguild@gmail.com
        </a>
      </div>
    </div>
  </footer>
</template>
