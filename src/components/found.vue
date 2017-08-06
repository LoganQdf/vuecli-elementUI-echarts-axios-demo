<template>
    <div>
        <div>
            <el-carousel indicator-position="outside">
              <el-carousel-item v-for="item in itemms" :key="item">
                <img :src="item.urll" alt="">
                <h3>{{ item.name }}</h3>
                <h2>{{item.urll}}</h2>
              </el-carousel-item>
            </el-carousel>
        </div>
    </div>
</template>

<script>
export default {
  name: 'footer',
  data () {
    return {
      itemms:[{
        name:"王",
        urll:"http://pic1.win4000.com/wallpaper/7/5469a11962625.jpg",
      },
        {
          name:"韩",
          urll:"http://pic1.win4000.com/wallpaper/7/5469a12253f79.jpg",
        }
      ]
    }
   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }

  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
</style>
