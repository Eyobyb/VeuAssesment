<template>
  <div class="button" :class="{normal:isNormal, small:isSmall, main:isMain , absent:!isMain}">
    <slot />
  </div>
</template>

<script>
export default {
  props: ["type", "size"],
  computed:{
    isSmall(){
        return this.size=='small'
    },
    isNormal(){
        return this.size=='normal'
    },
    isMain(){
        return this.type=='main'
    },
  }
};
</script>
<style scoped>
div {
  display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 4px;
    white-space: nowrap;
    user-select: none;
    cursor: pointer;

}
.normal {
  padding: 9px;
  padding-block: 5.5px;
}

.small {
  padding: 5.5px;
}


.main{
    background: #375673;
    color: white;
}

.main:hover{
    background: #304C65;
}

.main:active{
    background: #375673;
}
.absent{
    background: transparent;

}
.absent:hover{
background: #E0E2E4
}
.absent:active{
background: #ededed
}


</style>