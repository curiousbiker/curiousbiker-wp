<template>
  <div class="wrapper grid grid-cols-12">
    <div class=" col-span-8">
      <!-- <h1>{{ article }}</h1> -->
      <!-- 
      <time class=" text-gray-500 text-base block">
        {{ $moment(article.date).format("LLLL") }}
      </time> -->

      <!-- <div class="col-span-2 rounded-md overflow-hidden shadow-xl">
        <img :src="thumbnail" class=" w-full" />
      </div> -->
    </div>
    <div class=" col-span-4"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      article: null
    };
  }
  //   async fetch() {
  //     const [article] = await this.$axios.$get(
  //       `posts?slug=${this.$route.params.slug}&_embed`
  //     );
  //     this.article = article;
  //   },
  //   computed: {
  //     thumbnail() {
  //       return this.article._embedded["wp:featuredmedia"][0].source_url;
  //     }
  //   }
};
</script>
