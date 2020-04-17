<template>
<el-form label-position="left" :model="loginForm" status-icon :rules="rules" ref="loginForm" label-width="100px" class="demo-ruleForm">
    <el-form-item label="用户" prop="name">
        <el-input v-model="loginForm.name" placeholder="登录名"></el-input>
    </el-form-item>
  <el-form-item label="密码" prop="pass">
    <el-input type="password" v-model="loginForm.pass" autocomplete="off"></el-input>
  </el-form-item>
  <el-form-item>
    <el-button type="primary" @click="submitForm('loginForm')">登录</el-button>
    <el-button @click="resetForm('loginForm')">重置</el-button>
  </el-form-item>
</el-form>

</template>

<script>
  export default {
    data() {
      return {
         loginForm: {
          name:'',
          pass: '' 
        },
        rules: {
            name:[{ required:true,message:'请输入登录名',trigger:'blur' }],
          pass: [
            {required:true,message:'请输入密码', trigger: 'blur' },
            {min:3,max:15,message:'密码最小3位最大15位',trigger:'blur' }
          ]
        }
      };
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            //   console.log();
            //   let lparam={
            //       name:this.loginForm.name,
            //       pass:this.loginForm.pass
            //   };
              this.myaxios.put('/author/loginsys',this.myqs.stringify(this.loginForm))
              .then((result)=>{
                  console.log(result);
              });
            alert('submit!');
          } else {
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
  }
</script>
