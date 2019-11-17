<template>
  <div class="my">
    <button open-type="getUserInfo" @getuserinfo="bindGetUserInfo" v-if="isShow">开发模式下获取用户信息</button>
    <!--<button open-type="getUserInfo" @getuserinfo="bindGetUserInfo" @click="getUserInfo1" class="get-user-info">获取用户信息</button>-->
    <div class="bg"><img :src="userInfo.avatarUrl" alt=""></div>
    <div class="head-img-box">
      <div class="head-img"><img :src="userInfo.avatarUrl" alt=""></div>
      <div class="name">欢迎回来，{{userInfo.nickName}}</div>
    </div>
    <div class="nav">
      <ul>
        <li v-for="(item,index) in navList" :key="item"
            @click="changeNav(index)"
            :class="navIndex==index?'active':''">{{item.name}}</li>
      </ul>
    </div>
    <div class="content">
      <div class="no-box">
        <div class="no-img"><img src="../../../static/images/my/notepad.png" alt=""></div>
        <div class="no-t">暂无测评</div>
      </div>
      <div class="more" @click="bindViewTap">查看更多精彩测评</div>
    </div>
  </div>
</template>

<script>
  export default {
    data(){
      return{
        userInfo:{},
        navList:[
          {name:'未完成'},
          {name:'已完成'},
          {name:'全部测评'}
        ],
        navIndex:0,
        isShow:true,
      }
    },
    mounted(){
      // this.getSetting()
    },
    methods:{
      bindGetUserInfo (e) {
        console.log(e.mp.detail.userInfo)
        this.userInfo=e.mp.detail.userInfo
        this.isShow=false
      },
      changeNav(i){this.navIndex=i},
      bindViewTap(){
        const url = '../classify/main'
        if (mpvuePlatform === 'wx') {
          mpvue.switchTab({ url })
        } else {
          mpvue.navigateTo({ url })
        }
      },

    //   getSetting(){
    //     let that=this
    //     wx.getSetting({
    //       success: function(res){
    //         if (res.authSetting['scope.userInfo']) {
    //           wx.getUserInfo({
    //             success: function(res) {
    //               console.log(res.userInfo)
    //               that.userInfo=res.userInfo
    //               //用户已经授权过
    //               console.log('用户已经授权过')
    //             }
    //           })
    //         }else{
    //           console.log('用户还未授权过')
    //         }
    //       }
    //     })
    //
    //   },
    //   getUserInfo1(){
    //     console.log('click事件首先触发')
    //     // 判断小程序的API，回调，参数，组件等是否在当前版本可用。  为false 提醒用户升级微信版本
    //     // console.log(wx.canIUse('button.open-type.getUserInfo'))
    //     if(wx.canIUse('button.open-type.getUserInfo')){
    //       // 用户版本可用
    //     }else{
    //       console.log('请升级微信版本')
    //     }
    //   },
    //   bindGetUserInfo(e) {
    //     // console.log(e.mp.detail.rawData)
    //     if (e.mp.detail.rawData){
    //       //用户按了允许授权按钮
    //       console.log('用户按了允许授权按钮')
    //     } else {
    //       //用户按了拒绝按钮
    //       console.log('用户按了拒绝按钮')
    //     }
    // },
    }
  }
</script>

<style lang="scss" scoped type="text/scss">
  .get-user-info{
    opacity: 0;
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
  }
  .bg{
    width: 100%;
    height: 100px;
    overflow: hidden;
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
    -webkit-filter: blur(10px);
    -moz-filter: blur(10px);
    -o-filter: blur(10px);
    -ms-filter: blur(10px);
    filter: blur(10px);
    img{
      width: 100%;
    }
  }
  .head-img-box{
    width: 100%;
    height: 100px;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    padding: 0 10px;
    .head-img{
      width: 50px;
      height: 50px;
      overflow: hidden;
      border-radius: 50%;
      border: 1px solid #fff;
      margin-right: 10px;
      img{
        width: 100%;
        height: 100%;
      }
    }
    .name{
      font-size: 16px;
      color: #fff;
    }
  }
  .nav{
    width: 100%;
    height: 40px;
    background: #fff;
    border-bottom: 0.5px solid #eaeaea;
    ul{
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      li{
        font-size: 14px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: #888;
        width: 120px;
        height: 40px;
        position: relative;
      }
      .active{
        font-weight: bold;
        color: #333;
        font-size: 15px;
      }
      .active:after{
        /*border-bottom: 2px solid #ffdd2b;*/
        display: block;
        width: 60px;
        height: 3px;
        background: #ffdd2b;
        border-radius: 5px;
        position: absolute;
        bottom: 0;
        /*margin: 0 auto;*/
        content: '';
        left: 30px;
      }
    }
  }
  .no-box{
    width: 200px;
    height: 200px;
    overflow: hidden;
    background: #eaeaea;
    border-radius: 50%;
    margin: 0 auto;
    margin-top: 50px;
    margin-bottom: 40px;
    .no-img{
      width: 100px;
      height:100px;
      margin-top: 40px;
      margin-left:55px;
      margin-bottom: 20px;
      img{
        width: 100%;
        height: 100%;
      }
    }
    .no-t{
      color: #333;
      font-size: 14px;
      text-align: center;
    }
  }
  .more{
    width: 300px;
    height: 50px;
    background: #ffdd2b;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #333;
    font-size: 14px;
    border-radius: 5px;
    margin: 0 auto;
  }
</style>
