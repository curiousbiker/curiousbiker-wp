<template>
  <div class="grid grid-cols-3 gap-5 ">
    <div class="col-span-1">
      <PuSkeleton height="100px" />
    </div>
    <div class="col-span-2">
      <PuSkeleton :count="2" />
    </div>
  </div>
</template>
