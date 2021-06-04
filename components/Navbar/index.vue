<template>
  <div class="wrapper">
    <div class="navbar">
      <a href="#" class="navbar__logo">
        Curious Biker
      </a>

      <div class="navbar__search">
        <input
          type="text"
          placeholder="সার্চ করুন..."
          class="navbar__search--input focus:ring-primary"
        />
        <svg
          class="navbar__search--icon"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
            clip-rule="evenodd"
          />
        </svg>
      </div>
      <div class="navbar__links flex space-x-4">
        <a href="#">আমাদের সম্পর্কে</a>
        <a href="#">আমাদের সম্পর্কে</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.navbar {
  @apply flex items-center my-4 justify-between;
  &__search {
    @apply w-6/12 relative;
    &--input {
      @apply border px-4 py-2 rounded w-full border-none bg-gray-100;
    }
    &--icon {
      @apply h-5 w-5 absolute top-2 right-2 text-gray-600;
    }
  }
}
</style>
