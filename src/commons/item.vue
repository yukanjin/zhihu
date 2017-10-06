<template>
  <div class="item">
    <p>{{ newi.title }}</p>
    <div class="img-box">
      <img :src='newi.images[0]' />
    </div>
  </div>
</template>

<script>

export default {
  props: ['newi']
}
</script>

<style scoped>
  .item{
    background: #fff;
    border-radius: 5px;
    margin: .05rem;
    padding: .1rem;
  }
  .item:after{
    content: "";
    display: block;
    clear: both;
  }
  p{
    float:left;
    font-size: .16rem;
    width:2rem;
  }
  .img-box{
    float:right;
    background: gray;
    width:.8rem;
    height:.65rem;
    font-size: 0;
  }
  img{
    width:100%;
    height: 100%;
    vertical-align: top;
  }
</style>
