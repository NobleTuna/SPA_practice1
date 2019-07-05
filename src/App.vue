<template>
<v-app>
  <go-top />
  <Header />
  <Alert />
  <v-content>
    <router-view />
  </v-content>
  <Footer />
</v-app>
</template>

<script>
import store from './store'
import Header from './components/Header'
import Footer from './components/Footer'
import GoTop from '@inotom/vue-go-top';
import Alert from './components/BrowserAlert'



export default {
  name: 'App',
  components: {
    Header,
    Footer,
    GoTop,
    Alert,
  },
  store,
  data() {
    return {}
  }
}
</script>

<style></style>
