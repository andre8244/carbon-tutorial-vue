<template>
  <div class="bx--grid bx--grid--full-width landing-page">
    <div class="bx--row landing-page__banner">
      <div class="bx--col-lg-16">
        <cv-breadcrumb noTrailingSlash aria-label="Page navigation">
          <cv-breadcrumb-item>
            <cv-link href="/">Getting started</cv-link>
          </cv-breadcrumb-item>
        </cv-breadcrumb>
        <h1 class="landing-page__heading">Design &amp; build with Carbon</h1>
      </div>
    </div>
    <div class="bx--row landing-page__r2">
      <div class="bx--col bx--no-gutter">
        <cv-tabs selected="0" aria-label="Tab navigation">
          <cv-tab label="About">
            <div class="bx--grid bx--grid--no-gutter bx--grid--full-width">
              <div class="bx--row landing-page__tab-content">
                <div class="bx--col-md-4 bx--col-lg-7">
                  <h2 class="landing-page__subheading">What is Carbon?</h2>
                  <p class="landing-page__p">
                    Carbon is IBM’s open-source design system for digital
                    products and experiences. With the IBM Design Language as
                    its foundation, the system consists of working code, design
                    tools and resources, human interface guidelines, and a
                    vibrant community of contributors.
                  </p>

                  <cv-modal
                    :visible="modalVisible"
                    :close-aria-label="closeAriaLabel"
                    :size="size"
                    :primary-button-disabled="primaryButtonDisabled"
                    @modal-shown="actionShown"
                    @modal-hidden="actionHidden"
                    @modal-hide-request="actionHideRequest"
                    @after-modal-hidden="actionAfterHidden"
                    :auto-hide-off="autoHideOff"
                  >
                    <!-- <template v-if="use_label" slot="label"
                      >Label of modal</template
                    > -->
                    <template v-if="use_title" slot="title"
                      >Login</template
                    >
                    <template v-if="use_content" slot="content">
                      <!-- <p>
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit, seed do eiusmod tempor incididunt ut labore et
                        dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex
                        ea commodo consequat.
                      </p> -->

                      <cv-form @submit.prevent="actionSubmit">
                        <cv-text-input
                          :light="light"
                          :label="usernameLabel"
                          :disabled="disabled"
                          :placeholder="usernamePlaceholder"
                          v-model="username"
                          class="mg-bottom-2"
                          required
                        >
                          <template
                            v-if="use_helperTextSlot"
                            slot="helper-text"
                            >{{ usernameHelper }}</template
                          >
                        </cv-text-input>
                        <cv-text-input
                          :light="light"
                          :label="passwordLabel"
                          :placeholder="passwordPlaceholder"
                          v-model="password"
                          class="mg-bottom-2"
                          required
                        >
                          <template
                            v-if="use_helperTextSlot"
                            slot="helper-text"
                            >{{ passwordHelper }}</template
                          >
                        </cv-text-input>
                        <cv-button :icon="Notification20">
                          Login
                        </cv-button>
                      </cv-form>
                    </template>
                    <!-- <template v-if="use_secondaryButton" slot="secondary-button"
                      >secondary</template
                    >
                    <template v-if="use_primaryButton" slot="primary-button"
                      >primary</template
                    > -->
                  </cv-modal>

                  <cv-button @click="modalVisible = true"
                    >Open login modal</cv-button
                  >
                </div>
                <div class="bx--col-md-4 bx--offset-lg-1 bx--col-lg-8">
                  <img
                    class="landing-page__illo"
                    src="../../assets/tab-illo.png"
                    alt="Carbon illustration"
                  />
                </div>
              </div>
            </div>
          </cv-tab>
          <cv-tab label="Design">
            <div class="bx--grid bx--grid--no-gutter bx--grid--full-width">
              <div class="bx--row landing-page__tab-content">
                <div class="bx--col-lg-16">
                  Rapidly build beautiful and accessible experiences. The Carbon
                  kit contains all resources you need to get started.
                </div>
              </div>
            </div>
          </cv-tab>
          <cv-tab label="Develop">
            <div class="bx--grid bx--grid--no-gutter bx--grid--full-width">
              <div class="bx--row landing-page__tab-content">
                <div class="bx--col-lg-16">
                  Carbon provides styles and components in Vanilla, React,
                  Angular, and Vue for anyone building on the web.
                </div>
              </div>
            </div>
          </cv-tab>
        </cv-tabs>
      </div>
    </div>
    <div class="bx--row landing-page__r3">
      <div class="bx--col-md-4 bx--col-lg-4">
        <h3 class="landing-page__label">The Principles</h3>
      </div>
      <div class="bx--col-md-4 bx--col-lg-4">Carbon is Open</div>
      <div class="bx--col-md-4 bx--col-lg-4">Carbon is Modular</div>
      <div class="bx--col-md-4 bx--col-lg-4">Carbon is Consistent</div>
    </div>
  </div>
