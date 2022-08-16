<template>
  <div class="login-wrap">
        <el-form
          :model="formdata"
          status-icon
          :rules="rules"
          ref="ruleForm"
          label-width="100px"
          class="demo-ruleForm">
          <el-form-item label="用户名" prop="username">
            <el-input type="password" v-model="formdata.username" autocomplete="off"></el-input>
          </el-form-item>
          <el-form-item label="密码" prop="password">
            <el-input v-model.number="formdata.password"></el-input>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="submitForm('ruleForm')">提交</el-button>
            <el-button @click="resetForm('ruleForm')">重置</el-button>
          </el-form-item>
        </el-form>
  </div>
</template>

<script>
export default {
  name: "login"
}
</script>

<style scoped>

</style>
