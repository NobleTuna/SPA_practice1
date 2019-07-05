<template>
<v-layout align-center justify-center row fill-height data-aos="fade-up">
  <v-flex xs5 text-xs-center>
    <v-layout align-center justify-center row fill-height elevation-5 style="min-height:500px;" white pa-4>
      <v-flex xs12 text-xs-center>
        <v-btn round color="#df4a31" dark v-on:click="loginWithGoogle" style="width:100%;">
          <v-icon size="25" class="mr-2">fa-google</v-icon> Google 로그인
        </v-btn>
      </v-flex>
    </v-layout>
  </v-flex>
</v-layout>
</template>

<script>
import FirebaseService from '@/services/FirebaseService'

import AOS from 'aos';
import 'aos/dist/aos.css';

AOS.init();

AOS.init({
  // Global settings:
  disable: false, // accepts following values: 'phone', 'tablet', 'mobile', boolean, expression or function
  startEvent: 'DOMContentLoaded', // name of the event dispatched on the document, that AOS should initialize on
  initClassName: 'aos-init', // class applied after initialization
  animatedClassName: 'aos-animate', // class applied on animation
  useClassNames: false, // if true, will add content of `data-aos` as classes on scroll
  disableMutationObserver: false, // disables automatic mutations' detections (advanced)
  debounceDelay: 50, // the delay on debounce used while resizing window (advanced)
  throttleDelay: 99, // the delay on throttle used while scrolling the page (advanced)


  // Settings that can be overridden on per-element basis, by `data-aos-*` attributes:
  offset: 120, // offset (in px) from the original trigger point
  delay: 0, // values from 0 to 3000, with step 50ms
  duration: 400, // values from 0 to 3000, with step 50ms
  easing: 'ease', // default easing for AOS animations
  once: true, // whether animation should happen only once - while scrolling down
  mirror: false, // whether elements should animate out while scrolling past them
  anchorPlacement: 'top-bottom', // defines which position of the element regarding to window should trigger the animation
});


export default {
  name: 'LoginPage',
  data() {
    return {}
  },
  components: {},
  methods: {
    async loginWithGoogle() {
      const result = await FirebaseService.loginWithGoogle()
      this.$store.state.accessToken = result.credential.accessToken
      this.$store.state.user = result.user
    }
  },
  mounted() {
    console.log(this.$store.state)
  }
}
</script>

<style></style>
