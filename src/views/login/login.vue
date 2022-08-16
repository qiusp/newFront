<template>
  <div class="login-wrap">
        <el-form
          :model="formdata"
          :rules="rules"
          ref="ruleForm"
          label-width="100px"
        >
          <el-form-item label="用户名" prop="username">
            <el-input type="password" v-model="formdata.username" autocomplete="off"></el-input>
          </el-form-item>
          <el-form-item label="密码" prop="password">
            <el-input v-model.number="formdata.password"></el-input>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="login('ruleForm')">提交</el-button>
            <el-button @click="resetForm('ruleForm')">重置</el-button>
          </el-form-item>
        </el-form>
  </div>
</template>

<script>
export default {
  name: "login",
  data(){
    //es6箭头函数

    var validatePass = (rule, value, callback) => {
      if (value === '') {
        callback(new Error('请输入用户名'));
      } else {
        callback();
      }
    };

    var validatePass2 = (rule, value, callback) => {
      if (value === '') {
        callback(new Error('请输入密码'));
      } else {
        callback();
      }
    };


    return{
      // 定义变量
      formdata:{
        username:'',
        password:''
      },
      // 定义限制
      rules: {
        username: [
          { validator: validatePass, trigger: 'blur' }
        ],
        password: [
          { validator: validatePass2, trigger: 'blur' }
        ],
      }
    };
  },
  methods:{
    login(){},
    resetForm(){}
  }


}
</script>

<style scoped>
.login-wrap{
  height: 100%;
  background-color: beige;
  /*弹性盒布局*/
  display: flex;
  justify-content: center;
  align-items: center;

  background-image: url("../../assets/image/login1.png");
  background-position: center;
  /* 背景图不平铺 */
  /*background-repeat: no-repeat;*/
  /* 当内容高度大于图片高度时，背景图像的位置相对于viewport固定 */
  background-attachment: fixed;
  /* 让背景图基于容器大小伸缩 */
  /*background-size: cover;*/
  /* 设置背景颜色，背景图加载过程中会显示背景色 */
  /*background-color: #464646;*/

}
</style>
