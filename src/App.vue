<template>
	<div id="app">
    <layoutView :currentSidePanel="currentSidePanel" @closeSidePanel="closeSidePanel" @toggleSidePanel="toggleSidePanel"></layoutView>

    <!-- 侧边弹窗 -->
    <appPanel v-if="currentSidePanel==='appPanel'"></appPanel>
    <setupPanel v-if="currentSidePanel==='setupPanel'" @close="closeSidePanel" @moreSetup="showMoreSetup"></setupPanel>
    <notifyPanel v-if="currentSidePanel==='notifyPanel'" @close="closeSidePanel"></notifyPanel>
    <helpPanel v-if="currentSidePanel==='helpPanel'" @close="closeSidePanel"></helpPanel>
    <accountPanel v-if="currentSidePanel==='accountPanel'" @close="closeSidePanel"></accountPanel>

    <!-- 设置modal -->
    <setupModal v-if="isShowSetupModal" @close="closeSetupModal" @lessSetup="showLessSetup"></setupModal>
	</div>
</template>
<script>
import layoutView from '@/views/layout';

import appPanel from '@/components/sidePanel/appPanel';
import setupPanel from '@/components/sidePanel/setupPanel';
import notifyPanel from '@/components/sidePanel/notifyPanel';
import helpPanel from '@/components/sidePanel/helpPanel';
import accountPanel from '@/components/sidePanel/accountPanel';
import setupModal from '@/components/modal/setupModal';

export default {
  components: {
    layoutView,
    appPanel,
    setupPanel,
    notifyPanel,
    helpPanel,
    accountPanel,
    setupModal
  },
  data() {
    return {
      currentSidePanel: '',

      isShowSetupModal: false
    }
  },
  methods: {
    closeSidePanel () {
      this.currentSidePanel = '';
    },
    toggleSidePanel ( panelName ) {
      if( this.currentSidePanel !== panelName ) {
        this.currentSidePanel = panelName;
      } else {
        this.closeSidePanel();
      }
    },

    closeSetupModal() {
      this.isShowSetupModal = false;
    },
    showLessSetup() {
      this.closeSetupModal();
      this.currentSidePanel = 'setupPanel';
    },
    showMoreSetup() {
      this.closeSidePanel();
      this.isShowSetupModal = true;
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
  font-weight: 300;
  overflow-y: hidden;
  overflow-x: auto;
  position: absolute;
  font-size: 16px;
}



#app{
    height: 100%;
    width: 100%;
    overflow: hidden;
}
</style>
