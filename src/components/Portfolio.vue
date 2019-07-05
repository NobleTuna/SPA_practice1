<template>
<v-card>
  <v-img :src="imgSrc" height="200px">
  </v-img>
  <v-card-title primary-title>
    <div>
      <div class="headline title_overflow">{{title}}</div>
      <span class="grey--text body_overflow">

        {{body}}</span>
    </div>
  </v-card-title>
</v-card>
</template>

<script>
export default {
  name: 'Portfolio',
  props: {
    date: {
      type: String
    },
    title: {
      type: String
    },
    body: {
      type: String
    },
    imgSrc: {
      type: String
    },
  },
  data() {
    return {
    }
  }
}
</script>

<style>
.title_overflow {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
  -o-text-overflow: ellipsis;
  -ms-text-overflow: ellipsis;
  -moz-text-overflow: ellipsis
}

.body_overflow {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
  word-wrap: break-word;
}
</style>
