<template>
  <div id="app">
    <tutorial-header />
    <cv-content id="#main-content">
      <router-view />
    </cv-content>

    <!-- <cv-header aria-label="Carbon header">
      <cv-skip-to-content href="#main-content">
        Skip to content
      </cv-skip-to-content>
      <cv-header-name href="javascript:void(0)" prefix="IBM">
        [Platform]
      </cv-header-name>
      <template v-slot:left-panels v-if="areLeftPanels"> </template>
      <template v-slot:right-panels v-if="areRightPanels"> </template>
    </cv-header>

    test1

    <cv-side-nav id="side-nav" fixed expanded>
      <cv-side-nav-items>
        <cv-side-nav-menu title="L1 menu">
          <template v-slot:nav-icon
            ><Fade16
          /></template>
          <cv-side-nav-menu-item href="javascript:void(0)" active>
            L2 menu item
          </cv-side-nav-menu-item>
          <cv-side-nav-menu-item href="javascript:void(0)">
            L2 menu item
          </cv-side-nav-menu-item>
          <cv-side-nav-menu-item href="javascript:void(0)">
            L2 menu item
          </cv-side-nav-menu-item>
        </cv-side-nav-menu>
        <cv-side-nav-menu title="L1 menu">
          <template v-slot:nav-icon
            ><Fade16
          /></template>
          <cv-side-nav-menu-item href="javascript:void(0)">
            L2 menu item
          </cv-side-nav-menu-item>
          <cv-side-nav-menu-item href="javascript:void(0)" aria-current="page">
            L2 menu item
          </cv-side-nav-menu-item>
          <cv-side-nav-menu-item href="javascript:void(0)">
            L2 menu item
          </cv-side-nav-menu-item>
        </cv-side-nav-menu>
        <cv-side-nav-link href="javascript:void(0)">
          <template v-slot:nav-icon
            ><Fade16
          /></template>
          L1 link
        </cv-side-nav-link>
        <cv-side-nav-link href="javascript:void(0)">
          <template v-slot:nav-icon
            ><Fade16
          /></template>
          L1 link
        </cv-side-nav-link>
      </cv-side-nav-items>
    </cv-side-nav>

    test2 -->
  </div>
</template>

<script>
import TutorialHeader from './components/TutorialHeader';
// import Fade16 from '@carbon/icons-vue/es/fade/16';

export default {
  name: 'App',
  components: {
    TutorialHeader
    // Fade16
  },
  data() {
    return {
      areLeftPanels: true,
      areRightPanels: true
    };
  }
};
</script>

<style lang="scss">
@import './styles/carbon';

.right-panel {
  left: auto;
  right: 0;
}

.mg-bottom-2 {
  margin-bottom: 2rem;
}
</style>
