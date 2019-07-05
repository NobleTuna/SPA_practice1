<template>
<div>
  <ImgBanner imgSrc="https://source.unsplash.com/random" data-aos="fade-down">
    <div style="line-height:1.2em; font-size:8vw;" slot="text">자기 개발을 멈추면 죽는다</div>
  </ImgBanner>
  <v-container>

    <AboutMe data-aos="fade-right"></AboutMe>

    <!-- Portfolio -->
    <v-layout my-5 data-aos="fade-left">
      <v-flex xs12>
        <h2 class="headline my-5 text-xs-center">
          <v-btn color="warning" flat large to="portfolio" replace style="font-size:1.2em;text-transform:none;" slot="text">Portfolio</v-btn>
        </h2>
        <PortfolioList></PortfolioList>
      </v-flex>
    </v-layout>

    <!-- Post -->
    <v-layout my-5 data-aos="fade-right">
      <v-flex xs12>
        <h2 class="headline my-5 text-xs-center">
          <v-btn color="warning" flat large to="Post" replace style="font-size:1.2em;text-transform:none;" slot="text">Post</v-btn>
        </h2>
        <PostList :column="2"></PostList>
      </v-flex>
    </v-layout>

    <!-- Github -->
    <v-layout my-5 data-aos="fade-left">
      <v-flex xs12>
        <h2 class="headline my-5 text-xs-center">
          <v-btn color="warning" flat large replace style="font-size:1.2em;text-transform:none;" slot="text">Project</v-btn>
        </h2>
        <RepositoryList></RepositoryList>
      </v-flex>
    </v-layout>
  </v-container>
</div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PortfolioList from '../components/PortfolioList'
import PostList from '../components/PostList'
import RepositoryList from '../components/RepositoryList'
import AboutMe from '../components/AboutMe'

var filter = "win16|win32|win64|mac|macintel";

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
  name: 'HomePage',
  components: {
    AboutMe,
    ImgBanner,
    PortfolioList,
    PostList,
    RepositoryList
  },
  data: function() {
    return {}
  },
  mounted() {},
}
</script>

<style>
@media (max-width:960px) {
  .mobile_center {
    text-align: center;
  }
}

.borderImg {
  border-radius: 100px;
  box-shadow: 5px 5px 20px 5px gray;
}
</style>
