<template lang='pug'>
.main
  .top
    p#title Pneumonia Classification
  .bottom
    .wrap
      .box
        .beforedropped(v-if='!image')
          label.btn
            | SELECT OR DROP AN IMAGE
            input.input(type="file" name="image" @change="onChange")
        .afterdropped(v-else)
          img.img(:src="image" alt="")
          button.btn(@click="removeFile") REMOVE


</template>

<script lang='js'>
import {defineComponent} from 'vue'
export default defineComponent({
  data() {
    return {
      image: require("@/assets/pneumonia-logo.png"),
    }
  },
  methods: {
    onDrop: function(e) {
      e.stopPropagation();
      e.preventDefault();
      const files = e.dataTransfer.files;
      this.createFile(files[0]);
    },
    onChange(e) {
      const files = e.target.files;
      this.createFile(files[0]);
    },
    createFile(file) {
      if (!file.type.match('image.*')) {
        alert('Select an image');
        return;
      }
      const img = new Image();
      const reader = new FileReader();
      // const vm = this;

      reader.onload = function(e) {
        this.image = e.target.result;
      }
      reader.readAsDataURL(file);
    },
    removeFile() {
      this.image = '';
    }
  }
})
</script>

<style lang='stylus' scoped>
.main
  .top
    #title
      font-family OCR A Std, monospace
      font-size 60px
      text-align center
      font-weight bold
      padding 30px
  .bottom
    display flex
    justify-content center
    .wrap
      .box
        text-align center
        border 5px dashed #ff6666
        height 500px
        width 500px
        .beforedropped
          height 100%
          width 100%
          .btn
            background-color: #d3394c;
            border: 0;
            color: #fff;
            cursor: pointer;
            display: inline-block;
            font-weight: bold;
            padding: 15px 35px;
            position: relative;
            top 50%
            transform translateY(-50%)
            &:hover
              background-color #722040
            .input[type="file"]
              position absolute
              opacity 0
              z-index -1
        .afterdropped
          .img
            border 1px solid #f6f6f6
            display inline-block
            height 490px
            max-height 100%
            max-width 100%
            width 490px
          .btn
            margin 10px
            background-color: #d3394c;
            border: 0;
            color: #fff;
            cursor: pointer;
            display: inline-block;
            font-weight: bold;
            padding: 15px 35px;
            &:hover
              background-color #722040
</style>