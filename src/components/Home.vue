<template>
  <div>
    <!-- 首页搜索框 -->
    <div class="search-bar">
      <van-row gutter="5">
        <van-col span="3">
          <img :src="locationIcon" width="60%" class="location-icon">
        </van-col>
        <van-col span="16">
          <input type="text" class="search-input" placeholder="请输入内容">
        </van-col>
        <van-col span="5">
          <van-button size="mini">查找</van-button>
        </van-col>
      </van-row>
    </div>
    <!-- 轮播图 -->
    <div class="swiper-area">
      <van-swipe :autoplay="1000">
        <van-swipe-item v-for="(banner,index) in bannerPicArray" :key="index">
          <img v-lazy="banner.imageUrl" width="80%">
          <!-- <img v-lazy="banner.imageUrl" width="80%"> -->
        </van-swipe-item>
      </van-swipe>
    </div>
    <!-- easyMock -->
    <div class="type-bar">
      <div v-for="(cate,index) in category" :key="index">
        <img v-lazy="cate.image" width='90%'>
        <span>{{cate.mallCategoryName}}</span>
      </div>
      <!-- swiper -->
      <!-- <swiper :options="swiperOption">
        <swiper-slide v-for="(item,index) in recommendGoods" :key="index">
          <div class="recommend-item">
            <img :src="item.image" width="80%">
            <div>{{ite.goodsName}}</div>
            <div>${{item.price}} (${{item.mallPrice}})</div>
          </div>
        </swiper-slide>
      </swiper>
    </div> -->
    <swiperDefault></swiperDefault>
    <!-- 商品推荐 -->
    <div class="shopping-area">
      <div class="shopping-title">商品推荐</div>
      <div class="shopping-body"></div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import swiperDefault from '@/swiper/swiperDefault'
export default {
  data() {
    return {
      locationIcon: require('@/assets/images/China.png'),
      bannerPicArray:[
        {imageUrl: ''},
        {imageUrl: ''},
        {imageUrl: ''}
      ]
    }
  },
  created() {
    axios({
      url: 'https://www.easy-mock.com/mock/5ae2427800247c2aa1efe442/SmileVue/SmileVue/index',
      method: 'get',
    })
    .then(response=>{
      consol.log(response)
      if(response.status == 200) {
        this.category = response.data.data.category;
      }
    })
    .catch((error) => {
    })
  },
  components: {swiper,swiperSlide,swiperDefault}
};
</script>

<style lang="scss" scoped>
.search-bar{
  height: 2.2rem;
  background-color: rgb(80, 46, 21);
  line-height: 2.2rem;
  .location-icon{
      padding-top: .2rem;
      padding-left: .3rem;
      margin: 0 auto;
  }
  .search-input{
      width:100%;
      height: 1.3rem;
      border-top:0px;
      border-left:0px;
      border-right:0px;
      border-bottom: 1px solid rgb(235, 199, 199) !important ;
      background-color: rgb(235, 199, 199);
      color:#fff;
      text-align: center;
  }
}
  .swiper-area {
    width: 20rem;
    clear: both;
    img {
      height: 100px;
    }
  }
  .shopping-area{
    background-color: #fff;
    margin-top: .3rem;
    .shopping-title{
      border-bottom: 1px solid #eee;
      font-size: 14px;
      padding: .2rem;
      color: #e5017d;
    }
  }
  .type-bar {
    background-color: #fff;
    margin:0 .3rem .3rem .3rem;
    border-radius: .3rem;
    font-size:14px;
    display: flex;
    flex-direction:row;
    flex-wrap:nowrap;
    div {
      padding: .3rem;
      font-size: 12px;
      text-align: center;
    }
  }
</style>
