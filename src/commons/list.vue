<template>
  <div class="list">
    <p v-if=" title == '' ">今日热闻</p>
    <p>{{ title }}</p>
    <item v-for="newi in news.stories" :newi='newi'></item>
  </div>
</template>

<script>
import item from '@/commons/item'
export default {
  props: ['news'],
  components: {
    item: item
  },
  data () {
    return {
      title: ''
    }
  },
  methods: {
    getTitle () {
      var date = this.news.date.substring(6, 8)
      var month = this.news.date.substring(4, 6)
      var year = this.news.date.substring(0, 4)
      var day = new Date(year, month - 1, date).getDay()
      switch (day) {
        case 0:
          day = '星期日'
          break
        case 1:
          day = '星期一'
          break
        case 2:
          day = '星期二'
          break
        case 3:
          day = '星期三'
          break
        case 4:
          day = '星期四'
          break
        case 5:
          day = '星期五'
          break
        case 6:
          day = '星期六'
          break
      }
      this.title = month + '月' + date + '日 ' + day
    }
  },
  mounted () {
    this.getTitle()
  }
}
</script>

<style scoped>
  p{
    font-size: .13rem;
    margin:.1rem;
  }
  .list{
    padding-bottom: .02rem;
  }
</style>
