<template>
<div class="py-3">
  <v-layout>
    <v-flex xs10>
      <h1>Portfolio write</h1>

      <v-form ref="form" v-model="valid" lazy-validation>
        <v-container>

          <!-- 타이틀 입력 폼 -->
          <v-flex px10 py10>
            <v-text-field v-model="title" :counter="30" :rules="titleRules" label="제목" required>
            </v-text-field>
          </v-flex>

          <!-- 바디 입력 폼 -->
          <v-flex px10 py10>
            <MarkdownEditor v-on:sendBody="getBody"></MarkdownEditor>
          </v-flex>

          <!-- 이미지 업로드 입력 폼 -->
          <v-flex>
            <v-container fluid>
              <v-flex xs12 class="text-xs-center text-sm-center text-md-center text-lg-center">
                <img :src="imageUrl" height="150" v-if="imageUrl" />
                <v-text-field label="Select Image" @click='pickFile' v-model='imageName' prepend-icon='attach_file'></v-text-field>
                <input type="file" style="display: none" ref="image" accept="image/*" @change="onFilePicked">
              </v-flex>
            </v-container>
          </v-flex>
          <v-flex px10 py10>
            <v-btn color="warning" dark @click.stop="submit()">Submit</v-btn>
          </v-flex>
        </v-container>
      </v-form>
    </v-flex>
  </v-layout>
</div>
</template>

<script>
import MarkdownEditor from '../components/MarkdownEditor'
import FirebaseService from '@/services/FirebaseService'

export default {
  data: () => ({
    valid: true,
    title: '',
    titleRules: [
      v => !!v || '제목을 입력해주세요!',
      v => (v && v.length <= 30) || '제목은 30자 이내로 입력해주세요!'
    ],
    imageName: '',
    imageUrl: '',
    imageFile: '',
    body: ''
  }),
  name: '',
  methods: {
    getBody(msg) {
      this.body = msg;
    },

    pickFile() {
      this.$refs.image.click()
    },

    onFilePicked(e) {
      const files = e.target.files
      if (files[0] !== undefined) {
        this.imageName = files[0].name
        if (this.imageName.lastIndexOf('.') <= 0) {
          return
        }
        const fr = new FileReader()
        fr.readAsDataURL(files[0])
        fr.addEventListener('load', () => {
          this.imageUrl = fr.result
          this.imageFile = files[0] // this is an image file that can be sent to server...
        })
      } else {
        this.imageName = ''
        this.imageFile = ''
        this.imageUrl = ''
      }
      // console.log("imgfile :" + this.imageFile);
      // console.log("imgurl : " + this.imageUrl);
      // console.log("imgName : " + this.imageName);
    },

    reset() {
      this.$refs.form.reset()
    },

    resetValidation() {
      this.$refs.form.resetValidation()
    },
    submit() {
      FirebaseService.postPortfolio(this.title,this.body, this.imageUrl);
    }
  },
  components: {
    MarkdownEditor
  }
}
</script>

<style>

</style>
