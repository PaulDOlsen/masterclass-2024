<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">
import { supabase } from '@/lib/supabaseClient'
import { ref } from 'vue'
import type { Tables } from '../../../database/types'

const projects = ref<Tables<'projects'>[] | null>(null)
;(async () => {
  const { data, error } = await supabase.from('projects').select()
  if (error) console.log(error)

  projects.value = data
  console.log('projects: ', projects.value)
  return data
})()
</script>

<template>
  <div>
    <h1>Project Page</h1>
    <RouterLink to="/">Go to home</RouterLink>
    <ul>
      <li v-for="project in projects" :key="project.id">{{ project.name }}</li>
    </ul>
  </div>
</template>

<style lang="scss" scoped></style>
