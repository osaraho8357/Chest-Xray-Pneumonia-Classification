<template lang="pug">
.home
  .left
    .sidenavbarcomponent
      SideNavBarComponent#sidebar(
        :hideSidebar="hideSidebar"
      )
  .right
    .homecomponent
      HomeComponent#home
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HomeComponent from '@/components/HomeComponent.vue'; // @ is an alias to /src
import SideNavBarComponent from '@/components/SideNavBarComponent.vue';
import TopNavbarComponent from '@/components/TopNavBarComponent.vue'

export default defineComponent({
  name: 'Home',
  components: {
    HomeComponent,
    SideNavBarComponent,
    TopNavbarComponent,
  },
  methods: {
    hideSidebar() {
      const sidebarComponent = document.getElementsByClassName("sidenavbarcomponent")[0]
      const sidebar = document.getElementById("sidebar")
      const a = sidebar?.cloneNode(true)
      const img: any = document.createElement('img')
      img.src = require("@/assets/menubar.png")
      img.style.width = "30px"
      img.style.cursor = "pointer"
      img.id = 'img';
      img.addEventListener('click', function() {
        sidebarComponent.appendChild(sidebar!)
        sidebarComponent.removeChild(img!);
      })
      if (sidebar) {
        sidebarComponent.removeChild(sidebar!);
        sidebarComponent.appendChild(img);
      } 
    },
  }
});
</script>
#header
#middle
#social-media

<style lang='stylus' scoped>
.home
  width 100%
  height 100%
  display flex
  .left
    .sidenavbarcomponent
      #sidebar
        height 100vh
        width 380px
        position relative
        box-shadow 0 3px 1px -2px rgba(0,0,0.2,1),
        0 2px 2px 0 rgba(0,0,0,0.14),
        0 1px 5px 0 rgba(0,0,0,0.12)
  // .right
  //   .homecomponent
  //     height 1000px
</style>