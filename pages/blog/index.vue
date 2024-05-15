<template>
  <main>
    <h1>Posts</h1>
    <!-- find all blog posts -->
    <ContentList :query="query" v-slot="{ list }">
      <div class="card" v-for="article in list" :key="article._path">
        <NuxtLink :to="article._path">
          <h2>{{ article.title }}</h2>
        </NuxtLink>
        <p>{{ article.description }}</p>
        <i> {{ formatDateHeader(article.date) }}</i>
      </div>
    </ContentList>
  </main>
</template>

<script setup lang="ts">
  import type { QueryBuilderParams } from '@nuxt/content/dist/runtime/types'
  // sort by title and date
  const query: QueryBuilderParams = { path: '/blog', sort: [{ title: 1, date: 1 }] }
  // where: [{ layout: 'article' }], limit: 5,

  // yyyy-mm-dd date string formatter
  function formatDateHeader(dateString: string): string {
    let str = 'N/A';

    if (dateString) {
      str = new Date(dateString).toISOString().split('T')[0];
    }

    return str;
  } 
</script>

<style>
  @import url('~/assets/css/globals.scss');
</style>