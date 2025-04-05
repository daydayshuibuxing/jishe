<!-- components/top-bar/top-bar.vue -->
<template>
  <view class="top-bar">
    <!-- 左侧logo -->
    <image 
      class="logo" 
	  :src="logoUrl" 
      mode="aspectFit"
    ></image>
    
    <!-- 右侧日期 -->
    <text class="date">{{ formattedDate }}</text>
  </view>
</template>

<script>
export default {
  name: 'TopBar',
  props: {
    // logo图片路径
    logoUrl: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      currentDate: new Date()
    };
  },
  computed: {
    // 格式化日期显示
    formattedDate() {
      const options = { year: 'numeric', month: 'long', day: 'numeric' };
      return this.currentDate.toLocaleDateString('zh-CN', options);
    }
  }
};
</script>

<style scoped>
.top-bar {
  /* 固定定位在顶部 */
  top: 0;
  left: 0;
  width: 100%;
  height: 30rpx; /* 根据实际情况调整 */
  display: flex;
  align-items: center; /* 垂直居中 */
  justify-content: space-between; /* 左右分布 */
  z-index: 1000;
}

.logo {
  height: 140rpx; /* 根据实际logo尺寸调整 */
  width: 140rpx; /* 控制logo显示宽度 */
  margin-left: -30rpx;
  margin-top: -40rpx;
}

.date {
  font-size: 10rpx;
  color: rgb(100,106,105);
  margin-right: 45rpx;
}
</style>