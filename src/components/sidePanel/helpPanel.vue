<template>
<div class="helpPanel">
  <div class="panel">
    <div class="heading">
      <span class="title">帮助</span>
      <i class="close el-icon-close" @click="close"></i>
    </div>
    <div class="body"></div>
  </div>
</div>
</template>

<script>
export default {
  created() {

  },
  methods: {
    close() {
      this.$emit('close');
    }
  }
}
</script>

<style lang="scss">
@import 'css/mixin';
.helpPanel{
  @include rightPanel;
}
</style>
