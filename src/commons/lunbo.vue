<template>
  <div class="view" v-on:touchstart = "">
    <ul  id="box">
      <li v-for="(newi,key) in news.top_stories" :newi='newi'>
        <banner :newi='newi'></banner>
      </li>
    </ul>
    
  </div>
</template>

<script>
import banner from '@/commons/banner'
export default {
  props: ['news'],
  components: {
    banner: banner
  },
  methods: {
    lunbo () {
      setInterval(function () {
        var ul = document.getElementById('box')
        var margin = parseInt(ul.style.marginLeft)
        if (margin > -400) {
          margin = margin - 100 + '%'
          ul.style.marginLeft = margin
        } else {
          ul.style.marginLeft = 0
        }
      }, 5000)
    }
  },
  mounted () {
    this.lunbo()
  }
}
</script>

<style scoped>
  .view{
    width:100%;
    overflow: hidden;
  }
  #box{
    width:500%;
    transition: .5s;
  }
  .box:after{
    content:"";
    display:block;
    clear:both;
  }
  li{
    width:20%;
    float:left;
  }
</style>
