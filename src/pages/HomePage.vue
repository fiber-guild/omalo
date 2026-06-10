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
  <Layout
    :overlay="true"
    contrast-target-id="hero-contrast-sentinel"
    container-class="relative min-h-screen w-full"
  >
    <section id="hero-section" class="relative h-dvh w-full overflow-hidden">
      <img
        src="/poster.jpg"
        alt="Alchemic Valleys Exploration & Natural Dyeing poster"
        class="absolute inset-0 h-full w-full object-cover"
      />

      <div
        id="hero-contrast-sentinel"
        class="absolute bottom-0 h-px w-full"
        aria-hidden="true"
      />

      <div
        class="relative z-10 flex h-full flex-col justify-between bg-black/35 p-6 sm:p-10"
      >
        <h1
          class="mb-3 max-w-5xl pt-20 text-3xl leading-tight tracking-tight text-[#ededed] drop-shadow-[0_3px_14px_rgba(0,0,0,0.65)] sm:text-5xl"
        >
          <span class="uppercase font-bold">Alchemic Valleys</span>
          <br />Exploration & Natural Dyeing <br />in vestomta
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
      <div class="max-w-5xl text-slate800 space-y-6">
        <p class="text-4xl z-10 relative">
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
        <!-- <div class="mx-auto w-full max-w-2xl">
          <img src="../assets/vestomta.png" alt="Vestomta village" />
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1903.4630873660956!2d45.523127317144464!3d42.37880458215024!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x40459c53ce5b8b2b%3A0xf08bbbdc9cc27091!2sVestomta!5e1!3m2!1sen!2sge!4v1781110566868!5m2!1sen!2sge" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div> -->
        <div class="max-w-2xl mx-auto -mt-8">
          <img src="../assets/plants.jpg" alt="" srcset="" />
        </div>
        <p class="text-4xl -mt-10 relative z-10">
          <strong>The Practice:</strong> Processing and dyeing wool with madder
          root (Rubia tinctorum), indigo, turmeric, and mountain flowers.
        </p>
        <div class="max-w-2xl mx-auto -mt-8">
          <img class="w-full" src="../assets/hiking.webp" alt="" srcset="" />
        </div>
        <p class="text-4xl -mt-10">
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
        <!-- <p>
          The group will be small and intimate. To book your spot or ask
          questions, send us a DM.
        </p> -->
      </div>
    </section>
    <section
      id="image-section"
      class="mx-auto max-w-5xl px-4 py-20 text-slate-900 space-y-6"
    >
      <h2 class="mb-4 text-2xl font-semibold">About Us</h2>
      <!-- <p>
        Natia is a Tusheti native, professional mountain guide, and the creator
        of Nateii. Having grown up among these peaks, she leads our explorations
        through the Vestomta valley with an intimate knowledge of its hidden
        trails and history. She offers a truly unique perspective on the
        valley—combining the physical journey of the trek with the ancient
        knowledge of the land’s natural colors.
      </p> -->
      <div
        class="text-rxl text-4xl relative z-10 font-montserrat tracking-tight"
      >
        Our work in the Vestomta valley is a collaboration rooted in a shared
        passion for the Tushetian landscape and its ancient wool traditions. By
        combining mountain exploration, academic research, and contemporary
        design, we strive to document and preserve the living heritage of the
        high Caucasus.
      </div>
      <div class="mx-auto max-w-2xl -mt-8">
        <img src="../assets/we.png" alt="" />
      </div>
      <p>
        <strong>Natia </strong> [Natia Karkhilarui] is a Tusheti native,
        professional mountain guide, and the creator of
        <a
          class="underline text-gray-400 hover:text-gray-300 transition"
          href="https://www.instagram.com/nateii_in_tusheti"
          target="_blank"
          >Nateii</a
        >. Having grown up among these peaks, she leads our explorations through
        the Vestomta valley with an intimate knowledge of its hidden trails and
        history. She offers a truly unique perspective on the valley—combining
        the physical journey of the trek with the ancient knowledge of the
        land’s natural colors. Follow her journey:
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
          href="https://www.instagram.com/aqtushetii_residency"
          target="_blank"
          >AqTushetii residency</a
        >, where she works to bridge the gap between contemporary design and the
        preservation of ancient highland traditions.
      </p>

      <p>
        <strong>Tamara</strong> [Tamara kalkhitashvili] is a researcher,
        professor of Digital Humanities at Ilia State University, and an
        advanced practitioner of natural dyeing. For the past five years, she
        has worked alongside Anna as an assistant to master artisan Nanalo
        Azikuri, specializing in the complex chemistry and history of botanical
        colors. A PhD in Philology, Tamara’s academic work—including research
        for the State Silk Museum and the digital preservation of Georgian
        heritage—allows her to decode the cultural semantics and "language" of
        Tushetian textiles, bridging the gap between historical linguistics and
        living craft.
      </p>
      <p>
        The group will be small and intimate. To book your spot or ask
        questions, send us on
        <a
          class="underline text-gray-400 hover:text-gray-400 transition"
          href="https://www.instagram.com/omalo_fiber_guild/"
          target="_blank"
          >istagram</a
        >
        DM or mail omalofiberguild@gmail.com.
      </p>
    </section>
  </Layout>
</template>
