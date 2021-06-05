<template>
  <div class="grid grid-cols-1 gap-10 md:grid-cols-4">
    <div class="col-span-2 overflow-hidden rounded-md shadow-xl ">
      <nuxt-link :to="article.slug">
        <img :src="thumbnail" :alt="article.title.rendered" class="w-full " />
      </nuxt-link>
    </div>
    <div class="flex flex-col justify-center col-span-2">
      <nuxt-link
        :to="article.slug"
        class="block text-3xl font-bold text-dark font-HindSiliguri"
      >
        {{ article.title.rendered }}
      </nuxt-link>

      <time class="block my-6 text-xl text-gray-500 ">
        {{ $moment(article.date).format("LLLL") }}
      </time>

      <div
        class="text-xl text-gray-700"
        v-html="article.excerpt.rendered.slice(0, 120) + '...'"
      ></div>

      <nuxt-link
        :to="article.slug"
        class="flex items-center mt-10 space-x-3 text-xl text-primary"
      >
        <span>বিস্তারিত পড়ুন</span>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="w-5 h-5"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
            clip-rule="evenodd"
          />
        </svg>
      </nuxt-link>
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
