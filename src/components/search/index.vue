<template>
  <div class="search">
    <i class="search__icon fas fa-search" />
    <input
      class="search__input"
      placeholder="Filter by name"
      type="text"
      @keyup="$emit('change', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  name: "Search"
};
</script>

<style></style>
