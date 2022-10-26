<template>
  <drop-down-wrapper @outsideClick="outsideClick">
    <div class="limit-container">
      {{limit}}
      <secondary-buttons @click.native="downClicked" size="small">
        <down-arrow :isDown="isDown" />
      </secondary-buttons>

      <div :class="{'drop-content':isDown , 'dop-hide':!isDown}">
        <div class="selected-container">
          {{limit}}
          <down-arrow :isDown="true" />
        </div>
        <div class="line"></div>
        <div v-for="(limitValue,index) of limits" :key="index">
          <div
            class="unselected-number"
            v-if="limit!=limitValue"
            @onClick="limitChange(limitValue)"
          >{{limitValue}}</div>
        </div>
      </div>
    </div>
  </drop-down-wrapper>
</template>

<script>
import DownArrow from "./DownArrow.vue";
import DropDownWrapper from "./DropDownWrapper.vue";
import SecondaryButtons from "./SecondaryButtons.vue";

export default {
  props: ["limit"],
  data() {
    return {
      isDown: false,
      limits: [10, 25, 50, 100]
    };
  },
  methods: {
    outsideClick() {
      this.isDown = false;
    },
    downClicked() {
      this.isDown = !this.isDown;
    },
    limitChange(value) {
      this.$emit("limitChange", value);
    }
  },
  components: { SecondaryButtons, DownArrow, DropDownWrapper }
};
</script>


<style scoped>
.limit-container {
  position: relative;
  display: flex;
  align-items: center;
}
.drop-content {
  width: 41px;
  position: absolute;
  left: 0;
  top: -10px;
  background: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 8px 16px;
  gap: 4px;
  border: 1px solid #e0e2e4;
  border-radius: 8px;
  opacity: 1;
  transition: all 0.3s;
  -wekit-transition: all 0.3s;
  -moz-transition: all 0.3s;
}

.dop-hide {
  display: none;
  opacity: 0;
  transition: all 0.3s;
  -wekit-transition: all 0.3s;
  -moz-transition: all 0.3s;
}

.selected-container {
  display: flex;
  align-items: center;
  gap: 4px;
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  color: #252526;
}

.unselected-number {
  height: 20px;
  width: 100%;
}

.unselected-number:hover {
  background: #e0e2e4;
  user-select: none;
  cursor: pointer;
  box-shadow: -15px 0 0 #e0e2e4, 15px 0px 0 #e0e2e4,20px 0px 0 #e0e2e4,25px 0px 0 #e0e2e4,30px 0px 0 #e0e2e4,37px 0px 0 #e0e2e4;
}
</style>