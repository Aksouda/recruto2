<template>
  <div>
  <!-- Google Tag Manager -->
<!-- End Google Tag Manager -->
    <v-app-bar
      app
      color="white"
      class="app-bar-shadow"
    >
      <div class="toolbar-wrapper">
        <div class="d-flex align-center">
          <nuxt-link :to="localePath('/')">
            <transition
              appear
              name="rotate"
            >
              <v-img
                alt="Recruto logo"
                class="shrink mr-2"
                contain
                :src="logoSrc"
                transition="fade-transition"
                width="120"
              />
            </transition>
          </nuxt-link>
          <div class="companii">Pentru companii</div>
        </div>
        <v-spacer />
        <v-btn
          text
          class="hidden-sm-and-down text-none font-weight-regular"
          :to="localePath('/contact')"
        >
          {{ $t('frontpage.contactus') }}
        </v-btn>
        <v-btn
          text
          class="hidden-sm-and-down text-none font-weight-regular"
          :to="localePath('/candidate')"
        >
          {{ $t('frontpage.cta_candidate') }}
        </v-btn>
        <v-btn
          text
          :to="localePath('/company')"
          class="hidden-sm-and-down text-none font-weight-regular"
        >
          {{ $t('frontpage.call_to_action') }}
        </v-btn>
        <LanguageSwitcher />
      </div>
      <div class="line"></div>
    </v-app-bar>
  </div>
</template>

<script>
import { mdiMenu } from '@mdi/js'

export default {
  components: {
    LanguageSwitcher: () => import('./LanguageSwitcher')
  },
  data: function () {
    const icons = { mdiMenu }
    return {
      drawer: false,
      logoSrc: require('@/assets/logo.png'),
      icons
    }
  }
}

</script>
<style scoped>
.app-bar-shadow {
  box-shadow: inset 0 -1px 0 0 rgba(0,0,0,0.1) !important;
  height:84px !important
}

.toolbar-wrapper {
  display: flex;
  flex-direction: row;
  margin: auto;
  max-width: 1260px;
  width: 100%;
  align-items: center;
  height:84px !important
}

@keyframes spinHorizontal {
  0% { transform: rotateY(0deg); }
  100% { transform: rotateY(360deg); }
}
.rotate-enter-active {
  animation: spinHorizontal 1s;
}

.v-menu__content {
  box-shadow: 0 4px 4px 0 rgba(0,0,0,0.02) !important;
}
.d-flex{
  flex-direction:column !important;
}
.companii{
  opacity:0;
}
</style>
