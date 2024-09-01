<template>
  <div class="vue-panel">
    <div class="project-login-panel">
      <div class="login-type">
        <span class="login-type-panel action" @click="loginWayClick(0, $event)" title="account">账号登录</span>
        <span class="login-type-panel" @click="loginWayClick(1, $event)" title="phone">手机登录</span>
        <span class="login-type-panel test-a action" @click="loginWayClick(2, $event)" title="email">油箱登录</span>
        <span class="login-type-panel action type-action-23" @click="loginWayClick(3, $event)" title="test">测试登录</span>
        <span class="login-type-panel" @click="loginWayClick(4, $event)" title="other">其他登录</span>
      </div>
      <div class="login-data"> 
        <div class="login-data-panel" v-show="verifyArray[0]">
          <div class="login-account-panel">
            <div class="left-icon"><i class="iconfont icon-wodemianshi"></i></div>
            <div class="right-input"><input type="text" ref="systemAccountName" placeholder="请输入系统账户" value="" /></div>
          </div>
          <div class="login-pwd-panel">
            <div class="left-icon"><i class="iconfont icon-quanxian-mian"></i></div>
            <div class="right-input"><input type="text" ref="systemAccountPwd" placeholder="请输入系统密码" value="" /></div>
          </div>
          <div class="login-error-panel">
            <span class="error-info" ref="errorInfo"></span>
          </div>
          <div class="login-submit-panel" ref="submitType" @click="loginSubmitClick" type="account"></div>
        </div>
        <div class="login-data-panel" v-show="verifyArray[1]">
          <div class="login-account-panel" style="background-color: #81b569;">
            <div class="left-icon"><i class="iconfont icon-wodemianshi"></i></div>
            <div class="right-input"></div>
          </div>
          <div class="login-pwd-panel" style="background-color: #4c7e7e;">
            <div class="left-icon"><i class="iconfont icon-quanxian-mian"></i></div>
            <div class="right-input"></div>
          </div>
          <div class="login-submit-panel" ref="submitType" @click="loginSubmitClick" type="phone"></div>
        </div>
        <div class="login-data-panel" v-show="verifyArray[2]">
          <div class="login-account-panel" style="background-color: #81b569;">
            <div class="left-icon"><i class="iconfont icon-wodemianshi"></i></div>
            <div class="right-input"></div>
          </div>
          <div class="login-pwd-panel" style="background-color: #4c7e7e;">
            <div class="left-icon"><i class="iconfont icon-quanxian-mian"></i></div>
            <div class="right-input"></div>
          </div>
          
          <div class="login-submit-panel" ref="submitType" @click="loginSubmitClick" type="email"></div>
        </div>
        <div class="login-data-panel" v-show="verifyArray[3]"><span>测试验证</span></div>
        <div class="login-data-panel" v-show="verifyArray[4]"><span>其他验证</span></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      verifyArray: [true, false, false, false, false]
    };
  },
  methods: {
    loginWayClick(index, e){
      if(!e.target.className.includes("action")){
        var panelList = document.getElementsByClassName("login-type-panel");
        for(var k = 0; k < panelList.length; k ++){
          var classArray = panelList[k].className.split(" ");
          if(classArray.includes("action")){
            panelList[k].className = classArray.filter(item => item !== "action").join(" ");
            e.target.className = e.target.className + " action";
          }
        }
      }

      if(index == 0 && this.verifyArray[index]){
        this.verifyArray[index] = true;
      }else{
        var count = this.verifyArray.length;
        for(var i = 0; i < count; i ++){
          this.verifyArray[i] = false;
          if(i == index){
            this.verifyArray[i] = !this.verifyArray[i];
          }
        }
      }
    }
  }
}
</script>

<style>
  .vue-panel{
    width: 100vw;
    height: 100vh;
    background: url(../assets/wall.jpeg)no-repeat 0 0 fixed;
    background-size: cover;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
  }
  
  .project-login-panel{width:400px;height:250px;background: #FFF;margin: 10% auto 0 auto;}
  .login-type{
    width: 100%;
    height: 49px;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    border-bottom:1px solid #000;
  }
  .login-type-panel:hover{
    cursor: pointer;
  }
  .login-data{
    position: relative;
    width: 100%;
    height: 200px;
  }
  .login-data-panel{
    position: relative;
    width: 100%;
    height: 100%;
    display: flex;
    flex-flow: column;
    align-items: center;
    justify-content: center;
  }
  .login-account-panel,.login-pwd-panel{
    width:300px;
    height: 40px;
    display: flex;
    color: #000;
    align-items: center;
    font-size: 18px !important;
    justify-content: space-between;
    border-bottom: 1px solid #B1B1B1;
  }
  .left-icon{
    position: relative;
    width: 40px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .left-icon>i{
    font-size: 18px !important;
  }
  .right-input{
    position: relative;
    width: 260px;
    height: 100%;
    display: flex;
    align-items: center;
  }
  .right-input>input{
    position: relative;
    width: 100%;
    height: 100%;
    outline: none;
    border: transparent;
  }
  /* .login-account-panel,.login-pwd-panel>div{
    position: relative;
    width:100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    border-bottom: 1px solid #000;
  } */




  .login-error-panel{
    width: 300px;
    height: 30px;
  }
  .login-submit-panel{
    width: 300px;
    height: 40px;
    background-color: #a0a0a0;
  }
  .action{
    color: #FF0000;
  }

</style>