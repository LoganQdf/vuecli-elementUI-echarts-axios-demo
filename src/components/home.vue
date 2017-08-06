<template>
  <div>
    <div class="music"></div>
    <ul class="music-box">
      <router-link to="/home/found">发现</router-link>
      <router-link to="/home/my">我的</router-link>
      <router-link to="/home/found">现在</router-link>
      <router-link to="/home/found">过去</router-link>

    </ul>

    <transition name="">
    <router-view class="children-view"></router-view>
      </transition>
  </div>
</template>

<script>

  export default {
    name: 'list',
    data () {
      return {
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .music{background-color:red; width:100%; height:60px;position:fixed; bottom:0px;}
  .children-view{ width:100%; margin-top:40px;}

  .fold-enter-active {
    animation-name: fold-in;
    animation-duration: .1s;
  }
  .fold-leave-active {
    animation-name: fold-out;
    animation-duration: .1s;
  }
  @keyframes fold-in {
    0% {
      transform: translate3d(0, 100%, 0);
    }
    50% {
      transform: translate3d(0, 50%, 0);
    }
    100% {
      transform: translate3d(0, 0, 0);
    }
  }
  @keyframes fold-out {
    0% {
      transform: translate3d(0, 0, 0);
    }
    50% {
      transform: translate3d(0, 50%, 0);
    }
    100% {
      transform: translate3d(0, 100%, 0);
    }
  }
</style>
