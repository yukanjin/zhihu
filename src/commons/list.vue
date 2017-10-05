<template>
  <div class="list">
    <p>今日热闻</p>
    <item v-for="newi in news" :newi='newi'></item>
  </div>
</template>

<script>
import item from '@/commons/item'
export default {
  props: ['news'],
  components: {
    item: item
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
