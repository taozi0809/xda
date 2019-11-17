<template>
  <div class="classify">
    <div class="pos-top">
      <div class="l">
        <div class="img-box"><img src="../../../static/images/user.png" alt=""></div>
        <div class="t">壹心理测评+</div>
      </div>
      <div class="r">
        <div class="input">
          <div class="search-box"><van-icon name="search" color="#888" size="14px"/></div>
          <div class="t">搜索</div>
        </div>
      </div>
    </div>
    <div class="main">
      <div class="main-l">
        <ul>
          <li v-for="(item,index) in navList" :key="index" :class="navIndex==index?'active':''"
              @click="changeNav(index)">{{item.title}}</li>
        </ul>
      </div>
      <div class="main-r">
        <div class="main-r-top" @click="isDrapdown=!isDrapdown">
          <div class="l">排序</div>
          <div class="r">{{drapdownList[drapdownIndex].name}}&nbsp;<van-icon name="arrow-down" /></div>
        </div>
        <div class="main-r-list">
          <ul>
            <li v-for="(item,index) in list" :key="index" class="list-item">
              <div class="l">
                <div class="t">{{item.title}}</div>
                <div class="des">{{item.des}}</div>
                <div class="number">{{item.number}}</div>
              </div>
              <div class="r"><img :src="item.src"></div>
            </li>
            <div class="no-more">没有更多了</div>
          </ul>
        </div>
        <div class="main-l-dropdown" v-if="isDrapdown">
          <ul>
            <li v-for="(item,index) in drapdownList" :key="index"
                :class="drapdownIndex==index?'active':''"
                @click="changeDrapdown(index)">
              <div class="box">{{item.name}} &nbsp;<van-icon name="success" v-if="drapdownIndex==index"/></div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data(){
      return{
        navIndex:0,
        navList:[
          {title:'全部'},
          {title:'性格'},
          {title:'情感'},
          {title:'职场'},
          {title:'健康'},
          {title:'人际'},
          {title:'亲子'},
          {title:'能力'},
          {title:'趣味H5'},
          {title:'性格'},
          {title:'情感'},
          {title:'职场'},
          {title:'健康'},
          {title:'人际'},
          {title:'亲子'},
          {title:'能力'},
          {title:'趣味H5'},
        ],
        list:[
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/1.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/2.png',
          },
          {
            title:'测测你的大抑郁有多深？',
            des:'抑郁测试[专版版]',
            number:'20.0w人已测',
            src:'../../static/images/carda/3.png',
          },
        ],
        drapdownIndex:0,
        drapdownList:[
          {name:'按时间'},
          {name:'按热度'},
        ],
        isDrapdown:false,
      }
    },
    methods:{
      changeNav(i){
        this.navIndex=i
      },
      changeDrapdown(i){
        this.isDrapdown=false
        this.drapdownIndex=i
      }
    },
  }
</script>

<style lang="scss" scope type="text/scss">
  .classify{
    width: 100%;
    position: absolute;
    top: 0;
    bottom: 0;
    overflow: hidden;
    box-sizing: border-box;
    .pos-top{
      width: 100%;
      height: 40px;
      background: rgba(0,0,0,.4);
      position: absolute;
      top: 0;
      left: 0;
      overflow: hidden;
      z-index: 10;
      display: flex;
      align-content: center;
      justify-content: space-between;
      box-sizing: border-box;
      padding: 0 5px;
      .l{
        width: 150px;
        height: 40px;
        display: flex;
        align-items: center;
        .img-box{
          width: 26px;
          height: 26px;
          overflow: hidden;
          box-sizing: border-box;
          border: 1px solid #fff;
          border-radius:50%;
          margin-right: 5px;
          img{
            width: 100%;
            height: 100px;
          }
        }
        .t{
          color: #fff;
          font-size: 14px;
          height: 26px;
          line-height: 26px;
        }
      }
      .r{
        width: 80px;
        height: 40px;
        display: flex;
        align-items: center;
        .input{
          width: 80px;
          height: 26px;
          border-bottom-left-radius: 30px;
          border-bottom-right-radius: 30px;
          border-top-left-radius: 30px;
          border-top-right-radius: 30px;
          background: #fff;
          display: flex;
          align-items: center;
          .search-box{
            width: 26px;
            height: 26px;
            display: flex;
            align-items: center;
            justify-content: center;
          }
          .t{
            color: #888;
            font-size: 12px;
          }
        }
      }
    }
    .main{
      position: absolute;
      top: 40px;
      width: 100%;
      bottom: 0;
      box-sizing: border-box;
      display: flex;
      .main-l{
        width: 75px;
        box-sizing: border-box;
        height: 100%;
        border: 0.5px solid #eaeaea;
        background:#eee;
        overflow-x: hidden;
        overflow-y: auto;
        ul{
          li{
            width: 100%;
            height: 50px;
            font-size: 14px;
            color: #333;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
          }
          .active{
            font-size: 15px;
            font-weight: bold;
            background: #fff;
          }
        }
      }
      .main-r{
        width: 300px;
        box-sizing: border-box;
        height: 100%;
        border-left: 0.5px solid #eaeaea;
        position: relative;
        .main-r-top{
          width: 100%;
          height: 51px;
          background: #fff;
          border-bottom: 0.5px solid #eaeaea;
          overflow: hidden;
          display: flex;
          align-items: center;
          justify-content: space-between;
          padding: 0 10px;
          box-sizing: border-box;
          .l{
            color: #333;
            font-size: 14px;
          }
          .r{
            color: #333;
            font-size: 14px;
            display: flex;
            align-items: center;
          }
        }
        .main-r-list{
          width: 100%;
          position: absolute;
          top: 51px;
          bottom: 0;
          box-sizing: border-box;
          overflow-x: hidden;
          overflow-y: auto;
          .list-item{
            width: 100%;
            height: 100px;
            box-sizing: border-box;
            border-bottom: 0.5px solid #eaeaea;
            overflow: hidden;
            padding: 10px 5px;
            display: flex;
            justify-content: space-between;
            .l{
              width: 200px;
              position: relative;
              height: 80px;
              box-sizing: border-box;
              padding-left: 5px;
              .t{
                color: #333;
                font-size: 15px;
                font-weight: bold;
                margin-bottom: 10px;
              }
              .des{
                color: #888;
                font-size: 14px;
              }
              .number{
                color: #888;
                font-size: 12px;
                position: absolute;
                right: 0;
                bottom: 0;
              }
            }
            .r{
              width: 80px;
              height: 80px;
              overflow: hidden;
              border-radius: 5px;
              flex-shrink: 0;
              img{
                width: 100%;
                height: 100%;
              }
            }
          }
          .no-more{
            width: 100%;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            color: #888;
          }
        }
        .main-l-dropdown{
          position: absolute;
          top: 50px;
          height: 100px;
          width: 100%;
          background: #fff;
          border-bottom: 0.5px solid #eaeaea;
          overflow: hidden;
          box-sizing: border-box;
          z-index: 10;
          ul{
            li{
              width: 100%;
              height: 50px;
              color: #888;
              font-size: 14px;
              display: flex;
              align-items: center;
              flex-direction:row-reverse;
              .box{
                display: flex;
                align-items: center;
                padding-right: 10px;
              }
            }
            .active{
              background: #eaeaea;
              color: #333;
            }
          }
        }
      }

    }
  }
</style>