</template>

<script>
import Notification20 from '@carbon/icons-vue/es/notification/20';

export default {
  name: 'LandingPage',
  data() {
    // eslint-disable-next-line no-console
    console.log('Notification20', Notification20); ////
    return {
      closeAriaLabel: 'Close',
      use_label: true,
      use_title: true,
      use_content: true,
      size: 'default',
      use_secondaryButton: true,
      use_primaryButton: true,
      primaryButtonDisabled: false,
      autoHideOff: false,
      modalVisible: false,
      light: false,
      usernameLabel: 'Username',
      disabled: false,
      passwordVisible: false,
      passwordHideLabel: 'Hide password',
      passwordShowLabel: 'Show password',
      usernamePlaceholder: 'Username',
      use_helperTextSlot: true,
      use_invalidMessageSlot: false,
      value: 'value',
      usernameHelper: 'Please input your username',
      invalidMessage: 'Invalid message',
      username: '',
      password: '',
      passwordLabel: 'Password',
      passwordPlaceholder: 'Password',
      passwordHelper: 'Please input your password',
      Notification20: Notification20
    };
  },
  methods: {
    actionShown() {
      // eslint-disable-next-line no-console
      console.log('actionShown'); ////
    },
    actionHidden() {
      // eslint-disable-next-line no-console
      console.log('actionHidden'); ////
      this.modalVisible = false;
    },
    actionHideRequest() {
      // eslint-disable-next-line no-console
      console.log('actionHideRequest'); ////
    },
    actionAfterHidden() {
      // eslint-disable-next-line no-console
      console.log('actionAfterHidden'); ////
    },
    actionSubmit() {
      // eslint-disable-next-line no-console
      console.log('actionSubmit', this.username, this.password); ////
      this.modalVisible = false;
    }
  }
};
</script>

<style lang="scss">
@import '../../styles/carbon-utils';
@import './carbon-overrides';
@import './mixins';

.landing-page__illo {
  max-width: 100%;
}

.landing-page__banner {
  padding-top: $spacing-05;
  padding-bottom: $spacing-07 * 4;
  @include landing-page-background;
}

.landing-page__heading {
  @include carbon--type-style('productive-heading-05');
}

.landing-page__r2 {
  margin-top: rem(-40px);
}

.landing-page__tab-content {
  padding-top: $layout-05;
  padding-bottom: $layout-05;
}

.landing-page__subheading {
  @include carbon--type-style('productive-heading-03');
  @include carbon--font-weight('semibold');
}

.landing-page__p {
  @include carbon--type-style('productive-heading-03');
  margin-top: $spacing-06;
  margin-bottom: $spacing-08;

  @include carbon--breakpoint-between((320px + 1), md) {
    max-width: 75%;
  }
}

.landing-page__r3 {
  padding-top: $spacing-09;
  padding-bottom: $spacing-09;
  @include landing-page-background;
}

.landing-page__label {
  @include carbon--type-style('heading-01');
}
</style>
