<template>
  <div class="setupModal" @click="close">
    <div class="container">
      <div class="menuPanel">
        <div class="heading">设置</div>
        <div class="body">
          <ul>
            <li class="item">常规</li>
            <li class="item">邮件</li>
            <li class="item active">日历</li>
          </ul>
          <div class="lessSetup">
            <el-button type="text" icon="el-icon-back" @click="lessSetup">转到常用设置</el-button>
          </div>
        </div>
      </div>
      <div class="subPanel">
        <el-scrollbar class="body">
        <ul>
          <li class="item">布局</li>
          <li class="item">规则</li>
          <li class="item active">整理</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>
          <li class="item">附件</li>
          <li class="item">同步</li>
          <li class="item">答复</li>

        </ul>
        </el-scrollbar>
      </div>
      <div class="contentPanel">
        <div class="heading">
          <div class="title">布局</div>
          <div>
            <el-button type="primary">保存</el-button>
            <el-button>放弃</el-button>
            <i class="close el-icon-close" @click="close"></i>
          </div>
        </div>
        <div class="body">
          2
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
    lessSetup() {
      this.$emit('lessSetup');
    }
  }
}
</script>

<style lang="scss">
.setupModal{
  position: fixed;
  z-index: 1;
  top: 0px;
  left: 0px;
  width: 100vw;
  height: 100vh;
  background-color: var(--blackTranslucent40);
  .container{
    display: flex;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    height: 90vh;
    width: 90vw;
    background: var(--white);
    box-shadow: rgba(0, 0, 0, 0.4) 0px 0px 5px 0px;
    ul{
      margin: 0;
      padding: 0;
    }
    li{
      list-style: none;
    }
    .menuPanel{
      width: 220px;
      height: 100%;
      border-right: 1px solid var(--neutralLight);
      background-color: var(--neutralLighter);
      .heading{
        padding: 20px;
        font-size: 22px;
        font-weight: 400;
      }
      .body{
        .item{
          padding: 8px 20px;
          &.active{
            font-weight: 400;
            background-color: var(--themeLighter);
          }
          &:hover{
            background-color: var(--neutralLight);
          }
        }
        .lessSetup{
          padding: 8px 20px;
          button{
            font-weight: 300;
          }
        }
      }
    }
    .subPanel{
      flex: 0 0 auto;
      width: 200px;
      height: 100%;
      text-overflow: ellipsis;
      border-right: 1px solid var(--neutralLight);
      .body{
        padding: 20px 0;
        height: 100%;
        box-sizing: border-box;
        overflow: hidden;
      }
      .item{
        padding: 8px 20px;
        &.active{
          background-color: var(--themeLighter);
        }
        &:hover{
          background-color: var(--neutralLight);
        }
      }
    }
    .contentPanel{
      flex: 1;
      display: flex;
      flex-direction: column;
      .heading{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 20px;
        height: 65px;
        border-bottom: 1px solid var(--neutralLight);
        .title{
          font-size: 22px;
          font-weight: 400;
        }

        .close{
          font-size: 18px;
        }
      }
      .body{
        flex: 1;
      }
    }
  }
}
</style>
