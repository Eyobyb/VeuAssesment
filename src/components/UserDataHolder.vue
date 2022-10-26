<template>
  <div class="main-down-row-container">
    <user-data-row @unfold="unfold">
      <template #image>
        <user-image size="small" :url="userData.image" />
      </template>

      <template #status>
        <status-indicator :status="userData.status" />
      </template>
      <template #name>
        <p>{{userData.name}}</p>
      </template>
      <template #date>
        <date-value :date="userData.date" />
      </template>
    </user-data-row>
    <div class="fold-container" :class="{max:fold , min:!fold}">
      <user-under-data-row :image="userData.image"></user-under-data-row>
    </div>

    <div class="line"></div>
  </div>
</template>

<script>
import StatusIndicator from "./StatusIndicator.vue";
import UserDataRow from "./UserDataRow.vue";
import UserImage from "./UserImage.vue";
import DateValue from "./DateValue.vue";
import UserUnderDataRow from "./UserUnderDataRow.vue";

export default {
  components: {
    UserDataRow,
    UserImage,
    StatusIndicator,
    DateValue,
    UserUnderDataRow
  },
  props: ["userData"],
  data() {
    return {
      fold: false
    };
  },
  methods: {
    unfold(value) {
      this.fold = value;
    }
  }
};
</script>

<style scoped>
.main-down-row-container {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.fold-container {
  overflow: hidden;
  transition: all 300ms ease-in-out;
}

.min {
  height: 0px;
}

.max {
  height: 620px;
}


</style>