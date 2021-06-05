<template>
  <div>
    <div v-if="!$fetchState.pending">
      <ArticleCards-Featured :article="resources[0]" />
      <div class="grid grid-cols-4 gap-10 my-10 ">
        <template v-for="article in resources.slice(1)">
          <ArticleCards-Card-1 :key="article.id" :article="article" />
        </template>
      </div>
    </div>
    <div v-else>
      <!-- Skeleton start -->
      <Skeletons-Featured />
      <div class="grid grid-cols-4 gap-10 my-10 ">
        <template v-for="i in new Array(8)">
          <Skeletons-Card-1 :key="i" />
        </template>
      </div>
      <!-- Skeleton end -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      resources: []
    };
  },
  async fetch() {
    const resources = await this.$axios.$get(
      "posts?categories=268&per_page=9&_embed"
    );
    this.resources = resources;
  }
};
</script>
