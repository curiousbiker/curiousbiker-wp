<template>
  <div class=" grid grid-cols-3 gap-5">
    <div class=" col-span-1">
      <div href="#" class="aspect-h-1 aspect-w-1">
        <img
          :src="thumbnail"
          :alt="article.title.rendered"
          class=" w-full object-cover"
        />
      </div>
    </div>
    <div class=" col-span-2">
      <a href="#" class=" text-lg block text-dark font-KohinoorBangla">
        {{ article.title.rendered }}
      </a>

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
