<template>
  <div class="index">
    <topNav></topNav>
    <lunbo :news='news'></lunbo>
    <list :news='news'></list> 
    <list v-for='before in more' :news='before'></list>
  </div>
</template>
<script>
import nav from '@/commons/nav'
import lunbo from '@/commons/lunbo'
import list from '@/commons/list'
export default {
  components: {
    topNav: nav,
    lunbo: lunbo,
    list: list
  },
  data () {
    return {
      news: '',
      more: []
    }
  },
  methods: {
    getData () {
      this.$ajax.get('https://zhihu-daily.leanapp.cn/api/v1/last-stories').then(news => {
        this.news = news.data.STORIES
        console.log(this.news)
      }, news => {
        console.log('数据加载失败')
      })
    },
    dataBefore (day) {
      this.$ajax.get('/api/4/news/before/' + day).then(more => {
        this.more.push(more.data)
        console.log(this.more)
      }, more => {
        console.log('数据加载失败')
      })
    }
  },
  mounted () {
    this.getData()
    var _this = this
    var curTime = new Date()
    var boo = true
    window.onscroll = function () {
      if (boo === true) {
        var scrollTop = Number(document.body.scrollTop || document.documentElement.scrollTop)
        var offsetHeight = document.body.offsetHeight
        var clientHeight = document.documentElement.clientHeight
        if ((offsetHeight - clientHeight) - scrollTop <= 1) {
          boo = false
          var date = curTime.getDate()
          if (date < 10) {
            date = 0 + '' + date
          }
          var month = curTime.getMonth() + 1
          if (month < 10) {
            month = 0 + '' + month
          }
          var year = curTime.getYear() + 1900
          var day = '' + year + month + date
          _this.dataBefore(day)
          curTime = new Date(curTime - 86400 * 1000)
        }
      }
      setTimeout(function () { boo = true }, 1000)
    }
  }
}
</script>

<style scoped>
</style>
