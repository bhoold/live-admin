<template>
<div class="setupPanel">
  <div class="panel">
    <div class="heading">
      <span class="title">快速设置</span>
      <i class="close el-icon-close" @click="close"></i>
    </div>
    <div class="body">
      <div class="content">
        <div class="moreSetup">
          <el-button type="text" @click="moreSetup">显示全部设置</el-button>
        </div>
      </div>
    </div>
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
    },
    moreSetup() {
      this.$emit('moreSetup');
    }
  }
}
</script>

<style lang="scss">
@import 'css/mixin';
.setupPanel{
  @include rightPanel;
  .body{
    .content{
      .moreSetup{
        button{
          font-weight: 300;
        }
      }
    }
  }
}
</style>
