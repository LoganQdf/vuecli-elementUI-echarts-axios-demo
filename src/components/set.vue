<template>
    <div class="set">
      <el-tabs v-model="activeName" @tab-click="handleClick">
        <el-tab-pane label="用户管理" name="first" >
          <h1>用户管理</h1>
          <el-button type="primary" icon="edit" @click="tip"></el-button>
          <el-button type="primary" icon="share" @click="open3"></el-button>
          <el-button type="primary" icon="delete"  @click="dialogVisible = true"></el-button>
          <el-button type="primary" icon="search">搜索</el-button>
          <el-button type="primary">上传<i class="el-icon-upload el-icon--right"></i></el-button>
        </el-tab-pane>


        <el-tab-pane label="配置管理" name="second">
          <h2>配置管理</h2>
          <el-checkbox :indeterminate="isIndeterminate" v-model="checkAll" @change="handleCheckAllChange">全选</el-checkbox>
          <div style="margin: 15px 0;"></div>
          <el-checkbox-group v-model="checkedCities" @change="handleCheckedCitiesChange">
            <el-checkbox v-for="city in cities" :label="city" :key="city">{{city}}</el-checkbox>
          </el-checkbox-group>
        </el-tab-pane>
        <el-tab-pane label="角色管理" name="third">角色管理</el-tab-pane>
        <el-tab-pane label="定时任务补偿" name="fourth">定时任务补偿</el-tab-pane>
      </el-tabs>

      <!--shanchu-->
      <el-dialog title="提示" :visible.sync="dialogVisible" size="tiny" :before-close="handleClose">
        <span>藐视内容</span>
  <span slot="footer" class="dialog-footer">
    <el-button @click="dialogVisible = false">取 消</el-button>
    <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
  </span>
      </el-dialog>
    </div>
</template>

<script>
  const cityOptions = ['上海', '北京', '广州', '深圳'];
export default {
  name: 'pro',
  data () {
    return {
      activeName: 'first',
      dialogVisible: false,
      checkAll: true,
      checkedCities: ['上海', '北京'],
      cities: cityOptions,
      isIndeterminate: true
    }
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event);
    },
    tip: function (event) {
      this.$notify.success({
        title: 'mamaipi',
        message: '这是一条成功的提示消息',
        offset: 100,
        onClose:function(){
          alert("关闭了")
        }
      });
    },
  delete:function(){
      this.$confirm('确认关闭？')
        .then(_ => {
        done();
    })
    .catch(_ => {});
  },
    open3:function(){
        this.$prompt('请输入邮箱', '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
          inputPattern: /[\w!#$%&'*+/=?^_`{|}~-]+(?:\.[\w!#$%&'*+/=?^_`{|}~-]+)*@(?:[\w](?:[\w-]*[\w])?\.)+[\w](?:[\w-]*[\w])?/,
          inputErrorMessage: '邮箱格式不正确'
        }).then(({ value }) => {
          this.$message({
          type: 'success',
          message: '你的邮箱是: ' + value
        });
      }).catch(() => {
          this.$message({
          type: 'info',
          message: '取消输入'
        });
      });
    },
//    选择
    handleCheckAllChange(event) {
      this.checkedCities = event.target.checked ? cityOptions : [];
      this.isIndeterminate = false;
    },
    handleCheckedCitiesChange(value) {
      let checkedCount = value.length;
      this.checkAll = checkedCount === this.cities.length;
      this.isIndeterminate = checkedCount > 0 && checkedCount < this.cities.length;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar{ position:fixed;left:0px; top:70px;height:100%; width:100px;background-color:#000;}
.navbar-box-con{}
.navbar-box-con a{ height:72px;display:block; color:#fff;padding-top:40px;}
</style>
