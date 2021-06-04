<template>
  <div>
    <SectionTitle :title="title" />
    <div class=" grid grid-cols-2 gap-10">
      <ArticleCards-Card-1
        v-for="article in resources"
        :key="article.id"
        :article="article"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: ["resources", "title"]
};
</script>
