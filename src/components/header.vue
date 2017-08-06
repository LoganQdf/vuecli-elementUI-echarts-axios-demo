<template>
    <div>
      <div class="head-top"></div>
      <div class="head-box">
        <ul class="head-box-con">
          <router-link to="/home/nav1">论坛</router-link>
          <router-link to="/list">博客</router-link>
          <router-link to="/music">音乐</router-link>
        </ul>
      </div>
    </div>
</template>

<script>
export default {
  name: 'head',
  data () {
    return {
      pro:""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.head-top{background-color:#5fd3ca; width:100%; height:10px;;}
.head-box{background-color:#f1f1f1; height:60px;}
.head-box-con{ width:1200px; height:100%; margin:0 auto}
.head-box-con li{ width:10%; float:left; font-size:18px; line-height:60px; color:#666;}
.head-box-con a{ width:10%; float:left; height:100%; line-height:60px; text-align:center}
.head-box-con a:hover{ background-color:#00e0e0; color:#fff;}
</style>
