<template>
  <div class="grid grid-cols-12 gap-10 wrapper">
    <div class="col-span-8">
      <template v-if="!$fetchState.pending">
        <div>
          <h1 class="mb-10 text-3xl font-bold leading-relaxed">
            {{ article.title.rendered }}
          </h1>
          <img
            class="rounded-md"
            :src="thumbnail"
            :alt="article.title.rendered"
          />
        </div>
        <div
          v-html="article.content.rendered"
          class="mt-10 prose md:prose-xl"
        />
      </template>

      <template v-else>
        <div class="mb-4">
          <PuSkeleton height="15px" />
        </div>
        <PuSkeleton height="300px" />

        <div class="mt-4 ">
          <PuSkeleton :count="30" />
        </div>
      </template>
    </div>
    <div class="col-span-4 ">
      <div>
        <SectionTitle title="সাম্প্রতিক পোস্ট" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      article: null
    };
  },
  async fetch() {
    const [article] = await this.$axios.$get(
      `posts?slug=${this.$route.params.slug}&_embed`
    );
    this.article = article;
  },
  computed: {
    thumbnail() {
      return this.article._embedded["wp:featuredmedia"][0].source_url;
    }
  }
};
</script>
