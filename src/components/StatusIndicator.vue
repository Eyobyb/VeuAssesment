<template>
  <div :style="{backgroundColor:status}"></div>
</template>

<script>
export default {
  props: ["status"]
};
</script>

<style scoped>
div {
  height: 9.33px;
  width: 9.33px;
  border-radius: 50%;
}
</style>