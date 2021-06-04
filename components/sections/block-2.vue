<template>
  <div>
    <SectionTitle :title="title" />
    <div>
      <div>
        <ArticleCards-Card-1 :article="firstArticle" />
        <div class=" flex flex-col space-y-4 mt-6">
          <ArticleCards-Card-2
            v-for="article in othersArticle"
            :key="article.id"
            :article="article"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["resources", "title"],
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
