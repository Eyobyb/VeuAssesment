<template>
  <div class="button" :class="{main :isColorTypeMain , secondary:isColorTypeSecondary}">
    <slot />
  </div>
</template>

<script>
export default {
  props: ["type"],
  computed: {
    isColorTypeMain() {
      return "main" == this.type;
    },
    isColorTypeSecondary() {
      return "secondary" == this.type;
    }
  }
};
</script>

<style scoped>
.button {
  padding: 16px;
  padding-block: 11px;
  border-radius: 4px;
  cursor: pointer;
  width: max-content;
  user-select: none;
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  color: #ffffff;
  display: flex;
  align-items: center;
  white-space: nowrap;
}
.main {
  background: #375673;
}

.main:hover {
  background: #2f4a63;
}
.main:active {
  background: #395977;
}

.secondary {
  background: #377364;
}
.secondary:hover {
  background: #2f6457;
}
.secondary:active {
  background: #3f8775;
}
</style>