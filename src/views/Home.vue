<template lang="pug">
.home
  .navbarcomponent
    NavbarComponent
  .homecomponent
    HomeComponent
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HomeComponent from '@/components/HomeComponent.vue'; // @ is an alias to /src
import NavbarComponent from '@/components/NavbarComponent.vue';

export default defineComponent({
  name: 'Home',
  components: {
    HomeComponent,
    NavbarComponent,
  },
});
</script>

<style lang='stylus' scoped>
.home
  margin 0
  padding 0
  width 100%
  height 100%
  display flex
  .navbarcomponent
    height 100vh
    width 380px
    position relative
    box-shadow 0 3px 1px -2px rgba(0,0,0.2,1),
    0 2px 2px 0 rgba(0,0,0,0.14),
    0 1px 5px 0 rgba(0,0,0,0.12)
  .homecomponent
    height 100vh
</style>