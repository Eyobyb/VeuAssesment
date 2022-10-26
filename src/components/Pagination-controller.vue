<template>
  <div class="pagination-container">
    <page-location current="1" total="2" />
    <sort-order sortby="Sort Order" />
    <limit-drop-down limit="10" @limitChange="limitChange" />
  </div>
</template>

<script>
import LimitDropDown from "./LimitDropDown.vue";
import PageLocation from "./PageLocation.vue";
import SortOrder from "./SortOrder.vue";

export default {
  components: { LimitDropDown, PageLocation, SortOrder },
  props: ["sortby", "limit", "current", "total"],
  methods: {
    limitChange(value) {
      this.$emit("limitChange", value);
    }
  }
};
</script>
<style scoped>
.pagination-container {
  max-width: 450px;
  min-width: 300px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-bottom: 56px;
}
</style>

