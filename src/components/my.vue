<template>
    <div>
      <div class="footer"></div>
        <ul class="head-box-con">
          <el-button type="primary" icon="search" @click="submitForm">搜索</el-button>
          <img src="../../src/assets/logo.png" alt="">
        </ul>

        <li v-for="item in pros" class="list" style="border:1px solid #ccc">
            <h1>{{item.title}}</h1>
            <h3>{{item.recommendation_id}}</h3>
        </li>
    </div>
</template>

<script>

import Axios from 'axios'
export default {
  name: 'footer',
  data () {
    return {
      pros:[{
        "recommendation_id": 3820,
        "status": 1,
        "type": "boards",
        "seq": 19,
        "board_id": 28749828,
        "user_id": 18229647,
        "title": "〖 渐变海报〗",
        "description": "C4D渐变海报 拼贴渐变海报 朋克蒸汽波渐变海报",
        "category_id": "design",
        "pin_count": 385,
        "follow_count": 4377,
        "like_count": 139,
        "created_at": 1458669198,
        "updated_at": 1495504883,
        "deleting": 0,
        "is_private": 0,
        "user": {
          "username": "明仇",
          "urlname": "bsmyisb9o5",
          "pin_count": 41691,
          "follow_count": 9172,
          "user_id": 18229647
        }
      }]
    }
  },
  created: function () {
    var self=this;
    this.$ajax.get('http://localhost:8080/static/test2.json')
      .then(function(response) {
//          self.pros.push(response.data)
//          console.log(response.data);
//          var serdatt=response.data
//          self.$set("pros", serdatt);
       self.pros = response.data
        console.log(self.pros);

      });
    console.log("建立");
  },
  methods: {
    submitForm () {
      var self=this;
      this.$ajax.get('http://localhost:8080/static/test2.json')
        .then(function(response) {
//          self.pros.push(response.data)
//          console.log(response.data);
//          var serdatt=response.data
//          self.$set("pros", serdatt);
//          self.pros = response.data
          console.log(self.pros);

        });

//      this.$ajax({
//        method: 'get',
//        dataType:"json",
//        url: 'http://localhost:8080/static/test2.json'
//
//      }).then(function (response) {
//        console.log(response)
//
//
//      }).catch(function (error) {
////        console.log(error);
//      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer{background-color:#5fd3ca; width:100%; height:60px;position:fixed; bottom:0px;}
</style>
