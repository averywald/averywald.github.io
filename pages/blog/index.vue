<template>
  <main>
    <!-- find all blog posts -->
    <ContentList path="/blog" v-slot="{ list }">
      <div v-for="article in list" :key="article._path">
        <h2>{{ article.title }}</h2>
        <p>{{ article.description }}</p>
      </div>
    </ContentList>
  </main>
</template>

<script>
  console.log('script');
</script>
