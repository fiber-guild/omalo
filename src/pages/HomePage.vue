<script setup>
import Layout from "../layout/Layout.vue";

const scrollToDetails = () => {
  const target = document.getElementById("details");
  target?.scrollIntoView({ behavior: "smooth" });
};

const scrollToImage = () => {
  const target = document.getElementById("image-section");
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
      <div class="max-w-5xl text-slate-700 space-y-6">
        <p class="text-5xl">
          In Tusheti On the slopes of the Caucasus, in the remote village of
          Vestomta — a place tourists rarely find —
          <button
            type="button"
            class="inline-flex translate-y-1 items-center justify-center text-slate-700 transition hover:text-slate-600 cursor-pointer"
            @click="scrollToImage"
            aria-label="Scroll to image"
          >
            <span>three women</span>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="h-6 w-6"
              aria-hidden="true"
            >
              <path d="M12 5v14" />
              <path d="m19 12-7 7-7-7" />
            </svg></button
          >, including a local Tush guide, are waiting for you to explore wild,
          natural colors. Under the open sky, we will practice traditional
          methods of dyeing local wool.
        </p>
        <p>
          <strong>The Practice:</strong> Processing and dyeing wool with madder
          root (Rubia tinctorum), indigo, turmeric, and mountain flowers.
          Exploration: Daily hiking tours to neighboring villages.
        </p>
        <p><strong>Dates:</strong> August 6 – 12</p>
        <p>
          <strong>Transportation:</strong>Transport: Round-trip drive from
          Tbilisi to Tusheti.
        </p>
        <p>
          <strong>Stay:</strong> Accommodation in a traditional guesthouse in
          Vestomta.
        </p>

        <p>
          <strong>Price:</strong> €800 (includes transport, accommodation, and
          all workshop materials).
        </p>
        <p>
          The group will be small and intimate. To book your spot or ask
          questions, send us a DM.
        </p>
      </div>
    </section>
    <section
      id="image-section"
      class="mx-auto max-w-5xl px-4 py-20 text-slate-900"
    >
      <h2 class="mb-4 text-2xl font-semibold">Tree Woman</h2>
      <p>Natia Karkhilauri, Ani Gvelesiani, Tamara kalkhitashvili</p>
      <div class="mx-auto max-w-2xl">
        <img src="../assets/we.png" alt="" />
      </div>
    </section>
  </Layout>
</template>
