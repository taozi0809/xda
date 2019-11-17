<template>
  <div class="index">
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
    <div class='swiper'>
      <swiper
        :indicator-dots='true'
        indicator-color='#d8d8d8'
        indicator-active-color = '#ffad36'
        :autoplay='true'
        :interval='5000'
        :circular='true'
      >
        <a href="" v-for="(item,index) in swipeList" :key="index">
          <swiper-item class="swipe-item-m">
            <img :src="item.src">
          </swiper-item>
        </a>
      </swiper>
    </div>
    <div class="card">
      <div class="card-top">
        <div class="t-b">
          <div class="t t-r">热卖</div>
          <div class="t">爆款</div>
          <div class="hot">HOT</div>
        </div>
        <div class="p4">不容错过的精彩测评</div>
      </div>
      <div class="card-list">
        <scroll-view class="scroll-view_H card-list-x" scroll-x="true" bindscroll="scroll" enable-flex="true">
          <a href="" v-for="(item,index) in cardaList" :key="index" class="scroll-view-a">
            <view class="scroll-view-item_H">
              <div class="img-box">
                <img :src="item.src" alt="">
                <div class="p4">{{item.number}}已测</div>
              </div>
              <div class="t">{{item.title}}</div>
            </view>
          </a>
        </scroll-view>
      </div>
    </div>
    <div class="card">
      <div class="card-top">
        <div class="t-b">
          <div class="t t-r">热卖</div>
          <div class="t">爆款</div>
          <div class="hot">HOT</div>
        </div>
        <div class="p4">不容错过的精彩测评</div>
      </div>
      <div class="card-list">
        <scroll-view class="scroll-view_H card-list-x" scroll-x="true" bindscroll="scroll" enable-flex="true">
          <a href="" v-for="(item,index) in cardaList" :key="index" class="scroll-view-a">
            <view class="scroll-view-item_H">
              <div class="img-box">
                <img :src="item.src" alt="">
                <div class="p4">{{item.number}}已测</div>
              </div>
              <div class="t">{{item.title}}</div>
            </view>
          </a>
        </scroll-view>
      </div>
    </div>
    <div class="handpick">
      <div class="top">
        <div class="l">
          <div class="t">精选测评</div>
          <div class="p4">不容错过的精彩测评</div>
        </div>
        <div class="r">更多 ></div>
      </div>
      <div class="list">
        <ul>
          <li v-for="(item,index) in list" :key="index" class="list-item">
            <div class="l">
              <div class="t">{{item.title}}</div>
              <div class="des">{{item.des}}</div>
              <div class="number">{{item.number}}</div>
            </div>
            <div class="r"><img :src="item.src"></div>
          </li>
        </ul>
      </div>
    </div>
    <div class="more" @click="bindViewTap">查看更多测评 ></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      swipeList:[
        {
          src:'../../static/images/swipe/1.png',
        },
        {
          src:'../../static/images/swipe/2.png',
        },
        {
          src:'../../static/images/swipe/3.png',
        },
        {
          src:'../../static/images/swipe/4.png',
        },
        {
          src:'../../static/images/swipe/5.png',
        },
      ],
      cardaList:[
        {
          src:'../../static/images/carda/1.png',
          number:'4545',
          title:'人格原型测试人格原型测试人格原型测试',
        },
        {
          src:'../../static/images/carda/2.png',
          number:'69825',
          title:'性魅力测试',
        },
        {
          src:'../../static/images/carda/3.png',
          number:'849725',
          title:'抑郁测试[专业版]',
        },
        {
          src:'../../static/images/carda/1.png',
          number:'1546',
          title:'潜意识画像测试',
        },
        {
          src:'../../static/images/carda/2.png',
          number:'89742654',
          title:'人生底色测试',
        },
        {
          src:'../../static/images/carda/3.png',
          number:'9523544635',
          title:'人格七宗罪',
        },

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
      ],
    }
  },
  methods: {
    bindViewTap(){
      const url = '../classify/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    }
  },
  created () {

  }
}
</script>

<style scoped lang="scss" type="text/scss">
  .index{
    padding-bottom: 40px;
  }
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
  .swiper{
    width: 100%;
    height: 150px;
    box-sizing: border-box;
    overflow: hidden;
    .swipe-item-m{
      width: 100%;
      height: 150px;
      img{
        width: 100%;
        height: 150px;
      }
    }

  }
  .card{
    width: 100%;
    height: 200px;
    overflow: hidden;
    box-sizing: border-box;
    /*border: 1px solid red;*/
    .card-top{
      width: 100%;
      height: 50px;
      box-sizing: border-box;
      /*border: 1px solid red;*/
      padding:5px;
      .t-b{
        display: flex;
        align-items: center;
        width: 110px;
        height: 25px;
        overflow: hidden;
        box-sizing: border-box;
        position: relative;
        /*border: 1px solid red;*/
        .t{
          height: 25px;
          line-height: 25px;
          font-size: 20px;
          color: #333;
          font-weight: bold;
        }
        .t-r{
          height: 25px;
          line-height: 25px;
          color: #ff5b5b;
        }
        .hot{
          position: absolute;
          right: 0;
          top: 0;
          color: #ff5b5b;
          font-size: 10px;
        }
      }
      .p4{
        height: 15px;
        line-height: 15px;
        color: #888;
        font-size: 10px;
      }
    }
    .card-list{
      width: 100%;
      height: 150px;
      overflow-x: auto;
      overflow-y: hidden;
      /*border: 1px solid red;*/
      display: flex;
      box-sizing: border-box;
      .scroll-view_H{
        width: auto;
        height: 150px;
        overflow: hidden;
        padding: 5px;
        display: flex;
        .scroll-view-a{
          display: inline-block;
          width: 100px;
          height: 140px;
          box-sizing: border-box;
          flex-shrink: 0;
          overflow: hidden;
          margin-right: 10px;
          .scroll-view-item_H{
            width: 100px;
            height: 140px;
            .img-box{
              width: 100px;
              height: 100px;
              overflow: hidden;
              border-radius: 5px;
              margin-bottom: 8px;
              img{
                width: 100%;
                height: 100%;
              }
            }
            .t{
              color: #333;
              font-size: 12px;
              font-weight: 600;
              line-height: 1.2;
              display: -webkit-box;
              -webkit-box-orient: vertical;
              -webkit-line-clamp: 2;
              overflow: hidden;
            }
          }
        }

      }
    }
  }
  .handpick{
    width: 100%;
    height: auto;
    .top{
      width: 100%;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-sizing: border-box;
      overflow: hidden;
      padding: 0 5px;
      .l{
        width: 100px;
        height: 50px;
        .t{
          height: 25px;
          line-height: 25px;
          font-size: 20px;
          color: #333;
          font-weight: bold;
        }
        .p4{
          height: 15px;
          line-height: 15px;
          color: #888;
          font-size: 10px;
        }
      }
      .r{
        height: 50px;
        line-height: 50px;
        color: #888;
        font-size: 12px;
      }
    }
    .list{
      width: 100%;
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
          width: 275px;
          position: relative;
          height: 80px;
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
          img{
            width: 100%;
            height: 100%;
          }
        }
      }
    }
  }
  .more{
    width: 150px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #333;
    font-size: 14px;
    border-radius: 5px;
    overflow: hidden;
    background: #eaeaea;
    margin: 0 auto;
    margin-top: 20px;
    /*margin-bottom: 40px;*/
  }
</style>











