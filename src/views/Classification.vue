<template lang='pug'>
.comonent
  .classification
    ClassificationComponent
</template>


<script lang='ts'>
import {defineComponent} from 'vue'
import ClassificationComponent from '@/components/ClassificationComponent.vue'
export default defineComponent({
  components: {
    ClassificationComponent,
  }
})
</script>


<style lang='stylus' scoped>

</style>