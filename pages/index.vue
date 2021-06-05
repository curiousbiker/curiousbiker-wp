<template>
  <div class="wrapper">
    <sections-featureds />
    <div class="grid grid-cols-12 gap-10 ">
      <div class="col-span-8">
        <div class="my-10 ">
          <sections-block-1 title="বাইকিং টিপস" :category_id="268" :limit="4" />
        </div>
        <div class="my-10 ">
          <sections-block-1
            title="টেকনিক্যাল বিষয়"
            :category_id="42"
            :limit="4"
          />
        </div>
        <div class="grid grid-cols-2 gap-10 ">
          <sections-block-2 title="বাইকিং নিউজ" :category_id="46" :limit="4" />
          <sections-block-2
            title="মোটরবাইক যন্ত্রাংশ"
            :category_id="43"
            :limit="4"
          />
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
</template>

<script>
export default {};
</script>
