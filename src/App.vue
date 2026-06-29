<template>
  <main class="min-h-screen bg-slate-950 text-white">

    <div
      class="fixed inset-0 -z-10 bg-[radial-gradient(circle_at_top,#2563eb22,transparent_45%)]"
    ></div>

    <AppNavbar />

    <div class="mx-auto max-w-7xl px-6">
      <AppHero :resume="resume" />

      <AppAbout :resume="resume" />

      <AppExperience :resume="resume" />

      <AppProjects :resume="resume" />

      <AppContact :resume="resume" />

      <Footer />
    </div>    

  </main>
</template>

<script setup>
  import resume from './data/resume.json'

  import AppNavbar from './components/AppNavbar.vue'
  import AppHero from './components/AppHero.vue'
  import AppAbout from './components/AppAbout.vue'
  import AppExperience from './components/AppExperience.vue'
  import AppProjects from './components/AppProjects.vue'
  import AppContact from './components/AppContact.vue'
  import Footer from './components/AppFooter.vue'
</script>