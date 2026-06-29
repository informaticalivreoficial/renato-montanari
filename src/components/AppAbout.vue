<script setup>
const { resume } = defineProps({
  resume: {
    type: Object,
    required: true
  }
})
</script>

<template>
<section
    id="about"
    class="py-32"
>

<div
    class="mx-auto grid max-w-7xl gap-20 lg:grid-cols-2"
>

<div>

<p
    class="mb-4 text-sky-400 uppercase tracking-[0.25em]"
>
Sobre
</p>

<h2
    class="text-4xl font-black"
>
{{ resume.about.title }}
</h2>

<p
    class="mt-8 leading-8 text-slate-300"
>
{{ resume.about.description }}
</p>

<div
    class="mt-10 flex flex-wrap gap-3"
>

<span
v-for="item in resume.highlights"
:key="item"
class="rounded-full border border-slate-700 px-4 py-2 hover:border-sky-500 transition"
>

{{ item }}

</span>

</div>

</div>

<div
class="grid gap-6"
>

<div
v-for="stat in resume.stats"
:key="stat.label"
class="rounded-2xl border border-slate-800 bg-slate-900/50 p-8"
>

<h3
class="text-5xl font-black text-sky-400"
>

{{ stat.value }}

</h3>

<p
class="mt-2 text-slate-300"
>

{{ stat.label }}

</p>

</div>

</div>

</div>

</section>
</template>