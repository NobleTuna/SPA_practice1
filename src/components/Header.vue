<template>
<v-toolbar fixed color="orange" dark scroll-off-screen scroll-target="#scrolling-techniques">
  <v-toolbar-side-icon>
    <v-icon>apps</v-icon>
  </v-toolbar-side-icon>
  <v-toolbar-title>Tuna's Blog</v-toolbar-title>

  <v-spacer></v-spacer>

  <v-btn icon>
    <router-link to="/" tag="none">
      <v-icon>home</v-icon>
    </router-link>
  </v-btn>
</v-toolbar>
</template>

<style>
.text-white {
  color: white;
}
</style>
