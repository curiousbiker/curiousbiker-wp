<template>
  <div>
    <div
      class=" overflow-hidden rounded-md shadow hover:shadow-xl transition duration-300"
    >
      <nuxt-link :to="article.slug">
        <img :src="thumbnail" :alt="article.title.rendered" class=" w-full" />
      </nuxt-link>
    </div>
    <div class=" mt-4">
      <nuxt-link
        :to="article.slug"
        class=" text-lg block text-dark font-KohinoorBangla"
      >
        {{ article.title.rendered }}
      </nuxt-link>

      <time class=" text-gray-500 text-base block">
        {{ $moment(article.date).format("LLLL") }}
      </time>
    </div>
  </div>
</template>

<script>
export default {
  props: ["article"],
  computed: {
    thumbnail() {
      return this.article._embedded["wp:featuredmedia"][0].source_url;
    }
  }
};
</script>
