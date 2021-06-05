<template>
  <div>
    <SectionTitle :title="title" />
    <div v-if="!$fetchState.pending">
      <div>
        <ArticleCards-Card-1 :article="firstArticle" />
        <div class="flex flex-col mt-6 space-y-4 ">
          <ArticleCards-Card-2
            v-for="article in othersArticle"
            :key="article.id"
            :article="article"
          />
        </div>
      </div>
    </div>
    <div v-else>
      <Skeletons-Card-1 />
      <div class="flex flex-col mt-6 space-y-4 ">
        <Skeletons-Card-2 v-for="i in new Array(limit)" :key="i" />
      </div>
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
  computed: {
    firstArticle() {
      return this.resources[0];
    },
    othersArticle() {
      return this.resources.slice(1);
    }
  },
  async fetch() {
    const resources = await this.$axios.$get(
      `posts?categories=${this.category_id}&per_page=${this.limit}&_embed`
    );
    this.resources = resources;
  }
};
</script>
