<template>
  <div>
    <ImgBanner imgSrc="https://source.unsplash.com/random" data-aos="fade-down">
      <div style="line-height:1.2em; font-size:8vw;" slot="text">Portfolio</div>
    </ImgBanner>
    <v-container>

      <!-- Portfolio -->
      <v-layout>
        <v-flex xs12 data-aos="fade-right">
          <PortfolioList :limits="6" :load-more="true"></PortfolioList>
        </v-flex>
      </v-layout>

    </v-container>
  </div>
</template>

<script>
import ImgBanner from '../components/ImgBanner'
import PortfolioList from '../components/PortfolioList'

export default {
	name: 'PortfolioPage',
	components: {
		ImgBanner,
		PortfolioList,
	},
}
</script>

<style></style>
