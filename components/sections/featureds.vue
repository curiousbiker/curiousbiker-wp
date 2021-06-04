<template>
  <div class="">
    <ArticleCards-Featured :article="firstArticle" />
    <div class=" grid grid-cols-4 gap-10 my-10">
      <ArticleCards-Card-1
        v-for="article in othersArticle"
        :key="article.id"
        :article="article"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: ["resources"],
  computed: {
    firstArticle() {
      return this.resources[0];
    },
    othersArticle() {
      return this.resources.slice(1);
    }
  }
};
</script>
