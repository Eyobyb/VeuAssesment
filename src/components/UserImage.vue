<template>
  <img :src="url" alt :class="{small:isSmall, large:isLarge}" />
</template>

<script>
export default {
  props: ["url", "size"],
  computed: {
    isSmall() {
      return this.size == "small";
    },
    isLarge() {
      return this.size == "large";
    }
  }
};
</script>

<style scroped>
.small {
  width: 24px;
  height: 24px;
}
.large {
  width: 200px;
  height: 200px;
}
img {
  object-fit: fill;
  border-radius: 2px;
}
</style>