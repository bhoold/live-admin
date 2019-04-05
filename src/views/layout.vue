<template>
  <div class="appContainer" @click="closeSidePanel">
    <top @toggleSidePanel="toggleSidePanel"></top>
    <div class="main">
      <el-card class="menu" shadow="never">
        <div class="header" slot="header">
          <el-button class="icon toggle" icon="el-icon-goods" title="切换左侧面板"></el-button>
          <!-- <el-button class="icon favorite" icon="el-icon-star-on" title="收藏的菜单项"></el-button>
          <el-button class="icon search" icon="el-icon-search" title="查找菜单项"></el-button> -->
        </div>
        <div class="body">
          <div class="list">
            <el-scrollbar class="listContainer">
              <el-tree
                :data="data5"
                icon-class="iconParent el-icon-arrow-right"
                :indent="0"
                node-key="id"
                default-expand-all
                :expand-on-click-node="true"
                @node-click="clickTreeItem"
                >
                <div class="item" slot-scope="{node,data}" :class="{parent:data.children}" :title="node.label">
                  <i class="icon el-icon-star-off" v-if="!data.children"></i>
                  <span>{{node.label}}</span>
                </div>
              </el-tree>
            </el-scrollbar>
          </div>
          <div class="notice">
            <el-button icon="el-icon-warning">版本升级了！</el-button>
          </div>
          <div class="menuBar">
            <el-button class="icon" icon="el-icon-phone-outline"></el-button>
            <el-button class="icon" icon="el-icon-message"></el-button>
            <el-button class="icon" icon="el-icon-mobile-phone"></el-button>
            <el-button class="icon" icon="el-icon-more"></el-button>
          </div>
        </div>
      </el-card>
      <el-card class="content" shadow="never">
        <div class="header" slot="header">
        <div class="breadcrumb">
          <div><a href="">首页</a></div>
          <i class="el-icon-arrow-right"></i>
          <div><a href="">基础设置</a></div>
          <i class="el-icon-arrow-right"></i>
          <div><a href="">网站资料设置</a></div>
        </div>
        </div>
        <div class="body">
          <div class="list">
          <el-scrollbar class="listContainer">
            <div class="wrap">
              test
            </div>
          </el-scrollbar>
          </div>
        </div>
      </el-card>
      <div class="side">
        <div class="heading">
          <span class="title">小技巧：</span>
        </div>
        <div class="body">
          2011年，参加过台北奥美的一个培训，很精彩，我还记得讲师是一个戴着黑框眼镜的男纸，他对洞察（insight）的描述是我听过最精妙的。他说，一个牛逼的洞察能激发消费者的3重反应。
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import top from '@/components/top';

export default {
  components: {
    top
  },
  data () {
    const data = [
      {
        id: 1,
        icon: '',
        label: '基础设置',
        children: [{
          id: 1,
          label: '网站设置'
        },{
          id: 2,
          label: '支付设置'
        },{
          id: 3,
          label: '微信设置'
        },{
          id: 4,
          label: '邮箱设置'
        },{
          id: 5,
          label: '短信设置'
        }]
      }, {
        id: 2,
        label: '商品管理',
        children: [{
          id: 5,
          label: '列表'
        }, {
          id: 6,
          label: '属性'
        }]
      }, {
        id: 3,
        label: '销售',
        children: [{
          id: 7,
          label: '二级 3-1'
        }, {
          id: 8,
          label: '二级 3-2'
        }]
      }, {
        id: 4,
        label: '客户',
        children: [{
          id: 7,
          label: '二级 3-1'
        }, {
          id: 8,
          label: '二级 3-2'
        }]
      }, {
        id: 5,
        label: '报表',
        children: [{
          id: 7,
          label: '二级 3-1'
        }, {
          id: 8,
          label: '二级 3-2'
        }]
      }, {
        id: 6,
        label: 'CMS'
      }
    ];
    return {
      data5: JSON.parse(JSON.stringify(data)),
    }
  },
  props: ['currentSidePanel'],
  created () {

  },
  methods: {
    closeSidePanel () {
      this.$emit('closeSidePanel');
    },
    toggleSidePanel(panelName) {
      this.$emit('toggleSidePanel', panelName);
    },

    clickTreeItem(data, node, component) {
      /* console.log(data)
      console.log(node)
      console.log(component) */
    }

  }
}
</script>

