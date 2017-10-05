<template>
  <div class="nav" @click='hide'>
    <i class="fa fa-bars" aria-hidden="true"></i>
    <span>首页</span>
    <i class="fa fa-ellipsis-v" @click='showa'></i>
    <i  class="fa fa-bell"></i>
    <div v-show='show' class="set">
      <p>夜间模式</p>
      <p>设置选项</p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      show: false
    }
  },
  methods: {
    showa: function (e) {
      if (e && e.stopPropagation) {
        // 非IE浏览器
        event.stopPropagation()
        // DOM:获取触发事件的对象
        // e.target;
      } else {
        // IE浏览器
        window.event.cancelBubble = true
        // IE:获取触发事件的对象
        // e.srcElement
      }
      this.show = !this.show
      console.log(this.show)
    },
    hide: function () {
      this.show = false
      console.log(this.show)
    }
  }
}
</script>

<style scoped>
  .nav{
    position: relative;
    padding:.1rem .2rem;
    background: #008bed;
    color: #fff;
    font-size: .2rem;
  }
  span{
    margin-left: .2rem;
  }
  .fa-ellipsis-v,.fa-bell{
    float: right;
    margin-top: .04rem;
    margin-left: .2rem;
  }
  .set{
    position: absolute;
    top: .03rem;
    right: .03rem;
    z-index: 1;
    width:50%;
    border-radius: 3px;
    background: #fff;
    color: #000;
    overflow: hidden;
  }
  p{
    width: 100%;
    padding:.1rem;
    font-size: .16rem
  }
  p:hover{
    background: #ccc;
  }
</style>
