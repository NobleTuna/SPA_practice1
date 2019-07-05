<template>
<!-- About Me -->
<v-layout my-5>
  <v-flex>
    <h2 class="headline mb-3 mobile_center">About Me</h2>
    <p class="mr-4 mobile_center">개발자(예정)인 위영웅입니다.</p>
  </v-flex>
  <v-flex xs4 class="hidden-sm-and-down">
    <v-img :src="getImgUrl('profile.png')" aspect-ratio="1.5" class="borderImg" />
  </v-flex>
</v-layout>
</template>

<script>
import AOS from 'aos';
import 'aos/dist/aos.css';

AOS.init();

export default {
  components: {},
  methods: {
    getImgUrl(img) {
      return require('../assets/' + img)
    }
  },
  data() {
    return {}
  }
}
</script>
