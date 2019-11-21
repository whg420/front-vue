<template>
  <div>
<ul>
<h1>登录系统</h1>
<li><b>Name：</b><input type='input' v-model='iptName'/></li>
<li><b>Password：</b><input type='password' v-model='iptPassword'/></li>
<li><button @click="ck">登录</button></li>
</ul>
</div>
</template>

<script>
import  axios from 'axios'
  export default {
    data() {
      return {
        iptName:'',
        iptPassword:''
      }
    },
    methods: {
      ck(){
        // 接收到input数据
        axios.get('/api/login',{
          params:{
            name:this.iptName,
            password:this.iptPassword
          },
          headers:{
"Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoi546L5byY6ZKiIiwicGFzc3dvcmQiOiIxMjM0NTYiLCJpYXQiOjE1NzQzNDA1MDh9.ZQqwltwCwA1pSCE28pwNjRENXZdiAnBA97EDN2InR7M"
          }
        }).then((response)=>{
    // handle success
    console.log(response.data.data);
  }).catch((error)=>{
    // handle error
    console.log(error);
  }).then(()=>{
    // always executed
  });
      }
    },
  }
</script>

<style scoped>

</style>