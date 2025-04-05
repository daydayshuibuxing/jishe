<template>
  <view class="container">
    <!-- 顶部导航栏 -->
    <header class="header">
      <view class="logo">
        <image 
          src="/static/images/未标题-2_画板 1.png" 
          class="app-logo"
          mode="aspectFit"
        />
      </view>
       <view class="date">
         <img src="/static/images/日历.svg" alt="图标" style="vertical-align: middle; width:28rpx; height:28rpx;">
         2025-03-03
       </view>
    
    </header>
    <!-- 门禁记录查询 -->
    <view class="section">
      <view class="section-header">
        <text class="section-title">门禁记录查询</text>
      </view>
      <view class="record-list">
        <view class="record-item" v-for="(record, index) in accessRecords" :key="index">
          <view class="record-avatar">
            <img src="/static/images/妈妈.svg" alt="Avatar" class="avatar-placeholder2">
          </view>
          <view class="record-details">
            <p>时间：{{ record.time }}</p>
             <p>成员：{{ record.member }}</p>
            <p>认证方式：{{ record.method }}</p>
          </view>
          <view class="record-number">{{ index + 1 }}</view>
        </view>
		<button class="view-more">查看更多...</button>
      </view>
    </view>

    <!-- 监控 -->
    <view class="section">
      <view class="section-header">
        <text class="section-title">监控</text>
        <text class="device-count">共3个设备</text>
      </view>
      
        <view class="camera-item" v-for="(camera, index) in cameras" :key="index">
          <view class="camera-info">
            <text class="camera-name">{{ camera.name }}</text>
            <text class="camera-location">位置：{{ camera.location }}</text>
          </view>
          <view class="camera-preview">
            <img :src="camera.preview" alt="Camera Preview" />
          </view>
        </view>
    </view>

    
  </view>
</template>

<script>
export default {
  data() {
    return {
      accessRecords: [
        {
          time: '20:06 2025-3-17',
          member: '爸爸',
          method: '人脸'
        },
        {
          time: '17:20 2025-3-17',
          member: '儿子',
          method: 'NFC'
        },
        {
          time: '12:30 2025-3-17',
          member: '未知',
          method: '未认证'
        }
      ],
      cameras: [
        {
          name: '01摄像头',
          location: '客厅',
          preview: '/static/images/客厅.png'
        },
        {
          name: '02摄像头',
          location: '厨房',
          preview: '/static/images/厨房.png'
        }
      ]
    };
  }
};
</script>

<style>
/* 全局样式 */
.container {
  background: linear-gradient(
      165deg, 
      #0f2027 20%, 
      #203a43 50%, 
      #2c5364 100%
    );
  	background-size: cover; /* 确保背景覆盖整个容器 */
  	  background-attachment: fixed; /* 背景随页面固定 */
  color: #fff;
  padding: 35rpx;
  box-sizing: border-box;
}

/* 顶部导航栏 */
.header {    /* 保持原有内边距 */
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  width: 95%; 
  padding: 2rpx 8rpx;
}
.logo {
  
}
.app-logo{
	width: 150rpx;
	 height: 150rpx;
	
}
.date {
  font-size: 28rpx;
  opacity: 0.4;
}
/* 门禁记录查询 */
.section {
 flex: 1;
   padding: 10rpx;
   
}

.section-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20rpx;
}

.section-title {
  font-size: 40rpx;
  font-weight: bold;
}

.record-list {
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 25rpx;
  padding: 8rpx;
  margin: 1rpx 0rpx;
}

.record-item {
 display: flex;
   align-items: center;
   margin-bottom: 20rpx;
   padding: 20rpx;
   background: RGB(44,59,56,0.3);
   border: 1rpx solid rgba(255,255,255,0.1);
   border-radius: 25rpx;
}
.record-item:hover {
  border-color: rgba(255,255,255,0.3);
  transform: translateY(-2rpx);
}

.record-avatar .avatar-placeholder2 {
 width: 80rpx;
   height: 80rpx;
   background: RGB(44,59,56);
   border-radius: 50%;
   margin-right: 30rpx;
   margin-left: 30rpx;
}


.record-details p{
margin: 10rpx 0;
  line-height: 1.7;/* 减少行高（默认通常是 1.4-1.6） */
  font-size: 20rpx;
  padding-left: 57rpx;
  opacity: 0.5; 
}




.record-number {
  margin-left: auto;
    font-size: 55rpx;
    color: #1a6c6c;
}

.view-more {
  display: block;
  margin: 0 auto;
  padding: 1rpx 16rpx;
  background: RGB(44,59,56,0.3);
  border: 1rpx solid rgba(255,255,255,0.1);
  opacity: 0.7; 
  border: none;
  color: #fff;
  border-radius: 40rpx;
  font-size: 20rpx;
  cursor: pointer;
}

/* 监控 */
.camera-list {
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 25rpx;
  padding: 15rpx;
  margin: 1rpx 0rpx;
}

.camera-item {
  display: flex;
    align-items: center;
    margin-bottom: 20rpx;
    padding: 20rpx;
    background: RGB(44,59,56,0.3);
    border: 1rpx solid rgba(255,255,255,0.1);
    border-radius: 20rpx;
	width: 94%;  /* 原100px */
	  height: 200rpx; /* 原70px */
}

.camera-item:last-child {
  border-bottom: none;
}

.camera-info {
  flex: 1;
  display: flex;
  flex-direction: column;    /* 垂直排列 */
    align-items: flex-start;   /* 水平左对齐 */
    justify-content: flex-start; /* 垂直顶对齐（默认也是 start） */
	padding-left: 40rpx;
}

.camera-name {
  font-size: 60rpx;
  font-weight: bold;
  margin-bottom: 5rpx;
}

.camera-location {
  font-size: 23rpx;
  color: rgba(255, 255, 255, 0.7);
}

.camera-preview {
  width: 250rpx;
  height: 180rpx;
  border-radius: 40rpx;
  overflow: hidden;
}

.camera-preview img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* 底部导航栏 */

</style>