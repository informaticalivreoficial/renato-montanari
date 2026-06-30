<script setup>
const { resume } = defineProps({
  resume: {
    type: Object,
    required: true
  }
})
</script>

<template>
<section id="projects" class="py-32">

  <div class="mx-auto max-w-7xl px-6">

    <p class="text-sky-400 uppercase tracking-[0.25em] mb-4">
      Projetos
    </p>

    <h2 class="text-4xl font-black mb-16">
      O que já construí
    </h2>

    <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">

      <div
        v-for="project in resume.projects"
        :key="project.title"
        class="group overflow-hidden rounded-2xl border border-slate-800 bg-slate-900/30 transition hover:border-sky-500"
      >

        <!-- imagem -->
        <div class="h-48 overflow-hidden">
          <img
            :src="project.image"
            :alt="project.title"
            class="h-full w-full object-cover object-[center_15%] transition duration-500 group-hover:scale-105"
          />
        </div>

        <!-- conteúdo -->
        <div class="p-6">

          <h3 class="text-xl font-bold">
            {{ project.title }}
          </h3>

          <p class="mt-2 text-sm text-slate-400">
            {{ project.description }}
          </p>

          <!-- stack -->
          <div class="mt-4 flex flex-wrap gap-2">
            <span
              v-for="tech in project.stack"
              :key="tech"
              class="rounded-full border border-slate-700 px-3 py-1 text-xs text-slate-300"
            >
              {{ tech }}
            </span>
          </div>

          <!-- links -->
          <div class="mt-6 flex gap-4">

            <a
              v-if="project.github"
              :href="project.github"
              target="_blank"
              class="text-sm text-slate-300 hover:text-sky-400"
            >
              GitHub
            </a>

            <a
              v-if="project.demo"
              :href="project.demo"
              target="_blank"
              class="text-sm text-sky-400 hover:underline"
            >
              Demo
            </a>

          </div>

        </div>

      </div>

    </div>

  </div>

</section>
</template>