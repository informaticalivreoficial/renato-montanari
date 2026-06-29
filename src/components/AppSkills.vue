<script setup>
const { resume } = defineProps({
  resume: {
    type: Object,
    required: true
  }
})
</script>

<template>
<section id="skills" class="py-32">

  <div class="mx-auto max-w-7xl px-6">

    <p class="text-sky-400 uppercase tracking-[0.25em] mb-4">
      Skills
    </p>

    <h2 class="text-4xl font-black mb-16">
      Tecnologias que utilizo
    </h2>

    <div class="grid gap-12 lg:grid-cols-3">

      <div
        v-for="group in resume.skills"
        :key="group.category"
      >

        <h3 class="text-xl font-bold mb-6">
          {{ group.category }}
        </h3>

        <div class="space-y-6">

          <div
            v-for="skill in group.items"
            :key="skill.name"
          >

            <div class="flex justify-between text-sm mb-2">
              <span class="text-slate-300">
                {{ skill.name }}
              </span>

              <span class="text-slate-500">
                {{ skill.level }}%
              </span>
            </div>

            <!-- barra -->
            <div class="h-2 w-full rounded-full bg-slate-800 overflow-hidden">
              <div
                class="h-full bg-sky-500 transition-all duration-500"
                :style="{ width: skill.level + '%' }"
              />
            </div>

          </div>

        </div>

      </div>

    </div>

  </div>

</section>
</template>