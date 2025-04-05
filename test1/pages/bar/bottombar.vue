<template>
	<view>
		<!-- 底部导航栏 -->
		<nav class="bottom-nav">
		  <view class="nav-item" @click="onNav('照明')">
		    <img src="/images/灯泡.png" alt="icon" class="nav-icon" />
		    <view class="nav-label">照明</view>
		  </view>
		  <view class="nav-item" @click="onNav('安防')">
		    <img src="/images/监控3.png" alt="icon" class="nav-icon" />
		    <view class="nav-label">安防</view>
		  </view>
		
		  <!-- 中间凸起的主页按钮 -->
		  <view class="nav-center" @click="onNav('首页')">
		    <img src="https://via.placeholder.com/40" alt="home" class="home-icon" />
		  </view>
		
		  <view class="nav-item" @click="onNav('家电')">
		    <img src="/images/家.png" alt="icon" class="nav-icon" />
		    <view class="">家电</view>
		  </view>
		  <view class="nav-item" @click="onNav('成员')">
		    <img src="/images/成员1.png" alt="icon" class="nav-icon" />
		    <view class="nav-label">成员</view>
		  </view>
		</nav>
	</view>
</template>

<script>
</script>

<style>
	/* 底部导航栏 */
	.bottom-nav {
	  position: fixed;
	  bottom: 0;
	  left: 0;
	  width: 100%;
	  height: 120rpx; /* 修改：60px → 120rpx */
	  background: #102522;
	  display: flex;
	  border-radius: 40rpx; /* 修改：20px → 40rpx */
	  align-items: center;
	  justify-content: space-around;
	  z-index: 10;
	}
	
	/* 普通导航按钮 */
	.nav-item {
	  text-align: center;
	  color: #fff;
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	}
	.nav-icon {
	  width: 48rpx; /* 修改：24px → 48rpx */
	  height: 48rpx; /* 修改：24px → 48rpx */
	  margin-bottom: 4rpx; /* 修改：2px → 4rpx */
	}
	.nav-label {
	  font-size: 24rpx; /* 修改：12px → 24rpx */
	  opacity: 0.9;
	}
	
	/* 中间凸起的主页按钮 */
	.nav-center {
	  position: absolute;
	  bottom: 0;
	  left: 50%;
	  transform: translateX(-50%);
	  width: 128rpx; /* 修改：64px → 128rpx */
	  height: 128rpx; /* 修改：64px → 128rpx */
	  border-radius: 50%;
	  background: #0b2925;
	  border: 4rpx solid #fff; /* 修改：2px → 4rpx */
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  top: -40rpx; /* 修改：-20px → -40rpx */
	  cursor: pointer;
	}
	.home-icon {
	  width: 80rpx; /* 修改：40px → 80rpx */
	  height: 80rpx; /* 修改：40px → 80rpx */
	}
</style>