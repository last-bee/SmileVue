<template>
  <div>
    <div  class="search-bar">
       <van-row>
        <van-col span='3' >
          <img :src="locationIcon"  class="location-icon">
        </van-col>
        <van-col span='16'>
          <input type="text" class="search-input">
        </van-col>
        <van-col span='5'>
          <van-button size='mini'>查找</van-button>
        </van-col>
      </van-row>
    </div>
    <div class="swiper-area">
        <van-swipe :autoplay='1000'>
            <van-swipe-item v-for='(item,index) in bannerList' :key='index'>
              <img :src="item.imageUrl" class="img-src">
            </van-swipe-item>
        </van-swipe>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
  export default {
    data(){
      return{
          locationIcon:require('../../assets/img/location.png'),
          bannerList:[
            {imageUrl:'http://7xjyw1.com1.z0.glb.clouddn.com/simleVueDemoPic001.jpg'},
            {imageUrl:'http://7xjyw1.com1.z0.glb.clouddn.com/simleVueDemoPic002.jpg'},
            {imageUrl:'http://7xjyw1.com1.z0.glb.clouddn.com/simleVueDemoPic003.jpg'}
          ]
      }
    },
    created(){
      axios({
        url:'https://www.easy-mock.com/mock/5afd662977cb97630341a85e/example/index',
        method:'get'
      }).then((res)=>{
        console.log(res.data.data)
      })
    }
  }
</script>

<style scoped>
.search-bar{
  height: 2.5rem;
  background-color: #e5017d;
  line-height: 2.5rem;
  overflow: hidden;
}
.location-icon{
  padding:.2rem;
  padding-left: .3rem;
  width:90%;
}
.search-input{
  width:100%;
  text-align: left;
  height: 1.3rem;
  border:0 ;
  border-bottom:1px solid #ffffff;
  background: #e5017d;
  color:#fff;
 
}
.img-src{
  width:100%
}
.swiper-area{
  clear: both;
}
</style>