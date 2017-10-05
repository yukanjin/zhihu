<template>
  <div class="banner">
    <img src="../assets/top.jpg" />
    <p>{{ news.title }}</p>
    <span v-if='news.author != ""'>{{ news.author }}</span>
  </div>
</template>

<script>
export default {
  data () {
    return {
      news: {
        title: '新闻标题',
        author: '作者'
      }
    }
  }
}
</script>

<style scoped>
  .banner{
    position: relative;
    width: 100%;
    margin-bottom: -25px;
  }
  img{
    width:100%;
  }
  p,span{
    position: absolute;
    bottom:0;
    transform: translateY(-25px);
  }
  p{
    color:#fff;
    font-size: .2rem;
    padding:22px 20px;
  }
  span{
    right: .05rem;
    font-size: .14rem;
    color:#dedede;
    padding:.02rem;
  }
</style>