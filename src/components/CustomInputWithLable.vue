<template>
  <div class="custom-input-with-lable-container">
    <div class="title-container">
      <p>{{title}}</p>
      <p v-if="title=='Code'">{{jsonTitle}}</p>
    </div>
    <slot />
  </div>
</template>

<script>
export default {
  props: ["title"],
  computed: {
    jsonTitle() {
      return "<json>";
    }
  }
};
</script>

<style scoped>
p {
  font-weight: 700;
}

.custom-input-with-lable-container {
  display: flex;
  flex-direction: column;
  width: 100%;
}
.title-container {
  display: flex;
  justify-content: space-between;
}
p {
  line-height: 0;
  color: #6a6c6d !important;
}
</style>