<template>
  <div class="home-container">
    <!-- 吸顶组件 -->
    <van-sticky>
      <div class="header">
        <div class="address">
          <van-button class="school" size="small" type="default">鲁东大学  <i class="iconfont iconxiajiantou"></i></van-button>
        </div>
        <van-search class="search" placeholder="请输入搜索关键词" shape="round" readonly @click="test()" />
      </div>
      <div class="info-type">
        <van-tabs v-model="infoTypeActive" swipeable color="#1989FA" :border=false title-active-color="#1989FA">
          <van-tab v-for="index in 10" :title="'选项 ' + index" v-bind:key="index">
          </van-tab>
        </van-tabs>
      </div>
    </van-sticky>
    <div class="info-body">
      <div class="info-item" v-for="index in 6" v-bind:key="index">
        <div class="info-item-head">
          <div class="title">
            <van-col>
              <van-image round width="2rem" height="2rem" src="https://img.yzcdn.cn/vant/cat.jpeg"/>
            </van-col>
            <van-col class="title-info">
              <van-row class="title-info-user">
                时光静好微风不燥
              </van-row>
              <van-row class="title-info-date">
                10-09:17:01
              </van-row>
            </van-col>
            <van-col class="sex-age">
              <div>
                男 | 21
              </div>
            </van-col>
          </div>
          <div class="star">
             <i class="iconfont iconjiahao">关注</i>
          </div>
        </div>
        <div class="info-item-body">
          <div class="info-item-body-content">
            有些习惯，终究要用一生的时光改变。就像，某些不可言明的怀念。往往在夜深人静时，轰然来袭。刺痛到心底最柔软的地方，无力挣扎。
          </div>
          <div class="info-item-body-img">
            <van-image width="32%" height="6em" fit="cover" :src="item" v-for="(item,index) in infoPicture" :key="index"/>
            <!-- <VuePreview :slides=slide></VuePreview> -->
          </div>
        </div>
        <!-- 尾部 -->
        <div class="info-item-footer">
          <!-- 按钮 -->
          <div class="action-button">
            <van-button type="default" size="small"><i class="iconfont icondianzan"></i><span>68</span></van-button>
            <van-button type="default" size="small"><i class="iconfont iconpinglun1"></i><span>128</span></van-button>
            <van-button type="default" size="small"><i class="iconfont iconzhuanfa"></i><span>8</span></van-button>
          </div>
          <!-- 评论 -->
          <div class="comment">
            <div class="comment-head">
              <div>
                <i class="iconfont iconhuo"></i>
                <div><span>热评</span></div>
              </div>
              <span>11赞</span>
            </div>
            <div class="comment-info">
              <div class="comment-info-item"><authorIcon></authorIcon><span class="comment-info-author">时光静好微风不燥</span> : <span class="comment-info-content">倒计时3天！</span></div>
              <div class="comment-info-item"><span class="comment-info-author">雷布森</span> : <span class="comment-info-content">大半夜不睡觉会嫁不出去的！</span></div>
              <div class="comment-info-item"><span class="comment-info-author">会飞的鱼</span> : <span class="comment-info-content">这是个自拍。。</span></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Search, Button, Tab, Tabs, Row, Col, Sticky, Image, ImagePreview } from 'vant'
