<template lang='pug'>
.main
  .left
    #logo1
      p.fas.fa-lungs
    #title
      p Pneumonia Classification
    #logo2
      p.fas.fa-lungs-virus
</template>


<script lang='ts'>
import {defineComponent} from 'vue'
export default defineComponent({

})
</script>


<style lang='stylus' scoped>
.main
  .left
    display flex
    width 350px
    text-align center
    align-items center
    margin 3px
    #logo1
      font-size 30px
      margin 0 20px
      color #339933
    #title
      font-weight bold
      font-size 30px
      line-height 100%
    #logo2
      font-size 30px
      margin 0 20px
      color red
</style>