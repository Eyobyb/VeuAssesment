<template>
  <div class="main-row-container">
    <div class="sub-row-container">
      <slot name="image" />
      <slot name="status" />
      <slot name="name" />
    </div>
    <div class="sub-row-container">
      <slot name="date" />
      <secondary-buttons @click.native="downClicked" size="small">
        <down-arrow  :isDown="isDown" />
      </secondary-buttons>
    </div>
  </div>
</template>

<script>
import DownArrow from "./DownArrow.vue";
import SecondaryButtons from "./SecondaryButtons.vue";

export default {
  components: { DownArrow, SecondaryButtons },
  data() {
    return {
      isDown: false
    };
  },
  methods: {
    downClicked() {
      this.isDown = !this.isDown;
      this.$emit("unfold", this.isDown);
    }
  }
};
</script>

<style scroped>
.main-row-container {
  display: flex;
  justify-content: space-between;
}
.sub-row-container {
  display: flex;
  gap: 11.33px;
  align-items: center;
  width: max-content;
}
</style>