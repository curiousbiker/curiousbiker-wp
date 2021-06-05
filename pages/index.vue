<template>
  <div class="wrapper" v-if="!$fetchState.pending">
    <sections-featureds :resources="featureds" />

    <div class="grid grid-cols-12 gap-10 ">
      <div class="col-span-8">
        <div class="my-10 ">
          <sections-block-1 title="বাইকিং টিপস" :resources="category1" />
        </div>

        <div class="my-10 ">
          <sections-block-1 title="টেকনিক্যাল বিষয়" :resources="category2" />
        </div>

        <div class="grid grid-cols-2 gap-10 ">
          <sections-block-2 title="বাইকিং নিউজ" :resources="category3" />
          <sections-block-2 title="মোটরবাইক যন্ত্রাংশ" :resources="category4" />
        </div>
      </div>
      <div class="col-span-4">
        <HomeSideBar />
      </div>
    </div>
    <div class="">
      <FullWidthArticles />
    </div>
  </div>
  <div v-else>
    <h1 class="text-5xl">Loading</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      featureds: [],
      category1: [],
      category2: [],

      // col
      category3: [],
      category4: []
    };
  },
  async fetch() {
    const featureds = await this.$axios.$get(
      "posts?categories=268&per_page=9&_embed"
    );

    const category1 = await this.$axios.$get(
      "posts?categories=41&per_page=4&_embed"
    );

    const category2 = await this.$axios.$get(
      "posts?categories=42&per_page=4&_embed"
    );

    const category3 = await this.$axios.$get(
      "posts?categories=46&per_page=4&_embed"
    );

    const category4 = await this.$axios.$get(
      "posts?categories=43&per_page=4&_embed"
    );

    this.featureds = featureds;
    this.category1 = category1;
    this.category2 = category2;
    this.category3 = category3;
    this.category4 = category4;
  }
};
</script>
