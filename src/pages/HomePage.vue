<script setup>
import { ref } from "vue";
import Layout from "../layout/Layout.vue";

const baseUrl = import.meta.env.BASE_URL;
const heroPosterSrc = `${baseUrl}images/poster-1280.webp`;
const heroPosterSrcSet = `${baseUrl}images/poster-768.webp 768w, ${baseUrl}images/poster-1280.webp 1280w, ${baseUrl}images/poster-1920.webp 1920w`;
const heroLoaded = ref(false);

// Section image paths
const plantsSrc = `${baseUrl}images/sections/plants-800.webp`;
const plantsSrcSet = `${baseUrl}images/sections/plants-480.webp 480w, ${baseUrl}images/sections/plants-800.webp 800w, ${baseUrl}images/sections/plants-1200.webp 1200w`;

const hikingSrc = `${baseUrl}images/sections/hiking-800.webp`;
const hikingSrcSet = `${baseUrl}images/sections/hiking-480.webp 480w, ${baseUrl}images/sections/hiking-800.webp 800w, ${baseUrl}images/sections/hiking-1200.webp 1200w`;

const weSrc = `${baseUrl}images/sections/we-800.webp`;
const weSrcSet = `${baseUrl}images/sections/we-480.webp 480w, ${baseUrl}images/sections/we-800.webp 800w, ${baseUrl}images/sections/we-1200.webp 1200w`;

