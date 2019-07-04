<template>
<v-app>
  <go-top></go-top>
  <Header></Header>
  <Alert></Alert>
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
import Alert from './components/BrowserAlert'


export default {
  name: 'App',
  components: {
    Header: Header,
    Footer: Footer,
    GoTop: GoTop,
    Alert: Alert,
  },
  store,
  data() {
    return {
      //
    }
  }
}
</script>
