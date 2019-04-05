<template>
  <div class="accountPanel">
    <div class="panel">
      <div class="heading">
        <span class="title">我的账户</span>
        <i class="close el-icon-close" @click="close"></i>
      </div>
      <div class="body">
        <ul>
          <li><el-button type="text">编辑个人资料</el-button></li>
          <li><el-button type="text">退出登录</el-button></li>
        </ul>
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
    }
  }
}
</script>

<style lang="scss">
@import 'css/mixin';
.accountPanel{
  @include rightPanel;
  .body{
    ul{
      margin: 0;
      padding: 0;
    }
    li{
      list-style: none;
    }
  }
}
</style>
