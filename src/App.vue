<template>
	<div id="app">
		<div class="appContainer">
			<div class="top">
				<div class="left">
					<el-button class="icon menu" icon="el-icon-menu" title="应用"></el-button>
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
					<el-button class="icon setup" icon="el-icon-setting" title="设置"></el-button>
					<el-badge :value="99" :hidden="false" class="badge"><el-button class="icon notify" icon="el-icon-bell" title="通知"></el-button></el-badge>
					<el-button class="icon help" icon="el-icon-service" title="帮助"></el-button>
					<el-button class="icon avatar">
						<img src="https://cid-9346acc584c117d8.users.storage.live.com/users/0x9346acc584c117d8/myprofile/expressionprofile/profilephoto:UserTileStatic,UserTileSmall/MeControlMediumUserTile?ck=1&amp;ex=24&amp;fofoff=1" alt="">
					</el-button>
				</div>
			</div>
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
					sdf
				</div>
			</div>
		</div>
		<div class="appList">
			<div class="panel">
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
		</div>
	</div>
</template>
<script>
export default {
  data() {
    const data = [{
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
    }];
    return {
      data5: JSON.parse(JSON.stringify(data))
    }
  },
  methods: {
    clickTreeItem(data, node, component) {
      /* console.log(data)
      console.log(node)
      console.log(component) */
    }
  }
}
</script>

<style lang="scss">
:root
{
	--black:#000; --blackTranslucent40:rgba(0, 0, 0, 0.4); --white:#fff; --whiteTranslucent40:rgba(255, 255, 255, 0.4); --whiteTranslucent90:rgba(255, 255, 255, 0.9); --neutralDark:#212121; --neutralPrimary:#333333; --neutralPrimaryAlt:#3c3c3c; --neutralSecondary:#666666; --neutralTertiary:#a6a6a6; --neutralTertiaryAlt:#c8c8c8; --neutralQuaternary:#d0d0d0; --neutralQuaternaryAlt:#dadada; --neutralLight:#eaeaea; --neutralLighter:#f4f4f4; --neutralLighterAlt:#f8f8f8; --redDark:#a80000; --flaggedMessage:#fffdd9; --richUserContentBackground:#fff; --composeNeutralBackground:#fff; --composeNeutralLighterBackground:#f4f4f4; --themeDarker:#004578; --themeDark:#005A9E; --themeDarkAlt:#106EBE; --themePrimary:#0078D7; --themeSecondary:#2B88D8; --themeTertiary:#71AFE5; --themeLight:#C7E0F4; --themeLighter:#DEECF9; --themeLighterAlt:#EFF6FC; --headerBackground:#0078D7; --headerBackgroundSearch:#005A9E; --headerBrandText:#FFFFFF; --headerTextIcons:#FFFFFF; --headerSearchBoxBackground:rgba(255,255,255,0.7); --headerSearchBoxIcon:#004578; --headerSearchPlaceholderText:#004578; --headerSearchButtonBackground:#0078D7; --headerSearchButtonBackgroundHover:#004578; --headerSearchButtonIcon:#FFFFFF; --headerSearchFilters:#0078D7; --headerSearchFiltersHover:#004578; --headerButtonsBackground:#0078D7; --headerButtonsBackgroundHover:#005A9E; --headerButtonsBackgroundSearch:#005A9E; --headerButtonsBackgroundSearchHover:#004578; --headerBadgeBackground:#004578; --headerBadgeText:#FFFFFF; --headerSearchIcon:#FFFFFF; --searchBoxBackground:rgba(255,255,255,0.7); --fallback-black:#000; --fallback-blackTranslucent40:rgba(0, 0, 0, 0.4); --fallback-white:#fff; --fallback-whiteTranslucent40:rgba(255, 255, 255, 0.4); --fallback-whiteTranslucent90:rgba(255, 255, 255, 0.9); --fallback-neutralDark:#212121; --fallback-neutralPrimary:#333333; --fallback-neutralPrimaryAlt:#3c3c3c; --fallback-neutralSecondary:#666666; --fallback-neutralTertiary:#a6a6a6; --fallback-neutralTertiaryAlt:#c8c8c8; --fallback-neutralQuaternary:#d0d0d0; --fallback-neutralQuaternaryAlt:#dadada; --fallback-neutralLight:#eaeaea; --fallback-neutralLighter:#f4f4f4; --fallback-neutralLighterAlt:#f8f8f8; --fallback-redDark:#a80000; --fallback-flaggedMessage:#fffdd9; --fallback-richUserContentBackground:#fff; --fallback-composeNeutralBackground:#fff; --fallback-composeNeutralLighterBackground:#f4f4f4; --fallback-themeDarker:#004578; --fallback-themeDark:#005A9E; --fallback-themeDarkAlt:#106EBE; --fallback-themePrimary:#0078D7; --fallback-themeSecondary:#2B88D8; --fallback-themeTertiary:#71AFE5; --fallback-themeLight:#C7E0F4; --fallback-themeLighter:#DEECF9; --fallback-themeLighterAlt:#EFF6FC; --fallback-headerBackground:#0078D7; --fallback-headerBackgroundSearch:#005A9E; --fallback-headerBrandText:#FFFFFF; --fallback-headerTextIcons:#FFFFFF; --fallback-headerSearchBoxBackground:rgba(255,255,255,0.7); --fallback-headerSearchBoxIcon:#004578; --fallback-headerSearchPlaceholderText:#004578; --fallback-headerSearchButtonBackground:#0078D7; --fallback-headerSearchButtonBackgroundHover:#004578; --fallback-headerSearchButtonIcon:#FFFFFF; --fallback-headerSearchFilters:#0078D7; --fallback-headerSearchFiltersHover:#004578; --fallback-headerButtonsBackground:#0078D7; --fallback-headerButtonsBackgroundHover:#005A9E; --fallback-headerButtonsBackgroundSearch:#005A9E; --fallback-headerButtonsBackgroundSearchHover:#004578; --fallback-headerBadgeBackground:#004578; --fallback-headerBadgeText:#FFFFFF; --fallback-headerSearchIcon:#FFFFFF; --fallback-searchBoxBackground:rgba(255,255,255,0.7);
}
::-webkit-scrollbar{
  width: 0;
  height: 0;
}

body, div{
	margin: 0;
	padding: 0;
}

body{
	width: 100%;
    min-width: 1008px;
    height: 100%;
    overflow-y: hidden;
    overflow-x: auto;
    position: absolute;
}
#app{
    height: 100%;
    width: 100%;
    overflow: hidden;
	.appContainer{
		position: relative;
		display: flex;
		flex-direction: column;
		overflow: hidden;
		height: 100%;
		z-index: 0;
		&>.top{
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
				&:hover{
					background: #005a9e;
				}
				&:focus{
					outline: 1px solid;
					outline-offset: -1px;
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
                font-weight: bold;
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
			}
		}
	}
	.apps{
		position: fixed;
		z-index: 1000000;
		top: 0px;
		left: 0px;
		width: 100vw;
		height: 100vh;
		visibility: hidden;
		.panel{
			position: absolute;
			top: 48px;
			width: 320px;
		}
	}
}
</style>