const onHeroLoad = () => {
  heroLoaded.value = true;
};

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
  <Layout
    :overlay="true"
    contrast-target-id="hero-contrast-sentinel"
    container-class="relative min-h-screen w-full"
  >
    <section
      id="hero-section"
      class="relative h-dvh w-full overflow-hidden bg-slate-900"
    >
      <img
        :src="heroPosterSrc"
        :srcset="heroPosterSrcSet"
        sizes="100vw"
        alt="Alchemic Valleys Exploration & Natural Dyeing poster"
        loading="eager"
        fetchpriority="high"
        decoding="async"
        @load="onHeroLoad"
        :class="[
          'absolute inset-0 h-full w-full object-cover transition-opacity duration-700 ease-out',
          heroLoaded ? 'opacity-100' : 'opacity-0',
        ]"
      />

      <div
        id="hero-contrast-sentinel"
        class="absolute bottom-0 h-px w-full"
        aria-hidden="true"
      />

      <div
        :class="[
          'relative z-10 flex h-full flex-col justify-between bg-black/35 p-6 transition-opacity duration-700 ease-out sm:p-10',
          heroLoaded ? 'opacity-100' : 'opacity-0',
        ]"
      >
        <h1
          class="mb-3 max-w-5xl pt-20 text-3xl leading-tight tracking-tight text-[#ededed] drop-shadow-[0_3px_14px_rgba(0,0,0,0.65)] sm:text-5xl"
        >
          <span class="uppercase font-bold">Alchemic Valleys</span><br />
          <span class="text-2xl sm:text-5xl">Exploration & Natural Dyeing</span>
          <br /><span class="text-2xl sm:text-5xl">in Vestomta</span>
        </h1>
        <p class="text-white/90 hidden xl:block">
          omalo fiber guild in coloboration with
          <a
            href="https://www.instagram.com/nateii_in_tusheti"
            target="_blank"
            rel="noopener noreferrer"
            class="underline hover:text-gray-300 transition"
            >Nateii</a
          >
        </p>
      </div>

      <button
        type="button"
        :class="[
          'absolute bottom-2 left-1/2 z-20 -translate-x-1/2 text-center text-white transition-opacity duration-700 ease-out',
          heroLoaded ? 'opacity-100' : 'opacity-0',
        ]"
        @click="scrollToDetails"
        aria-label="Scroll to details"
      >
        <span
          class="block text-sm uppercase tracking-[0.2em] text-white/90 text-md"
        >
          <span class="text-nowrap">6 - 12 August</span> <br /><span
            class="text-nowrap"
            >Tusheti / Vestomta.</span
          >
        </span>
        <span
          class="inline-flex h-12 w-12 items-center justify-center text-2xl leading-none transition cursor-pointer text-white/90"
        >
          ↓
        </span>
      </button>
    </section>

    <section
      id="details"
      class="mx-auto max-w-5xl px-4 pt-10 sm:pt-20 text-slate-900"
    >
      <h2 class="mb-0 sm:mb-4 text-xl sm:text-2xl font-semibold">
        Event Details
      </h2>
      <div class="max-w-5xl text-slate-800 space-y-6">
        <p class="text-2xl sm:text-4xl z-10 relative tracking-tight">
          On the slopes of the Caucasus, in the remote village of Vestomta, a
          place tourists rarely find,
          <button
            type="button"
            class="inline-flex items-center justify-center text-slate-700 transition hover:text-slate-600 cursor-pointer"
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
              class="w-4 h-4 sm:h-6 sm:w-6"
              aria-hidden="true"
            >
              <path d="M12 5v14" />
              <path d="m19 12-7 7-7-7" />
            </svg></button
          >, including a local Tush guide, are waiting for you to explore wild,
          natural colors. Under the open sky, we will practice traditional
          methods of dyeing local wool.
        </p>
        <!-- <div class="mx-auto w-full max-w-2xl">
          <img src="../assets/vestomta.png" alt="Vestomta village" />
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1903.4630873660956!2d45.523127317144464!3d42.37880458215024!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x40459c53ce5b8b2b%3A0xf08bbbdc9cc27091!2sVestomta!5e1!3m2!1sen!2sge!4v1781110566868!5m2!1sen!2sge" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div> -->
        <div class="max-w-2xl mx-auto -mt-6 sm:-mt-8">
          <img
            :src="plantsSrc"
            :srcset="plantsSrcSet"
            sizes="(max-width: 768px) 100vw, (max-width: 1280px) 80vw, 672px"
            alt="Natural dye plants used during the workshop"
            loading="lazy"
            decoding="async"
          />
        </div>
        <p
          class="relative z-10 -mt-6 sm:-mt-10 font-montserrat tracking-tight text-2xl sm:text-4xl"
        >
          <strong>The Practice:</strong> Processing and dyeing wool with madder
          root (Rubia tinctorum), indigo, turmeric, and mountain flowers.
        </p>
        <div class="max-w-2xl mx-auto -mt-6 sm:-mt-8">
          <img
            class="w-full"
            :src="hikingSrc"
            :srcset="hikingSrcSet"
            sizes="(max-width: 768px) 100vw, (max-width: 1280px) 80vw, 672px"
            alt="Hiking trail in Tusheti"
            loading="lazy"
            decoding="async"
          />
        </div>
        <p
          class="-mt-6 sm:-mt-10 font-montserrat tracking-tight text-2xl sm:text-4xl"
        >
          <strong>Exploration:</strong> Daily hiking tours to neighboring
          villages.
        </p>
      </div>
      <div class="mt-6">
        <!-- <div class="mx-auto max-w-2xl grid grid-cols-5 gap-4">
          <img src="../assets/madder.png" alt="Vestomta village" />
          <img src="../assets/indigo.png" alt="Vestomta village" />
          <img src="../assets/tumeric.png" alt="Vestomta village" />
          <img src="../assets/krazana.png" alt="Vestomta village" />
          <img src="../assets/tavshava.png" alt="Vestomta village" />
        </div> -->

        <p><strong>Dates:</strong> August 6 – 12</p>
        <p>
          <strong>Location:</strong> Vestomta, Tusheti, Georgia. view on
          <a
            class="underline text-gray-400 hover:text-gray-300 transition"
            href="https://www.google.com/maps/place/Vestomta/@42.3790661,45.5209172,874m/data=!3m2!1e3!4b1!4m6!3m5!1s0x40459c53ce5b8b2b:0xf08bbbdc9cc27091!8m2!3d42.3791109!4d45.5235294!16s%2Fg%2F1tkml0jw?entry=ttu&g_ep=EgoyMDI2MDYwMy4xIKXMDSoASAFQAw%3D%3D"
            target="_blank"
            >google maps</a
          >
        </p>
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
      </div>
    </section>
    <section
      id="image-section"
      class="mx-auto max-w-5xl px-4 px-4 pt-10 sm:pt-20 text-slate-900 space-y-6"
    >
      <h2 class="mb-0 sm:mb-4 text-xl sm:text-2xl font-semibold">About Us</h2>
      <div
        class="font-montserrat tracking-tight text-2xl sm:text-4xl z-10 relative tracking-tight"
      >
        Our work in the Vestomta valley grew out of a shared love for this
        landscape and its wool traditions. Each of us brings something
        different: mountain guiding, design, academic research. Together we try
        to document the old craft knowledge of the high Caucasus and revive the
        life cycle of Tusheti wool.
      </div>
      <div class="mx-auto max-w-2xl -mt-8">
        <img
          :src="weSrc"
          :srcset="weSrcSet"
          sizes="(max-width: 768px) 100vw, (max-width: 1280px) 80vw, 672px"
          alt="Omalo Fiber Guild collaborators"
          loading="lazy"
          decoding="async"
        />
      </div>
      <p>
        <strong>Natia </strong> [Natia Karkhilarui] grew up in Tusheti and works
        as a professional mountain guide. She is the creator of
        <a
          class="underline text-gray-400 hover:text-gray-300 transition"
          href="https://www.nateii.net/"
          target="_blank"
          >Nateii</a
        >. She has known the valley's trails and stories since childhood, and on
        our walks the trek and the land's natural colors become part of the same
        lesson. Follow her at:
        <a
          class="underline text-gray-400 hover:text-gray-400 transition"
          href="https://www.instagram.com/nateii_in_tusheti"
          target="_blank"
          >@nateii_in_tusheti</a
        >
      </p>
      <p>
        <strong>Ani</strong> [Ani Gvelesiani] is a professional designer and web
        developer who has spent the last five years deeply immersed in the wool
        heritage of the Caucasus. Working as an assistant to the local master
        artisan Nanalo Azikuri, Ani has mastered the full cycle of Tushetian
        craft—from raw wool and thread processing to natural dyeing, traditional
        rug weaving, and the intricate knitting of mountain socks. Based in
        Omalo, her work is closely integrated with the
        <a
          class="underline text-gray-400 hover:text-gray-400 transition"
          href="https://aqtushetii.com/"
          target="_blank"
          >AqTushetii residency</a
        >, where she works to bridge the gap between contemporary design and the
        preservation of ancient highland traditions.
      </p>

      <p>
        <strong>Tamara</strong> [Tamara kalkhitashvili] is a researcher and
        professor of Digital Humanities at Ilia State University, and a longtime
        practitioner of natural dyeing. For the past five years she has worked
        alongside Ani as an assistant to Nanalo Azikuri, drawn especially to the
        chemistry and history of botanical colors. She holds a PhD in Philology,
        and her academic work, from research for the State Silk Museum to the
        digital preservation of Georgian heritage, lets her read Tushetian
        textiles as a language of their own.
      </p>
      <p class="py-10">
        The group will be small and intimate. To book your spot or ask
        questions, send us on
        <a
          class="underline text-gray-400 hover:text-gray-400 transition"
          href="https://www.instagram.com/omalo_fiber_guild/"
          target="_blank"
          >instagram</a
        >
        DM or write an email to
        <a
          href="mailto:omalofiberguild@gmail.com"
          class="underline text-gray-400 hover:text-gray-400 transition"
          >omalofiberguild@gmail.com</a
        >.
      </p>
    </section>
  </Layout>
</template>
