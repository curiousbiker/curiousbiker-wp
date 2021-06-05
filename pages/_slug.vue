<template>
  <div class="grid grid-cols-12 gap-10 wrapper">
    <div class="col-span-8 ">
      <h1 class="mb-10 text-3xl font-bold leading-relaxed">
        ডোনাল্ড ট্রাম্প: দুই বছরের জন্য ফেসবুক ও ইন্সটাগ্রামে নিষিদ্ধ সাবেক
        মার্কিন প্রেসিডেন্ট
      </h1>
      <a href="#">
        <img
          class="rounded-md"
          src="https://res.cloudinary.com/curious-biker/image/upload/v1622643329/maxresdefault_1351e576b.jpg"
          alt="feature-image"
        />
      </a>
      <p class="my-10 text-xl leading-relaxed ">
        যুক্তরাষ্ট্রের সাবেক প্রেসিডেন্ট ডোনাল্ড ট্রাম্প ২০২৩ সাল পর্যন্ত ফেসবুক
        ও ইন্সটাগ্রাম একাউন্ট ব্যবহার করতে পারবেন না।
      </p>
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
