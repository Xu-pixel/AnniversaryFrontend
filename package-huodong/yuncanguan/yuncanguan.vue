<template>
<view class="flex-col page">
  <view class="flex-col group">
	<swiper class="bigImg" :current="current">
	<swiper-item v-for="(big,index) in lists" :key="index">
    <image
      class="image"
      :src="big.picture_url"
	  />
	</swiper-item>
	</swiper>
    <view class="flex-row equal-division space-x-2">
      <view class="flex-col items-start equal-division-item space-y-8" :key="index" v-for="(small, index) in lists" @click='changeBigPic(index)'>
        <image
          class="image_2"
          :src="small.picture_url"
		  :class="[index == current ? 'active' : '']"
        />
        <text class="font_1">{{small.picture_name}}</text>
      </view>
    </view>
  </view>
</view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
		  buttonRect: {},
		  current: 0,//轮播图索引
		  list_HkvqbhWP: [null, null, null, null, null, null],
		  lists: [
		  			{
		  						sp:1,
		  				picture_name:'东门',
		  				picture_url:"https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/6360d2c65a7e3f0310d3abbb/636e0914f9b4a40011def608/16681556784402302093.png"
		  			},
		  			{
		  						sp:2,
		  				picture_name:'北门',
		  				picture_url:"https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/6360d2c65a7e3f0310d3abbb/636e0914f9b4a40011def608/16681556784447443523.png"
		  			},
		  			{
		  						sp:3,
		  				picture_name:'西门',
		  				picture_url:"https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/6360d2c65a7e3f0310d3abbb/636e0914f9b4a40011def608/16681556784426983374.png"
		  			},
		  			{
		  						sp:4,
		  				picture_name:'南门',
		  				picture_url:"https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/6360d2c65a7e3f0310d3abbb/636e0914f9b4a40011def608/16681556784433466945.png"
		  			},
		  			{
		  						sp:5,
		  				picture_name:'福友阁',
		  				picture_url:"https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/6360d2c65a7e3f0310d3abbb/636e0914f9b4a40011def608/16681556784456651986.png"
		  			},
		  			{
		  						sp:6,
		  				picture_name:'图书馆',
		  				picture_url:"https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/6360d2c65a7e3f0310d3abbb/636e0914f9b4a40011def608/16681556784456815493.png"
		  			}		
		  		],
	  };
    },
    methods: {
		changeBigPic(index){
			this.current = index;
		},
	},
  };
</script>

<style scoped lang="scss">
.page {
  background-color: #ffffff;
  width: 100%;
  overflow-y: auto;
  overflow-x: hidden;
  height: 100%;
  .group {
    flex: 1 1 auto;
    overflow-y: auto;
	.bigImg{width:100%;height:40rem;}
	.bigImg image{width:100%;height:40rem;}
    .image {
      width: 750rpx;
      height: 1162.03rpx;
    }
    .equal-division {
      padding: 11.39rpx 7.59rpx 138.61rpx 15.19rpx;
      background-color: #ffffff;
      .equal-division-item {
        flex: 1 1 121.52rpx;
        padding: 11.39rpx 3.8rpx;
        .image_2 {
          width: 113.92rpx;
          height: 75.95rpx;
        }
        .font_1 {
          font-size: 15.19rpx;
          font-family: SourceHanSansCN;
          line-height: 14.24rpx;
          color: #383838;
        }
      }
      .space-y-8 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 15.19rpx;
        }
      }
    }
    .space-x-2 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 3.8rpx;
      }
    }
  }
}
</style>