<template>
  <div class="page-conainer">
    Page
    <span class="highlight">{{current}}</span> of
    <span class="highlight">{{total}}</span>
  </div>
</template>

<script>
export default {
  props: ["current", "total"]
};
</script>
