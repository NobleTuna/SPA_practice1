<template>
<v-footer height="40">
  <v-spacer></v-spacer>
  <v-flex>
    &copy; <strong>NobleTuna</strong> {{ new Date().getFullYear() }}
  </v-flex>
</v-footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {}
  }
}
</script>

<style></style>
