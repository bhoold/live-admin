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
#app{
    height: 100%;
    width: 100%;
    overflow: hidden;
}
</style>
