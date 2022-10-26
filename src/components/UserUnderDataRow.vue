<template>
  <div class="user-under-data-row-container">
    <div class="image-box-container">
      <user-image size="large" :url="image" />
      <div class="action-container">
        <secondary-buttons :size="'normal'" :type="'main'">Replace</secondary-buttons>
        <secondary-buttons :size="'normal'">Clear</secondary-buttons>
      </div>
    </div>
    <div class="user-under-data-row-container">
      <custom-input-with-lable title="Image Title">
        <custom-input class="w-full" placeholder="Image Title" />
      </custom-input-with-lable>
      <custom-input-with-lable title="Alt Text">
        <custom-input class="w-full" placeholder="Alt Text" />
      </custom-input-with-lable>
      <custom-input-with-lable title="Link">
        <custom-input class="w-full" placeholder="Link" />
      </custom-input-with-lable>
      <custom-input-with-lable title="Code">
        <custom-input class="w-full" placeholder="Code" />
      </custom-input-with-lable>
    </div>
  </div>
</template>

<script>
import CustomInput from "./CustomInput.vue";
import CustomInputWithLable from "./CustomInputWithLable.vue";
import SecondaryButtons from "./SecondaryButtons.vue";
import UserImage from "./UserImage.vue";

export default {
  props: ["image"],
  components: { UserImage, SecondaryButtons, CustomInputWithLable, CustomInput }
};
</script>

<style scoped>
.image-box-container {
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding-top: 24px;
  align-items: center;
}

.action-container {
  display: flex;
  flex-direction: column;
  max-height: max-content;
  max-width: max-content;
  gap: 8px;
}
.user-under-data-row-container {
  display: flex;
  flex-direction: column;
  width: 100%;
  gap: 16px;

}

.w-full{

}
</style>