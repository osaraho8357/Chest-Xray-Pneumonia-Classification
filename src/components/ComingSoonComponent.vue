<template lang='pug'>
.main
  .frame
    p#title COMING SOON
    p#subtitle SITE UNDER CONSTRUCTION
    .progress
      .progress-bar.progress-bar-striped.progress-bar-animated(
        value="50" max="100"
      ) 50%
    p#paragraph Meanwhile, please visit my 
      a#link(href="https://gitlab.com/sebbyu/Chest_X-ray_Pneumonia_Classification" target="_blank") gitlab
      |  page and check out my work!
</template>


<script lang='ts'>
import {defineComponent} from 'vue'
export default defineComponent({

})
</script>


<style lang='stylus' scoped>
.main
  height 100vh
  display flex
  justify-content center
  align-items center
  .frame
    width 500px
    text-align center
    #title
      font-size 100px
      color white
      text-align center
      line-height 95%
      font-weight bold
    #subtitle
      color white
      font-weight 400
    .progress
      height 25px
      .progress-bar
        color black
        background-color #ff6699
        width 50%
        height 100%
        font-weight bold
        font-size 20px
    #paragraph
      margin-top 10px
      color white
      font-weight 400
      #link
        font-weight bold 
        color white
        text-decoration none
</style>