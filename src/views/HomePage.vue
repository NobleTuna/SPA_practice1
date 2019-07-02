<template>
<div>
  <ImgBanner imgSrc="https://source.unsplash.com/random">
    <div style="line-height:1.2em;" slot="text">자기 개발을 멈추면 죽는다.</div>
  </ImgBanner>
  <v-container>
    <!-- About Me -->
    <v-layout my-5>
      <v-flex>
        <h2 class="headline mb-3 mobile_center">About Me</h2>
        <p class="mr-4 mobile_center">개발자(예정)인 위영웅입니다.</p>
      </v-flex>
      <v-flex xs4 class="displayNon">
        <v-img :src="getImgUrl('profile.png')" aspect-ratio="1.5" />
      </v-flex>
    </v-layout>

    <!-- Portfolio -->
    <v-layout my-5>
      <v-flex xs12>
        <h2 class="headline my-5 text-xs-center">
          <v-btn flat large :to="{ name: 'portfolio', params: {} }" replace style="font-size:1.2em;text-transform:none;" slot="text">Portfolio</v-btn>
        </h2>
        <PortfolioList></PortfolioList>
      </v-flex>
    </v-layout>

    <!-- Post -->
    <v-layout my-5>
      <v-flex xs12>
        <h2 class="headline my-5 text-xs-center">Post</h2>
        <PostList :column="2"></PostList>
      </v-flex>
    </v-layout>


    <!-- Github -->
    <v-layout my-5>
      <v-flex xs12>
        <h2 class="headline my-5 text-xs-center">Project</h2>
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

var filter = "win16|win32|win64|mac|macintel";

export default {
  name: 'HomePage',
  components: {
    ImgBanner,
    PortfolioList,
    PostList,
    RepositoryList
  },
  data: function() {
    return {}
  },
  mounted() {},
  methods: {
    getImgUrl(img) {
      console.log(img);
      return require('../assets/' + img)
    }
  }
}
</script>

<style>
</style>
