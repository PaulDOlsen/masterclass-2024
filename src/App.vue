<script setup lang="ts">
import Input from '@/components/ui/input/Input.vue'
</script>

<template>
  <nav class="h-16 border-b bg-muted/40" flex justify-between px-6 items-center>
    <form class="w-full max-w-96">
      <Input class="w-full pl-8 bg-background" type="text" placeholder="Search ..." />
    </form>
    <div class="w-8 h-8 rounded-full bg-white"></div>
  </nav>
  <main>
    <RouterView />
  </main>
</template>
