<template>
  <div class=" grid grid-cols-1 md:grid-cols-4 gap-10">
    <div class=" col-span-2 rounded-md overflow-hidden shadow-xl">
      <img :src="thumbnail" :alt="article.title.rendered" class=" w-full" />
    </div>
    <div class="col-span-2 flex flex-col justify-center">
      <nuxt-link
        :to="article.slug"
        class=" text-3xl block text-dark font-HindSiliguri font-bold"
      >
        {{ article.title.rendered }}
      </nuxt-link>

      <time class=" text-gray-500 text-xl my-6 block">
        {{ $moment(article.date).format("LLLL") }}
      </time>

      <div
        class="text-xl text-gray-700"
        v-html="article.excerpt.rendered.slice(0, 120) + '...'"
      ></div>

      <nuxt-link
        :to="article.slug"
        class=" mt-10 text-primary items-center text-xl flex space-x-3"
      >
        <span>বিস্তারিত পড়ুন</span>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5"
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
