<template>
<div class="py-3">
  <v-layout>
    <v-flex xs10>
      <h1>Portfolio write</h1>

      <v-form>
        <v-container>
          <v-flex px10 py10>
            <v-text-field name="title" label="제목을 입력해주세요." outline></v-text-field>
          </v-flex>
          <v-flex px10 py10>
            <v-textarea outlined name="value" label="마크다운 형식으로 작성해주세요."></v-textarea>
          </v-flex>
          <v-flex px10 py10>
            <v-btn color="warning" dark>제출</v-btn>
          </v-flex>
        </v-container>
      </v-form>


      </form>
    </v-flex>
  </v-layout>
</div>
</template>

<script>
export default {
  name: 'WritePortfolio',
  props: {},
  methods: {},
}
</script>
<style>
</style>
