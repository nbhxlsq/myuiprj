<template>
  <div id="mainbody">
    <h2>我这里是首页</h2>
    <router-link to="/user">前往用户中心</router-link>
    <div>测试登录</div>
    <v-login/>
  </div>
</template>

<script>

// console.log(`${axios.defaults.baseURL}`);
// axios.get(`${axios.defaults.baseURL}/author/getuser?uid=1`).then((response) => {
//   console.log(response.data)
// })
// import myget from '../utils/api'
import {getRequest} from '../utils/api'
import Mylogin from '../components/Login'
export default {

  name: 'mainbody'
,
components:{
  'v-login':Mylogin
},
mounted(){
   console.log('coming in');
   getRequest('/author/getuser?uid=1').then((response) => {
  console.log(response)
  });

  this.myaxios.get('/author/getuser?uid=1').then((response) => {
  console.log(response)
})
  //  utilapi.getRequest.getRequest('/author/getuser?uid=1').then((response) => {
  // console.log(response.data)
  // });

}
 
}
</script>