import AuthorIcon from '../components/public/AuthorIcon.vue'
export default {
  name: 'home',
  data () {
    return {
      // 表示当前选中了哪一个信息类型
      infoTypeActive: '',
      infoPicture: [
        'https://img.yzcdn.cn/vant/cat.jpeg',
        'https://img.yzcdn.cn/vant/cat.jpeg',
        'https://img.yzcdn.cn/vant/cat.jpeg',
        'https://img.yzcdn.cn/vant/cat.jpeg',
        'https://img.yzcdn.cn/vant/cat.jpeg',
        'https://img.yzcdn.cn/vant/cat.jpeg',
        'http://i5.bbs.fd.zol-img.com.cn/t_s800x5000/g3/M05/05/09/Cg-4V1DPHT-Iai_SAAHD-4qBA14AADV9gNva6UAAcQT185.jpg',
        'http://pic22.nipic.com/20120629/9363864_135939629103_2.jpg',
        'https://img.yzcdn.cn/vant/cat.jpeg'
      ]
    }
  },
  methods: {
    test: function () {
      console.log('"dddd"')
    },
    img: function () {
      ImagePreview([
        'https://img.yzcdn.cn/1.jpg',
        'https://img.yzcdn.cn/2.jpg'
      ])
    }
  },
  components: {
    [Search.name]: Search, // 搜索组件
    [Button.name]: Button, // 按钮组件
    [Tab.name]: Tab, // 导航组件
    [Tabs.name]: Tabs, // 导航子组件
    [Row.name]: Row, // 布局行组件
    [Col.name]: Col, // 布局列组件
    [Sticky.name]: Sticky, // 粘性布局组件 吸顶
    [Image.name]: Image, // 图片显示组件
    [ImagePreview.name]: ImagePreview,
    'authorIcon': AuthorIcon
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/alibabaicon/iconfont.css';
.home-container{
  // 头部样式
  .header{
    background-color: #FFFFFF;
    display: flex;
    align-content: space-between;
    align-items: center;
    //搜索
    .search{
      flex-grow: 1;
    }
    //地址（学校）
    .address{
      padding: 10px 0px 10px 12px;
      display: flex;
      align-items: center;
      .school{
        border: none;
        span{
          font-weight: 900;
        }
        i{
          font-size: 120%
        }
      }
    }
  }
  //信息主体
  .info-body{
    //单个信息
    .info-item{
      background-color: #FFFFFF;
      margin-top: 8px;
      padding: 10px;
      //信息的头部
      .info-item-head{
        display: flex;
        justify-content: space-between;
        //头像及个人信息
        .title{
          display: flex;
          align-items: flex-end;
          //个人信息
          .title-info {
            margin-left: 8px;
            //用户名
            .title-info-user{
              font-size: 13px;
              font-weight: 900;
              color: #303133;
            }
            //发表时间
            .title-info-date{
              color: #909399;
              font-size: 10px;
            }
          }
          //性别年龄
          .sex-age{
            background-color: #D9ECFF;
            font-size: 8px;
            padding: 3px;
            border-radius: 3px;
            color: #1989FA;
            margin-left: 10px;
            align-self:flex-start;
          }
        }
        //关注
        .star{
          // align-self:center ;
          background-color: #1989FA;
          border-radius: 12.5px;
          height: 25px;
          width: 60px;
          display: flex;
          justify-content:center;
          align-items:center;
          padding-bottom: 2px;
          i{
            font-size: 10px;
            color: #FFFFFF;
          }
        }
      }
      //信息的主体部分
      .info-item-body{
        margin: 10px 0px;
        //信息主文
        .info-item-body-content{
          font-size: 13px;
          color: #606266;
          line-height: 25px;
        }
        //信息相关图片
        .info-item-body-img{
          display: flex;
          flex-wrap:wrap;
          justify-content: space-between;
          .van-image{
            // margin-right: 10px;
            // flex-grow: 1;
            margin-top: 10px;
          }
        }
        .info-item-body-img:after{
          content: '';
          width: 31%;
        }
      }
      //信息的尾部
      .info-item-footer{
        // 按钮
        .action-button{
          margin: 10px 0px;
          display: flex;
          justify-content: flex-end;
          .van-button{
            margin-left: 2%;
            border: none;
            .van-button__text{
              display: flex;
              align-items: center;
            }
            i{
              font-size: 20px;
              color: #909399;
            }
            span{
              margin-left: 6px;
              font-size: 12px;
              color: #909399;
            }
          }
          // .van-button:nth-child(1){
          //   i{
          //     font-size: 20px;
          //     align-self: flex-start;
          //   }
          // }
        }
        // 评论
        .comment{
          background-color: #F7F8FA;
          border-radius: 5px;
          padding: 5px  10px 10px 10px;
          .comment-head{
            display: flex;
            justify-content: space-between;
            div{
              display: flex;
              align-items:center;
              i{
                font-size: 25px;
                color: #FF440B;
                z-index: 1;
              }
              div{
                display: flex;
                justify-content:center;
                align-items:center;
                background: #FBE7CF;
                width: 34px;
                height: 16px;
                border-radius: 8px 8px 8px 8px;
                margin-left: -8px;
                span{
                  font-size: 12px;
                  color: #7B5B42;
                }
              }
            }
            span{
              font-size: 14px;
              color: #909399;
            }
          }
          .comment-info{
            .comment-info-item{
              display: flex;
              align-items: baseline ;
              .author{
                height: 17px;
                margin-right: 5px;
              }
            }
            margin-left: 3px;
            span{
              font-size: 13px;
              line-height: 30px;
            }
            .comment-info-author{
              color: #2C54BB;
            }
            .comment-info-content{
              margin-left: 5px;
            }
          }
        }
      }
    }
  }
}
</style>
