<template>
<v-container>
  <v-toolbar fixed color="orange" dark scroll-off-screen scroll-target="#scrolling-techniques">
    <v-toolbar-side-icon @click.stop="drawer = !drawer">
      <v-icon>list</v-icon>
    </v-toolbar-side-icon>

    <v-toolbar-title>Tuna's Blog</v-toolbar-title>

    <v-spacer></v-spacer>

    <v-btn icon>
      <router-link to="/" tag="none">
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
      <router-link :to="{ name: 'post', params: {} }" tag="none" class="hover-effect">
        <v-list-tile>
          <!-- <v-list-tile v-for="item in items" :key="item.title" @click=""> -->
          <v-list-tile-action>
            <v-icon>fa-edit</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Post</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </router-link>
      <router-link :to="{ name: 'portfolio', params: {} }" tag="none" class="hover-effect">
        <v-list-tile>
          <v-list-tile-action>
            <v-icon>folder_open</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Portfolio</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </router-link>
      <router-link :to="{ name: 'login', params: {} }" tag="none" class="hover-effect">
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
.hover-effect:hover{
  cursor:pointer;
  color:orange;
}
</style>

<script>
export default {
  data() {
    return {
      drawer: null,
      items: [{}]
    }
  }
}
</script>
