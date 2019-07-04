<template>
<v-container>
  <v-toolbar fixed color="orange" dark scroll-off-screen scroll-target="#scrolling-techniques">
    <v-toolbar-side-icon @click.stop="drawer = !drawer" class="hidden-md-and-up">
      <v-icon>list</v-icon>
    </v-toolbar-side-icon>

    <v-toolbar-title>Tuna's Blog</v-toolbar-title>

    <v-spacer></v-spacer>

    <v-btn icon class="hidden-sm-only">
      <router-link to="post" tag="span">
        <v-icon>receipt</v-icon>
      </router-link>
    </v-btn>

    <v-btn icon class="hidden-sm-only">
      <router-link to="portfolio" tag="span">
        <v-icon>folder_open</v-icon>
      </router-link>
    </v-btn>

    <v-btn icon class="hidden-sm-only" x>
      <router-link to="login" tag="span">
        <v-icon>account_circle</v-icon>
      </router-link>
    </v-btn>

    <v-btn icon>
      <v-icon @click="favorite">bookmark</v-icon>
    </v-btn>

    <v-btn icon>
      <router-link to="/" tag="span">
        <v-icon>home</v-icon>
      </router-link>
    </v-btn>

  </v-toolbar>

  <v-navigation-drawer v-model="drawer" fixed temporary>
    <v-list class="pa-1">
      <v-list-tile avatar>
        <v-list-tile-avatar>
          <img src="../assets/logo.png">
        </v-list-tile-avatar>

        <v-list-tile-content>
          <v-list-tile-title>NobleTuna</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>

    <v-list class="pt-0" dense>
      <v-divider></v-divider>
      <router-link to="post" class="hover-effect" tag="span">
        <v-list-tile>
          <!-- <v-list-tile v-for="item in items" :key="item.title" @click=""> -->
          <v-list-tile-action>
            <v-icon>receipt</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Post</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </router-link>
      <router-link to="portfolio" class="hover-effect" tag="span">
        <v-list-tile>
          <v-list-tile-action>
            <v-icon>folder_open</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Portfolio</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </router-link>
      <router-link to="login" class="hover-effect" tag="span">
        <v-list-tile>
          <v-list-tile-action>
            <v-icon>account_circle</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Login</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </router-link>
    </v-list>
  </v-navigation-drawer>
</v-container>
</template>

<style>
.text-white {
  color: white;
}

.hover-effect:hover {
  cursor: pointer;
  color: orange;
}
</style>


<script>
export default {
  name: 'Header',
  components: {},
  data() {
    return {
      drawer: null,
      items: [{}]
    }
  },
  methods: {
    favorite() {
      var bookmarkURL = window.location.href;
      var bookmarkTitle = document.title;
      var triggerDefault = false;
      if (window.sidebar && window.sidebar
        .addPanel) { // Firefox version < 23
        window.sidebar.addPanel(bookmarkTitle, bookmarkURL, '');
      } else if ((window.sidebar && (navigator.userAgent.toLowerCase().indexOf('firefox') > -1)) || (window.opera && window
          .print)) { // Firefox version >= 23 and Opera Hotlist
        var $this = $(this);
        $this.attr('href', bookmarkURL);
        $this.attr('title', bookmarkTitle);
        $this.attr('rel', 'sidebar');
        $this.off(e);
        triggerDefault = true;
      } else if (window.external && ('AddFavorite' in window
          .external)) { // IE Favorite
        window.external.AddFavorite(bookmarkURL, bookmarkTitle);
      } else { // WebKit - Safari/Chrome
        alert((navigator.userAgent.toLowerCase().indexOf('mac') != -1 ? 'Cmd' : 'Ctrl') + '+D 키를 눌러 즐겨찾기에 등록하실 수 있습니다.');
      }
      return triggerDefault;
    }
  }
}
</script>
