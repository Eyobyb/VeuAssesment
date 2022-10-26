<template>
  <drop-down-wrapper @outsideClick="outsideClick">
    <div class="limit-container">
      sort by 
      <span class="highlight">{{' '+sortby}}</span>
      <div :class="{'drop-content':isDown , 'dop-hide':!isDown}">
        <div class="selected-container">
          {{limit}}
          <down-arrow :isDown="true" />
        </div>
        <div class="line"></div>
        <div class="unselected-number">25</div>
        <div class="unselected-number">50</div>
        <div class="unselected-number">100</div>
      </div>
    </div>
  </drop-down-wrapper>
</template>

<script>
import DownArrow from "./DownArrow.vue";
import DropDownWrapper from "./DropDownWrapper.vue";

export default {
  props: ["sortby"],
  data() {
    return {
      isDown: false
    };
  },
  methods: {
    outsideClick() {
      this.isDown = false;
    },
    downClicked() {
      this.isDown = !this.isDown;
    }
  },
  components: { DownArrow, DropDownWrapper }
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
  box-shadow: -15px 0 0 #e0e2e4, 15px 0px 0 #e0e2e4;
}
</style>