<template lang='pug'>
.main
  #hide
    img#menubar(src="@/assets/menubar.png"
    @click="hideSidebar()")
  #header
      img#logo(src="@/assets/pneumonia-logo.png"
      @click="goHome()")
      a#title(href="/")
        p Pneumonia Classification
  #middle
    #elements
      a#element(v-for="(element, index) in elements"
      :key="index" :href="elements[index].toLowerCase()")
        p(v-bind:class="fontawesomes[index]")
        | {{ element }}
  #social-media
    a.fab.fa-facebook#social(href="https://www.facebook.com/" target="_blank")
    a.fab.fa-github#social(href="https://github.com/you0522/Chest_X-ray_Pneumonia_Classification" target="_blank")
    a.fab.fa-gitlab#social(href="https://gitlab.com/sebbyu/Chest_X-ray_Pneumonia_Classification" target="_blank")
</template>


<script lang='ts'>
import {defineComponent} from 'vue'
export default defineComponent({
  props: {
    hideSidebar: {
      type: Function
    },
  },
  data() {
    return {
      elements: [
        "About",
        "Classification",
        "Help",
      ],
      fontawesomes: [
        'fas fa-address-card',
        'fas fa-lungs-virus',
        'fas fa-question-circle',
      ]
    }
  },
  methods: {
    goHome() {
      document.location.href="/"
    }
  }
})
</script>


<style lang='stylus' scoped>
.main
  font-family Arial Narrow, sans-serif
  height 100%
  #hide
    height 30px
    #menubar
      width 30px
      height atuo
      float right
      cursor pointer
      transition 0.1s ease
      &:hover
        transform scale(1.1)
  #header
    width 350px
    position relative
    left 50%
    transform translateX(-50%)
    #logo
      width 330px
      height auto
      margin 50px 0 0 0
      cursor pointer
      transition 0.1s ease-out
      &:hover
        transform scale(1.1)
    #title
      font-weight bold
      font-size 35px
      line-height 100%
      text-decoration none
      color black
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
        text-decoration none
        align-items center 
        text-align center
        color black
        &:hover
          background-color #f2f2f2
          p
            color #ff6666
        p
          display flex
          justify-content center
          margin 10px 10px
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
      transition box-shadow 100ms cubic-bezier(0,0,0.2,1)
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
        color #ff6666
</style>