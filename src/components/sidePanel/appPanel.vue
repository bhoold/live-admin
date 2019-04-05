<template>
<div class="appPanel">
  <el-scrollbar class="panel">
  <div class="grid">
    <a href="#">
      <i class="el-icon-share"></i>
      <span>客户系统</span>
    </a>
    <a href="#">
      <i class="el-icon-goods"></i>
      <span>基础系统</span>
    </a>
    <a href="#">
      <i class="el-icon-time"></i>
      <span>OA系统</span>
    </a>
    <a href="#">
      <i class="el-icon-edit"></i>
      <span>edit</span>
    </a>
    <a href="#">
      <i class="el-icon-tickets"></i>
      <span>tickets</span>
    </a>
    <a href="#">
      <i class="el-icon-share"></i>
      <span>share</span>
    </a>
    <a href="#">
      <i class="el-icon-goods"></i>
      <span>goods</span>
    </a>
    <a href="#">
      <i class="el-icon-time"></i>
      <span>time</span>
    </a>
    <a href="#">
      <i class="el-icon-edit"></i>
      <span>edit</span>
    </a>
    <a href="#">
      <i class="el-icon-tickets"></i>
      <span>tickets</span>
    </a>
    <a href="#">
      <i class="el-icon-share"></i>
      <span>share</span>
    </a>
    <a href="#">
      <i class="el-icon-goods"></i>
      <span>goods</span>
    </a>
    <a href="#">
      <i class="el-icon-time"></i>
      <span>time</span>
    </a>
    <a href="#">
      <i class="el-icon-edit"></i>
      <span>edit</span>
    </a>
    <a href="#">
      <i class="el-icon-tickets"></i>
      <span>tickets</span>
    </a>
    <a href="#">
      <i class="el-icon-share"></i>
      <span>share</span>
    </a>
    <a href="#">
      <i class="el-icon-goods"></i>
      <span>goods</span>
    </a>
    <a href="#">
      <i class="el-icon-time"></i>
      <span>time</span>
    </a>
    <a href="#">
      <i class="el-icon-edit"></i>
      <span>edit</span>
    </a>
    <a href="#">
      <i class="el-icon-tickets"></i>
      <span>tickets</span>
    </a>
    <a href="#">
      <i class="el-icon-share"></i>
      <span>share</span>
    </a>
    <a href="#">
      <i class="el-icon-goods"></i>
      <span>goods</span>
    </a>
    <a href="#">
      <i class="el-icon-time"></i>
      <span>time</span>
    </a>
    <a href="#">
      <i class="el-icon-edit"></i>
      <span>edit</span>
    </a>
    <a href="#">
      <i class="el-icon-tickets"></i>
      <span>tickets</span>
    </a>
    <a href="#">
      <i class="el-icon-share"></i>
      <span>share</span>
    </a>
    <a href="#">
      <i class="el-icon-goods"></i>
      <span>goods</span>
    </a>
    <a href="#">
      <i class="el-icon-time"></i>
      <span>time</span>
    </a>
    <a href="#">
      <i class="el-icon-edit"></i>
      <span>edit</span>
    </a>
    <a href="#">
      <i class="el-icon-tickets"></i>
      <span>tickets</span>
    </a>
    <a href="#">
      <i class="el-icon-share"></i>
      <span>share</span>
    </a>
    <a href="#">
      <i class="el-icon-goods"></i>
      <span>goods</span>
    </a>
    <a href="#">
      <i class="el-icon-time"></i>
      <span>time</span>
    </a>
    <a href="#">
      <i class="el-icon-edit"></i>
      <span>edit</span>
    </a>
    <a href="#">
      <i class="el-icon-tickets"></i>
      <span>tickets</span>
    </a>

  </div>
  </el-scrollbar>
</div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import 'css/mixin';
.appPanel{
  position: fixed;
  z-index: 1;
  top: 0px;
  left: 0px;
  width: 100vw;
  height: 100vh;
  pointer-events: none;
  .panel{
    position: absolute;
    top: 48px;
    width: 320px;
    height: calc(100% - 48px);
    background-color: var(--white);
    box-shadow: rgba(0, 0, 0, 0.2) 0px 0px 30px 0px;
    pointer-events: auto;
    .grid{
      display: grid;
      grid-template-columns: auto auto auto;
      grid-gap: 10px;
      justify-content: center;
      margin: 25px 0;
      a{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 80px;
        height: 80px;
        background: var(--neutralLighterAlt);
        color: inherit;
        text-decoration: none;
        &:hover{
          color: var(--white);
          background: var(--themePrimary);
          i{
            color: var(--white);
          }
        }
        i{
          margin-bottom: 10px;
          font-size: 30px;
          color: var(--themePrimary);
        }
        span{
          font-size: 12px;
        }
      }
    }

  }
}
</style>
