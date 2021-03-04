<template lang='pug'>
.main
  #hide
    img#menubar(src="@/assets/menubar.png")
  #header
    //- #logo
    //-   p.fas.fa-lungs
    #title
      p Pneumonia Classification
    //- #logo
    //-   p.fas.fa-lungs-virus
  #middle
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
  font-family Arial Narrow, sans-serif
  height 100%
  #hide
    #menubar
      width 50px
      height auto
      margin 10px 10px 0 0
      float right
      cursor pointer
      transition 0.1s ease
      &:hover
        transform scale(1.1)
  #header
    display flex
    width 350px
    text-align center
    align-items center
    #logo
      font-size 30px
      margin 0 20px
      color #339933
    #title
      font-weight bold
      font-size 50px
      line-height 100%
  #middle
    height 70%
    #elements
      display inline-block
      width 100%
      position relative
      top 50%
      transform translateY(-80%)
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
          font-size 22px
  #social-media
    height 10%
    display flex
    justify-content space-between
    margin 5px 60px
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
      text-decoration none
      &:hover
        box-shadow 0 5px 5px -3px rgba(0,0,0,0.2),
        0 8px 10px 1px rgba(0,0,0,0.14),
        0 3px 14px 2px rgba(0,0,0,0.12)
        
        

</style>