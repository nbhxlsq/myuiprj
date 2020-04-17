<template>
 <el-container>
  <el-header height="50px">Header</el-header>
  <el-container >
    <el-aside width="200px" >       
        <m-menu/>
        </el-aside>
    <el-container>
      <el-main>
          <router-view/>
       <!-- <m-mainbody/>      -->
    </el-main>     
    </el-container>
  </el-container>
   <el-footer>Footer</el-footer>
</el-container>
</template>
<style>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 5px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
 
</style>
<script>
import Menu from '../components/Menu.vue'
import MainBody from '../components/mainbody'
import MainUser from '../components/user'
export default {
    components:{
        'm-menu':Menu,       

    }
}
</script>