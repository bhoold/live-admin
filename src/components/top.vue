<template>
<div class="top">
  <div class="left">
    <el-button
      class="icon menu"
      :class="{active: currentSidePanel==='appPanel'}"
      icon="el-icon-menu"
      title="应用"
      @click.stop="toggleSidePanel('appPanel')"
    ></el-button>
    <router-link class="logo" to="/">liveAdmin</router-link>
  </div>
  <div class="middle">
    <div class="search">
      <el-input placeholder="搜索">
        <i slot="prefix" class="el-input__icon el-icon-search"></i>
      </el-input>
    </div>
  </div>
  <div class="right">
    <el-button
      class="icon setup"
      :class="{active: currentSidePanel==='setupPanel'}"
      icon="el-icon-setting"
      title="设置"
      @click.stop="toggleSidePanel('setupPanel')"
    ></el-button>
    <el-badge :value="99" :hidden="false" class="badge">
      <el-button
        class="icon notify"
        :class="{active: currentSidePanel==='notifyPanel'}"
        icon="el-icon-bell"
        title="通知"
        @click.stop="toggleSidePanel('notifyPanel')"
      ></el-button>
    </el-badge>
    <el-button
      class="icon help"
      :class="{active: currentSidePanel==='helpPanel'}"
      icon="el-icon-service"
      title="帮助"
      @click.stop="toggleSidePanel('helpPanel')"
    ></el-button>
    <el-button
      class="icon avatar"
      :class="{active: currentSidePanel==='accountPanel'}"
      title="账户"
      @click.stop="toggleSidePanel('accountPanel')"
    >
      <img src="https://cid-9346acc584c117d8.users.storage.live.com/users/0x9346acc584c117d8/myprofile/expressionprofile/profilephoto:UserTileStatic,UserTileSmall/MeControlMediumUserTile?ck=1&amp;ex=24&amp;fofoff=1" alt="">
    </el-button>
  </div>
</div>
</template>

<script>
export default {
  props: ['currentSidePanel'],
  methods: {
    toggleSidePanel(panelName) {
      this.$emit('toggleSidePanel', panelName);
    }
  }
}
</script>

<style lang="scss">
.top{
  height: 48px;
  display: flex;
  position: relative;
  z-index: 0;
  flex: 0 0 auto;
  background: #0078d7;
  button.icon{
    margin-left: 0;
    padding: 12px;
    font-size: 24px;
    color: #fff;
    background: none;
    border: none;
    border-radius: 0;
    &:hover{
      background: #005a9e;
    }
    &:focus{
      outline: 1px solid;
      outline-offset: -1px;
    }
    &.active:hover{
      color: var(--themePrimary);
      background: var(--white);
    }
  }
  &>.left{
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    flex: 1 0 auto;
    box-sizing: border-box;
    overflow: hidden;
    max-width: 214px;
    padding-right: 16;
    button.icon{
      padding: 15px;
      font-size: 18px;
      &.active{
        color: var(--themePrimary);
        background: var(--white);
      }
    }
    .logo{
      margin-left: 1em;
      color: #fff;
      text-decoration: none;
    }
  }
  &>.middle{
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    flex: 1 1 0px;
  }
  &>.right{
    display: inline-flex;
    align-items: stretch;
    flex: 0 0 auto;
    .badge{
      sup{
        top: 8px;
        right: 5px;
        padding: 1px;
        height: 16px;
        min-width: 16px;
        font-size: 12px;
        line-height: 16px;
        border: none;
        border-radius: 16px;
        color: var(--white);
        background-color: var(--themeDarker);
        transform: none;
        cursor: pointer;
      }
    }
    .avatar{
      span{
        display: block;
        margin-top: -5px;
        width: 32px;
        height: 32px;
        border-radius: 50%;
        overflow: hidden;
      }
      img{
        display: block;
        width: 100%;
        height: 100%;
      }
    }
  }
}
</style>
