<template>
  <header>
    <nav
      class="flex justify-between bg-slate-700 shadow-lg items-center text-white py-4 px-3 md:px-24">
      <div><h2 class="text-3xl">Task Manager</h2></div>
      <ul class="flex items-center gap-5 text-xl font-semibold flex-wrap">
        <li><RouterLink to="/">Home</RouterLink></li>
        <li><RouterLink to="/about">About</RouterLink></li>
      </ul>
    </nav>
  </header>
</template>

<script setup></script>
