<template>
  <div class="input-container">
    <custom-input  :placeholder="placeholder"></custom-input>
    <main-button :type="actiontype">{{actionname}}</main-button>
  </div>
</template>

<script>
import CustomInput from "./CustomInput.vue";
import MainButton from "./MainButton.vue";
export default {
  components: {
    MainButton,
    CustomInput
  },
  props:['actionname','actiontype','placeholder']
};
</script>

<style scoped>
.input-container{
    display: flex;
    gap:3px;
}
input{
  width: 100%;
}
</style>