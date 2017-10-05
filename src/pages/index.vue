<template>
  <div class="index">
    <lunbo></lunbo>
    <list :news='news'></list> 
  </div>
</template>

<script>
import banner from '@/commons/banner'
import list from '@/commons/list'
export default {
  components: {
    lunbo: banner,
    list: list
  },
  data () {
    return {
      news: [
        {
          title: 'sdahf'
        },
        {
          title: 'sajnsc'
        },
        {
          title: 'sdaaahf'
        },
        {
          title: 'sajaansc'
        },
        {
          title: 'sdaahf'
        },
        {
          title: 'sajansc'
        }
      ]
    }
  }
}
</script>

<style scoped>
</style>
