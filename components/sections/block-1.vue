<template>
  <div>
    <SectionTitle :title="title" />
    <div class="grid grid-cols-2 gap-10">
      <template v-if="!$fetchState.pending">
        <ArticleCards-Card-1
          v-for="article in resources"
          :key="article.id"
          :article="article"
        />
      </template>
      <template v-else>
        <Skeletons-Card-1 v-for="i in new Array(limit)" :key="i" />
      </template>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "category_id", "limit"],
  data() {
    return {
      resources: []
    };
  },
  async fetch() {
    const resources = await this.$axios.$get(
      `posts?categories=${this.category_id}&per_page=${this.limit}&_embed`
    );
    this.resources = resources;
  }
};
</script>
