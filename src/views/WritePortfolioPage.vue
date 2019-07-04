<template>
<div>
  <ImgBanner imgSrc="https://source.unsplash.com/random">
    <div style="line-height:1.2em;font-size:8vw;" slot="text">Write Portfolio</div>
  </ImgBanner>
  <v-container>

    <!-- Portfolio -->
    <v-layout>
      <v-flex xs12>
        <WritePortfolio></WritePortfolio>
      </v-flex>
    </v-layout>

  </v-container>
</div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import WritePortfolio from '../components/WritePortfolio'
export default {
  name: 'PortfolioPage',
  components: {
    ImgBanner,
    WritePortfolio,
  },
}
</script>
