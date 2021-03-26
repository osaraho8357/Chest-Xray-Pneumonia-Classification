<template lang='pug'>
.main
  .background
    ComingSoonComponent
</template>


<script lang='ts'>
import {defineComponent} from 'vue'
import ComingSoonComponent from '@/components/ComingSoonComponent.vue'
export default defineComponent({
  name: "HomeComponent",
  components: {
    ComingSoonComponent,
  },
})
</script>


<style lang='stylus' scoped>
.main
  .background
    background linear-gradient(rgba(0,0,0,0.5),(rgba(0,0,0,0.7))), url("../assets/background.jpg") repeat
    height 100vh
    min-width calc(100vw - 380px)
    background-size 100% 100%
</style>