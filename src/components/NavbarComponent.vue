<template lang='pug'>
.main
  #hide
    button.fas.fa-minus-square#button(
      @click="hide_Menu()"
    )
  #header
    #logo
      p.fas.fa-lungs
    #title
      p Pneumonia Classification
    #logo
      p.fas.fa-lungs-virus
  #elements
    #element(v-for="(element, index) in elements"
    :key="index")
      p(v-bind:class="fontawesomes[index]")
      p {{ element }}
  #social-media
    a.fab.fa-facebook#social(href="https://www.facebook.com/" target="_blank")
    a.fab.fa-github#social(href="https://github.com/sebbyu/Chest-Xray-Pneumonia-Classification" target="_blank")
    a.fab.fa-gitlab#social(href="https://gitlab.com/sebbyu/Chest_X-ray_Pneumonia_Classification" target="_blank")

</template>


<script lang='ts'>
import {defineComponent} from 'vue'
export default defineComponent({
  setup() {
    const elements: string[] = [];
    const fontawesomes: string[] = [
      'fas fa-home',
      'fas fa-address-card',
      'fas fa-question-circle',
      'fas fa-envelope',
    ]
    elements.push('home');
    elements.push('About');
    elements.push('Help');
    elements.push('Contact');
    return {elements,fontawesomes,}
  }
})
</script>


<style lang='stylus' scoped>
.main
  font-family Noto Sans, sans-serif
  height 100%
  #hide
    #button
      position absolute
      right 0
      border none
      background-color white
      font-size 25px
      transition 0.15s ease
      &:hover
        background-color #f2f2f2
        transform scale(1.2)
  #header
    display flex
    height 150px
    width 100%
    text-align center
    align-items center
    margin 3px
    #logo
      font-size 30px
      color red
      margin 0 20px
    #title
      font-weight bold
      font-size 30px
      line-height 100%
  #elements
    height 70%
    display inline-block
    width 100%
    #element
      display flex
      cursor pointer
      padding 20px 5px
      margin-left 5px
      &:hover
        background-color #f2f2f2
      p
        display flex
        justify-content center
        align-items center 
        text-align center
        margin 10px 3px
        font-size 20px
  #social-media
    height 10%
    display flex
    justify-content space-between
    margin 5px 70px
    #social
      font-size 25px
      border solid 1px #ccc
      color rgba(0,0,0,0.87)
      background #fff
      border-radius 50%
      transition box-shadow 200ms cubic-bezier(0,0,0.2,1)
      box-shadow 0 3px 1px -2px rgba(0,0,0,0.2),
      0 2px 2px 0 rgba(0,0,0,0.14),
      0 1px 5px 0 rgba(0,0,0,0.12)
      width 50px
      height 50px
      display flex
      justify-content center
      align-items center
      cursor pointer
      background-color #f2f2f2
      &:hover
        box-shadow 0 5px 5px -3px rgba(0,0,0,0.2),
        0 8px 10px 1px rgba(0,0,0,0.14),
        0 3px 14px 2px rgba(0,0,0,0.12)

</style>