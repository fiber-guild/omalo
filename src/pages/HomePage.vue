<script setup>
import Layout from "../layout/Layout.vue";

const scrollToDetails = () => {
  const target = document.getElementById("details");
  target?.scrollIntoView({ behavior: "smooth" });
};
</script>

<template>
  <Layout :overlay="true" container-class="relative min-h-screen w-full">
    <section class="relative h-dvh w-full overflow-hidden">
      <img
        src="/poster.jpg"
        alt="Alchemic Valleys Exploration & Natural Dyeing poster"
        class="absolute inset-0 h-full w-full object-cover"
      />

      <div
        class="relative z-10 flex h-full flex-col justify-between bg-black/35 p-6 sm:p-10"
      >
        <h1
          class="mb-3 text-3xl font-bold tracking-tight text-white sm:text-5xl max-w-xl pt-20"
        >
          <span class="uppercase">Alchemic Valleys</span> Exploration & Natural
          Dyeing in vestomta
        </h1>
        <p class="text-white/90">
          omalo fiber guild in coloboration with
          <a
            href="https://www.instagram.com/omalo.fiber.guild/"
            class="underline"
            >Nateii</a
          >
        </p>
      </div>

      <button
        type="button"
        class="absolute bottom-8 left-1/2 z-20 -translate-x-1/2 text-center text-white"
        @click="scrollToDetails"
        aria-label="Scroll to details"
      >
        <span
          class="mb-2 block text-sm uppercase tracking-[0.2em] text-white/90 text-md"
        >
          6 - 12 August <br />Tusheti / Vestomta.
        </span>
        <span
          class="inline-flex h-12 w-12 items-center justify-center text-2xl leading-none transition hover:bg-black/50"
        >
          ↓
        </span>
      </button>
    </section>

    <section id="details" class="mx-auto max-w-5xl px-4 py-20 text-slate-900">
      <h2 class="mb-4 text-2xl font-semibold">Event Details</h2>
      <p class="max-w-2xl text-slate-700">
        Join us in Tusheti / Vestomta for a week of natural dyeing, textile
        practice, and mountain exploration. More program details can be added
        here.
      </p>
    </section>
  </Layout>
</template>
