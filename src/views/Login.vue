<template>
  <div class='login'>
    <div class='box'>
      <div><p class='system-name'>{{name}}</p></div>
      <el-form style='margin-top: 24px'>
        <el-form-item>
          <el-input type='text' placeholder="在此输入用户名." v-model="login.userName">
            <template slot="prepend">账&nbsp;&nbsp;号</template>
          </el-input>
        </el-form-item>
        <el-form-item name='password'>
          <el-input type='password' placeholder="在此输入密码." v-model="login.password">
            <template slot="prepend">密&nbsp;&nbsp;码</template>
          </el-input>
        </el-form-item>
      </el-form>
      <div class='other'>
        <el-row>
          <el-col :span=8>
            <el-checkbox v-model='login.remember'>记住登陆</el-checkbox>
          </el-col>
          <el-col :span=8 :offset=8><a :href='forgetPasswordUrl'>忘记密码</a></el-col>
        </el-row>
      </div>
      <div class='operation'>
        <el-button type='primary' style='width: 100%' @click="loginAction">登&nbsp;&nbsp;录</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      name: '这个是系统的名称',
      login: {
        userName: '',
        password: '',
        remember: false
      },
      forgetPasswordUrl: '#'
    }
  },
  methods: {
    loginAction () {
      console.log('login')
    }
  }
}
</script>

<style lang="less" scope>
  .login{
    width: 100%;
    height: 100%;
    background-image: url('../assets/login.jpeg');
    .box{
      width: 25%;
      height: 30%;
      position: relative;
      left: 20%;
      top: 25%;
      div{
        margin-bottom: 8px;
      }
      .other{
        margin-top: -8px;
      }
      .system-name{
        font-size: 24px;
      }
    }
  }
</style>

<style lang="less">
  .el-input__inner {
    background-color: transparent;
  }
  .el-input-group__prepend{
    background-color: transparent;
  }
  .el-checkbox__inner{
    background-color: transparent;
  }
  .el-button--primary{
    background-color: transparent;
  }
</style>
