<template>
  <div class="index">
    <!-- <navbar></navbar> -->
    <lunbo></lunbo>
    <list :news='news'></list> 
  </div>
</template>

<script>
// import nav from '@/commons/nav'
import banner from '@/commons/banner'
import list from '@/commons/list'
export default {
  components: {
    // navbar: nav,
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