<style lang="scss">
.appContainer{
  position: relative;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  height: 100%;
  z-index: 0;
  &>.main{
    display: flex;
    height: auto;
    flex: 1;
    flex-flow: row nowrap;
    align-items: stretch;
    &>.menu{
      display: flex;
      flex-flow: column;
      flex: 0 0 auto;
      width: 214px;
      border: none;
      background-color: var(--neutralLighter);
      .el-card__header{
        flex: 0 0 auto;
        border: none;
      }
      .header{
        margin: -18px -20px;
        height: 50px;
        border-bottom: 1px solid var(--neutralLight);
        box-sizing: border-box;
        button.icon{
          margin-left: 0;
          padding: 15px;
          font-size: 18px;
          background: none;
          border: none;
          border-radius: 0;
          &:hover{
            background-color: var(--themeLight);
            color: var(--neutralDark);
          }
          &:focus{
            color: var(--neutralDark);
          }
        }
      }
      .el-card__body{
        display: flex;
        flex: 1 1 auto;
      }
      .body{
        display: flex;
        flex: 1 1 auto;
        flex-flow: column nowrap;
        margin: -20px;
        border-right: 1px solid var(--neutralLight);
        .list{
          flex: 1 1 auto;
          position: relative;
          height: 0;
          .listContainer{
            height: 100%;
          }
          .el-tree{
            background: inherit;
          }
          .el-tree-node{
            &.is-current{
              &>.el-tree-node__content{
              background-color: var(--themeLight)!important;
              }
            }
          }
          .el-tree-node__content{
            height: 36px;
            &:hover{
              background-color: var(--neutralLight);
            }
          }
          .iconParent{
            padding: 15px;
            color: inherit;
            font-size: inherit;
            &.is-leaf{
              display: none;
            }
          }
          .item{
            &.parent{
              font-weight: 400;
            }
            .icon{
              padding: 15px;
            }
          }
        }
        .notice{
          border-top: 1px solid var(--neutralLight);
          button{
            position: relative;
            display: block;
            padding: 0;
            width: 100%;
            transition: all .3s;
            font-size: 14px;
            border: none;
            border-radius: 0;
            background: none;
            text-align: left;
            &:hover{
              background-color: var(--white);
              box-shadow: inset 0 0 0 var(--neutralLight),inset 0 1px 0 var(--neutralLight),inset 0 -3px 0 var(--headerButtonsBackground);
            }
            i{
              position: absolute;
              left: 17px;
              top: 14px;
            }
            span{
              display: inline-block;
              margin-left: 56px;
              padding: 12px 20px 15px 0;
              line-height: 1.3em;
              white-space: pre-wrap;
            }
          }
        }
        .menuBar{
          /* flex: 0 0 auto; */
          position: relative;
          display: flex;
          flex-wrap: nowrap;
          border-top: 1px solid var(--neutralLight);
          button.icon{
            padding: 15px;
            font-size: 18px;
            background: none;
            border: none;
            &:hover{
              background-color: var(--neutralLight);
              color: var(--neutralDark);
            }
            &:focus{
              color: var(--neutralDark);
              outline: 0;
            }
          }
          button.icon+button.icon{
            margin-left: 7px;
          }
        }
      }
    }
    &>.content{
      display: flex;
      flex-flow: column;
      flex: 1 1 auto;
      border: none;
      .el-card__header{
        flex: 0 0 auto;
        border: none;
      }
      .header{
        margin: -18px -20px;
        height: 50px;
        border-bottom: 1px solid var(--neutralLight);
        box-sizing: border-box;
        background-color: var(--neutralLighter);
        .breadcrumb{
          display: flex;
          align-items: center;
          height: 100%;
          div{
            margin: 0 5px;
          }
          a{
            color: inherit;
            text-decoration: none;
          }
        }
      }
      .el-card__body{
        display: flex;
        flex: 1 1 auto;
      }
      .body{
        display: flex;
        flex: 1 1 auto;
        flex-flow: column nowrap;
        margin: -20px;
        border-right: 1px solid var(--neutralLight);
        .list{
          flex: 1 1 auto;
          position: relative;
          height: 0;
          .listContainer{
            height: 100%;
          }
          .wrap{
            height: 3000px;
          }
        }
      }
    }
    &>.side{
      flex: 0 0 auto;
      width: 300px;
      background-color: var(--neutralLighter);
      .heading{
        padding: 10px 20px 0;
        height: 50px;
        box-sizing: border-box;
        .title{
          font-size: 22px;
          font-weight: 100;
        }
      }
      .body{
        padding: 0 20px 10px;
        font-size: 14px;
        font-weight: 100;
      }
    }
  }
}
</style>
