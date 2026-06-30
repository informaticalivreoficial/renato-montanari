<script setup>
import profileImage from '/perfil.jpeg'

const { resume } = defineProps({
  resume: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <section class="flex min-h-screen items-center">
    <div
      class="mx-auto grid w-full max-w-7xl items-center gap-16 px-6 py-24 lg:grid-cols-2"
    >
      <div class="order-2 text-center lg:order-1 lg:text-left">

        <span
          class="inline-flex rounded-full border border-sky-500/30 bg-sky-500/10 px-4 py-2 text-sm font-medium text-sky-400"
        >
          {{ resume.profile.title }}
        </span>

        <h1
          class="mt-8 text-5xl font-black leading-tight md:text-6xl xl:text-7xl"
        >
          {{ resume.profile.name }}
        </h1>

        <p
          class="mt-8 max-w-xl text-lg leading-8 text-slate-300 lg:max-w-2xl"
        >
          {{ resume.profile.summary }}
        </p>

        <!-- Skills -->
        <div class="mt-10 flex flex-wrap justify-center gap-3 lg:justify-start">
          <span
            v-for="skill in resume.skills"
            :key="skill"
            class="rounded-full border border-slate-700 bg-slate-900/50 px-4 py-2 text-sm transition-all duration-300 hover:border-sky-500 hover:bg-slate-800"
          >
            {{ skill.category }}
          </span>
        </div>

        <!-- Botões -->
        <div
          class="mt-12 flex flex-col justify-center gap-4 sm:flex-row lg:justify-start"
        >
          <a
            :href="'mailto:' + resume.profile.email"
            class="rounded-xl bg-sky-500 px-8 py-4 text-center font-semibold text-white transition hover:bg-sky-600"
          >
            Fale comigo
          </a>

          <a
            :href="resume.social.github"
            target="_blank"
            rel="noopener noreferrer"
            class="rounded-xl border border-slate-700 px-8 py-4 text-center transition hover:border-sky-500 hover:bg-slate-900"
          >
            GitHub
          </a>

          <a
            v-if="resume.social.linkedin"
            :href="resume.social.linkedin"
            target="_blank"
            rel="noopener noreferrer"
            class="rounded-xl border border-slate-700 px-8 py-4 text-center transition hover:border-sky-500 hover:bg-slate-900"
          >
            LinkedIn
          </a>
        </div>

      </div>

      <!-- Foto -->
      <div class="order-1 flex justify-center lg:order-2">

        <div class="relative">

          <!-- Luz azul -->
          <div
            class="absolute -left-10 -top-10 h-40 w-40 rounded-full bg-sky-500/20 blur-3xl"
          ></div>

          <div
            class="absolute -bottom-10 -right-10 h-40 w-40 rounded-full bg-cyan-400/20 blur-3xl"
          ></div>

          <!-- Foto -->
          <div
            class="relative overflow-hidden rounded-full border border-slate-700 bg-slate-900 p-2 shadow-2xl"
          >
            <img
              :src="profileImage"
              :alt="resume.profile.name"
              class="h-72 w-72 rounded-full object-cover md:h-96 md:w-96"
            />
          </div>

        </div>

      </div>

    </div>
  </section>
</template>