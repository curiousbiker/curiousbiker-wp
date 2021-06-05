<template>
  <div class="grid grid-cols-1 gap-10 md:grid-cols-4">
    <div class="col-span-2 overflow-hidden rounded-md shadow-xl">
      <PuSkeleton height="350px" />
    </div>
    <div class="flex flex-col justify-center col-span-2">
      <PuSkeleton :count="2" />

      <div class="my-6">
        <PuSkeleton width="40%" />
      </div>

      <div class="my-6">
        <PuSkeleton :count="2" />
      </div>
    </div>
  </div>
</template>
