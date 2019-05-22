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
          <img :src="banner.imageUrl" width="80%">
          <!-- <img v-lazy="banner.imageUrl" width="80%"> -->
        </van-swipe-item>
      </van-swipe>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
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
  // created() {
  //   axios({
  //     url: 'https://www.easy-mock.com/mock/5ae2427800247c2aa1efe442/SmileVue/SmileVue/index',
  //     method: 'get',
  //   })
  //   .then(response=>{
  //     consol.log(response)
  //     if(response.status == 200) {
  //       this.category = response.data.data.category;
  //     }
  //   })
  //   .catch((error) => {
  //   })
  // }
};
</script>

<style scoped>
.search-bar{
  height: 2.2rem;
  background-color: rgb(80, 46, 21);
  line-height: 2.2rem;
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
  .location-icon{
      padding-top: .2rem;
      padding-left: .3rem;
      margin: 0 auto;
  }
  .swiper-area {
    width: 20rem;
    clear: both;
  }
  .swiper-area img {
    height: 100px;
  }
</style>