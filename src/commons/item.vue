<template>
  <div class="item">
    <p>{{ newi.title }}</p>
    <div class="img-box">
      <img src="../assets/top.jpg" />
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
  }
  img{
    width:.8rem;
    height: .65rem;
    vertical-align: top;
  }
</style>
