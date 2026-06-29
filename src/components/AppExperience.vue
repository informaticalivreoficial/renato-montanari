<script setup>
const { resume } = defineProps({
  resume: {
    type: Object,
    required: true
  }
})
</script>

<template>
<section id="experience" class="py-32">

  <div class="mx-auto max-w-7xl px-6">

    <p class="text-sky-400 uppercase tracking-[0.25em] mb-4">
      Experiência
    </p>

    <h2 class="text-4xl font-black mb-16">
      Minha trajetória
    </h2>

    <div class="relative border-l border-slate-800 pl-8 space-y-12">

      <div
        v-for="item in resume.experience"
        :key="item.year"
        class="relative"
      >

        <!-- bolinha da timeline -->
        <span class="absolute -left-[41px] top-2 h-4 w-4 rounded-full bg-sky-500"></span>

        <p class="text-sky-400 font-semibold">
          {{ item.year }}
        </p>

        <h3 class="text-xl font-bold mt-1">
          {{ item.role }}
        </h3>

        <p class="text-slate-400">
          {{ item.company }}
        </p>

        <p class="mt-3 text-slate-300 leading-7">
          {{ item.description }}
        </p>

        <div class="mt-4 flex flex-wrap gap-2">
          <span
            v-for="tech in item.stack"
            :key="tech"
            class="rounded-full border border-slate-700 px-3 py-1 text-xs text-slate-300"
          >
            {{ tech }}
          </span>
        </div>

      </div>

    </div>

  </div>

</section>
</template>