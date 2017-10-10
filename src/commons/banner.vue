<template>
  <div class="banner">
    <img :src='newi.image' />
    <p>{{ newi.title }}</p>
    <span v-if='newi.author'>{{ newi.author }}</span>
  </div>
</template>

<script>
export default {
  props: ['newi']
}
</script>

<style scoped>
  .banner{
    position: relative;
    width: 100%;
    height:3rem;
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