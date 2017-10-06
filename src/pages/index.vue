<template>
  <div class="index">
    <topNav></topNav>
    <lunbo></lunbo>
    <list :news='news'></list> 
  </div>
</template>

<script>
import nav from '@/commons/nav'
import banner from '@/commons/banner'
import list from '@/commons/list'
export default {
  components: {
    topNav: nav,
    lunbo: banner,
    list: list
  },
  data () {
    return {
      news: ''
    }
  },
  methods: {
    getData () {
      this.$ajax.get('https://zhihu-daily.leanapp.cn/api/v1/last-stories').then(news => {
        this.news = news.data.STORIES.stories
        console.log(this.news)
        return news
      }, news => {
        console.log('数据加载失败')
      })
    }
  },
  mounted () {
    this.getData()
  }
}
</script>

<style scoped>
</style>
