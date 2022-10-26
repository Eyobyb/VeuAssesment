<template>
  <input type="text" :placeholder="placeholder" />
</template>

<script>
export default {
  props: ["placeholder"]
};
</script>

<style scoped>
input {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  padding-left: 12px;
  padding-right: 12px;
 
  color: #939597;
  border: 1px solid #e0e2e4;
  border-radius: 4px;
  height: 38px;
}
</style>