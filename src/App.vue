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
					</div>
					<div class="body">
						<div class="list">
							<div class="listContainer">
								<el-button icon="el-icon-warning">版本升级了!</el-button>
							</div>
						</div>
						<div class="notice">
							<el-button icon="el-icon-warning">版本升级了!</el-button>
						</div>
						<div class="menubar">
							<el-button class="icon" icon="el-icon-message"></el-button>
							<el-button class="icon" icon="el-icon-star-on"></el-button>
							<el-button class="icon" icon="el-icon-mobile-phone"></el-button>
							<el-button class="icon" icon="el-icon-more"></el-button>
						</div>
					</div>
				</el-card>
				<el-card class="content" shadow="never">
					<div slot="header">aa</div>
					<div class="list">sdf</div>
				</el-card>
				<div class="side">
					sdf
				</div>
			</div>
		</div>
		<div class="apps">
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

<style lang="scss">
:root
{ 
	--black:#000; --blackTranslucent40:rgba(0, 0, 0, 0.4); --white:#fff; --whiteTranslucent40:rgba(255, 255, 255, 0.4); --whiteTranslucent90:rgba(255, 255, 255, 0.9); --neutralDark:#212121; --neutralPrimary:#333333; --neutralPrimaryAlt:#3c3c3c; --neutralSecondary:#666666; --neutralTertiary:#a6a6a6; --neutralTertiaryAlt:#c8c8c8; --neutralQuaternary:#d0d0d0; --neutralQuaternaryAlt:#dadada; --neutralLight:#eaeaea; --neutralLighter:#f4f4f4; --neutralLighterAlt:#f8f8f8; --redDark:#a80000; --flaggedMessage:#fffdd9; --richUserContentBackground:#fff; --composeNeutralBackground:#fff; --composeNeutralLighterBackground:#f4f4f4; --themeDarker:#004578; --themeDark:#005A9E; --themeDarkAlt:#106EBE; --themePrimary:#0078D7; --themeSecondary:#2B88D8; --themeTertiary:#71AFE5; --themeLight:#C7E0F4; --themeLighter:#DEECF9; --themeLighterAlt:#EFF6FC; --headerBackground:#0078D7; --headerBackgroundSearch:#005A9E; --headerBrandText:#FFFFFF; --headerTextIcons:#FFFFFF; --headerSearchBoxBackground:rgba(255,255,255,0.7); --headerSearchBoxIcon:#004578; --headerSearchPlaceholderText:#004578; --headerSearchButtonBackground:#0078D7; --headerSearchButtonBackgroundHover:#004578; --headerSearchButtonIcon:#FFFFFF; --headerSearchFilters:#0078D7; --headerSearchFiltersHover:#004578; --headerButtonsBackground:#0078D7; --headerButtonsBackgroundHover:#005A9E; --headerButtonsBackgroundSearch:#005A9E; --headerButtonsBackgroundSearchHover:#004578; --headerBadgeBackground:#004578; --headerBadgeText:#FFFFFF; --headerSearchIcon:#FFFFFF; --searchBoxBackground:rgba(255,255,255,0.7); --fallback-black:#000; --fallback-blackTranslucent40:rgba(0, 0, 0, 0.4); --fallback-white:#fff; --fallback-whiteTranslucent40:rgba(255, 255, 255, 0.4); --fallback-whiteTranslucent90:rgba(255, 255, 255, 0.9); --fallback-neutralDark:#212121; --fallback-neutralPrimary:#333333; --fallback-neutralPrimaryAlt:#3c3c3c; --fallback-neutralSecondary:#666666; --fallback-neutralTertiary:#a6a6a6; --fallback-neutralTertiaryAlt:#c8c8c8; --fallback-neutralQuaternary:#d0d0d0; --fallback-neutralQuaternaryAlt:#dadada; --fallback-neutralLight:#eaeaea; --fallback-neutralLighter:#f4f4f4; --fallback-neutralLighterAlt:#f8f8f8; --fallback-redDark:#a80000; --fallback-flaggedMessage:#fffdd9; --fallback-richUserContentBackground:#fff; --fallback-composeNeutralBackground:#fff; --fallback-composeNeutralLighterBackground:#f4f4f4; --fallback-themeDarker:#004578; --fallback-themeDark:#005A9E; --fallback-themeDarkAlt:#106EBE; --fallback-themePrimary:#0078D7; --fallback-themeSecondary:#2B88D8; --fallback-themeTertiary:#71AFE5; --fallback-themeLight:#C7E0F4; --fallback-themeLighter:#DEECF9; --fallback-themeLighterAlt:#EFF6FC; --fallback-headerBackground:#0078D7; --fallback-headerBackgroundSearch:#005A9E; --fallback-headerBrandText:#FFFFFF; --fallback-headerTextIcons:#FFFFFF; --fallback-headerSearchBoxBackground:rgba(255,255,255,0.7); --fallback-headerSearchBoxIcon:#004578; --fallback-headerSearchPlaceholderText:#004578; --fallback-headerSearchButtonBackground:#0078D7; --fallback-headerSearchButtonBackgroundHover:#004578; --fallback-headerSearchButtonIcon:#FFFFFF; --fallback-headerSearchFilters:#0078D7; --fallback-headerSearchFiltersHover:#004578; --fallback-headerButtonsBackground:#0078D7; --fallback-headerButtonsBackgroundHover:#005A9E; --fallback-headerButtonsBackgroundSearch:#005A9E; --fallback-headerButtonsBackgroundSearchHover:#004578; --fallback-headerBadgeBackground:#004578; --fallback-headerBadgeText:#FFFFFF; --fallback-headerSearchIcon:#FFFFFF; --fallback-searchBoxBackground:rgba(255,255,255,0.7);
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
					border-bottom: 1px solid var(--neutralLight);
					button.toggle{
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
						padding-bottom: 20px;
					}
					.notice{
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
								padding: 12px 40px 15px 0;
								max-width: 117px;
							}
						}
					}
					.menubar{
						flex: 0 0 auto;
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
			}
			&>.side{
				flex: 0 0 auto;
				width: 300px;
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
