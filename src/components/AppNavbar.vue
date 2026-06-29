<template>
  <header class="fixed top-0 left-0 right-0 z-50 border-b border-slate-800 bg-slate-950/80 backdrop-blur">
    <div class="mx-auto flex h-16 max-w-7xl items-center justify-between px-6">
      <!-- Logo / Avatar -->
      <a href="#" class="flex items-center gap-3">

        <img
          :src="profileImage"
          alt="Profile"
          class="h-9 w-9 rounded-full object-cover border border-slate-700"
        />

        <span class="text-sm font-semibold text-white tracking-wide">
          Renato
        </span>

      </a>

      <nav class="hidden gap-8 md:flex">
        <a href="#about" class="text-slate-300 hover:text-sky-400 transition">
          Sobre
        </a>

        <a href="#skills" class="text-slate-300 hover:text-sky-400 transition">
          Skills
        </a>

        <a href="#projects" class="text-slate-300 hover:text-sky-400 transition">
          Projetos
        </a>

        <a href="#contact" class="text-slate-300 hover:text-sky-400 transition">
          Contato
        </a>
      </nav>
    </div>
  </header>
</template>

<script setup>
import profileImage from '@/assets/images/perfil.jpg'
</script>