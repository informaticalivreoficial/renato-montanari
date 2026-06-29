<template>
  <section id="contact" class="py-32">

    <div class="mx-auto max-w-4xl px-6 text-center">

      <!-- Título -->
      <h2 class="text-4xl font-black">
        {{ resume.contact.title }}
      </h2>

      <!-- descrição -->
      <p class="mt-6 text-lg text-slate-300">
        {{ resume.contact.description }}
      </p>

      <!-- botões -->
      <div class="mt-10 flex flex-col justify-center gap-4 sm:flex-row">

        <a
          :href="resume.profile.email ? 'mailto:' + resume.profile.email : resume.contact.email"
          class="rounded-xl bg-sky-500 px-8 py-4 font-semibold text-white transition hover:bg-sky-600"
        >
          Enviar Email
        </a>

        <a
          :href="resume.social.github"
          target="_blank"
          class="rounded-xl border border-slate-700 px-8 py-4 transition hover:border-sky-500 hover:bg-slate-900"
        >
          GitHub
        </a>

        <a
          v-if="resume.social.linkedin"
          :href="resume.social.linkedin"
          target="_blank"
          class="rounded-xl border border-slate-700 px-8 py-4 transition hover:border-sky-500 hover:bg-slate-900"
        >
          LinkedIn
        </a>

      </div>

    </div>

  </section>
</template>

<script setup>
const { resume } = defineProps({
  resume: {
    type: Object,
    required: true
  }
})
</script>