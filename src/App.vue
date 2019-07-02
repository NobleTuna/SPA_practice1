<template>
<v-app>
  <go-top></go-top>
  <Header>
  </Header>
  <v-content>
    <router-view />
  </v-content>
  <Footer></Footer>
</v-app>
</template>
<script>
import store from './store'
import Header from './components/Header'
import Footer from './components/Footer'
import GoTop from '@inotom/vue-go-top';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    GoTop
  },
  store,
  data() {
    return {
      //
    }
  }
}
</script>
