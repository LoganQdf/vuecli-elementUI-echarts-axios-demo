<template>
  <div>
      <div class="navbar">
          <ul class="navbar-box-con">
            <router-link to="/home/nav1">仪表盘</router-link>
            <router-link to="/home/nav2">分析</router-link>
            <router-link to="/home/nav3">预警中心</router-link>
            <router-link to="/home/nav4">词条管理</router-link>
          </ul>
      </div>
    <transition name="fade">
      <router-view class="children-view"></router-view>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'navbar',
  data () {
    return {
      pro:""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .navbar{ position:fixed;left:0px; top:70px;height:100%; width:100px;background-color:#000;}
  .navbar-box-con{}
  .navbar-box-con a{ height:72px;display:block; color:#fff;padding-top:40px;}
  .navbar-box-con .router-link-active{background-color:#00d2ff}
  .children-view{margin-left:100px;}

  .fade-enter{ opacity:0; margin-left:200px }	  /*初始状态*/
  .fade-enter-active{ transition: all .7s}	/*变化成什么样 --当元素出来(显示)*/
  .fade-leve-active{  transition: all .7s}	/*变化成什么样 --当元素离开(隐藏)*/
</style>
