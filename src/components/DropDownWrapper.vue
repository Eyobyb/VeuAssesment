<template>
  <div v-click-outside="outsideClick" class="max-width">
    <slot />
  </div>
</template>

<script>
export default {
  methods: {
    outsideClick() {
      this.$emit("outsideClick");
    }
  },
  directives: {
    "click-outside": {
      bind: function(el, binding, vnode) {
        el.clickOutsideEvent = function(event) {
          // here I check that click was outside the el and his children
          if (!(el == event.target || el.contains(event.target))) {
            // and if it did, call method provided in attribute value
            vnode.context[binding.expression](event);
          }
        };
        document.body.addEventListener("click", el.clickOutsideEvent);
      },
      unbind: function(el) {
        document.body.removeEventListener("click", el.clickOutsideEvent);
      }
    }
  }
};
</script>

<style scoped>
.max-width {
  width: max-content;
}
</style>