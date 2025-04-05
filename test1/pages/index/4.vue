<template>
  <view class="app">
    <!-- Header -->
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

    <!-- Profile Section -->
 <view class="welcome-message">
     <h1>小明，欢迎回家~</h1>
   </view>
    <view class="profile">
      <view class="profile-container">
        <view class="avatar">
          <img
     src="/static/images/头像 女孩.svg" 
     class="avatar-placeholder1"
     alt="用户头像">
     
        </view>
        <view class="profile-content">
          
          <view class="account-info">
            <p>账号：0001</p>
            <p>成员：儿子</p>
          </view>
        </view>
  <button class="edit-profile">
    <img src="/images/编辑.png" class="edit-icon"> 
    编辑个人资料
  </button>
      </view>
    </view>

    <!-- Operation Logs -->
    <section class="logs">
      <h2>操作日志</h2>
      <view class="log-item" v-for="(log, index) in logs" :key="index">
        <view class="log-avatar">
          <img src="/static/images/妈妈.svg"
     alt="用户头像" 
     class="avatar-placeholder2">
        </view>
        <view class="log-details">
          <p>时间：{{ log.time }}</p>
          <p>成员：{{ log.member }}</p>
          <p>操作：{{ log.action }}</p>
        </view>
        <view class="log-number">{{ index + 1 }}</view>
      </view>
      <button class="view-more">查看更多...</button>
    </section>

    <!-- Footer Navigation -->

      <view class="nav-item settings-box"> <!-- 新增样式类 -->
        <image 
            src="/static/images/设置.svg" 
            class="settings-icon" 
            mode="aspectFit"
          />
        <text class="settings-text">设置</text>
      </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      logs: [
        {
          time: "21:20 2025-3-17",
          member: "妈妈",
          action: "将客厅主灯亮度调整至档",
        },
        {
          time: "20:06 2025-3-17",
          member: "爸爸",
          action: "通过人脸认证开门",
        },
        {
          time: "19:30 2025-3-17",
          member: "妈妈",
          action: "将书房窗帘关闭",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* General Styles */
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: RGB(20,42,37);
  color: #fff;
}
.app {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

/* Header */
.header {
	  padding: 16rpx;     /* 保持原有内边距 */
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20rpx 30rpx;
  background: RGB(19,41,37);
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

/* Profile Section */
.profile {
 padding: 20rpx 15rpx;
  padding-top: 15rpx; 
  background: rgba(30, 53, 48, 0.08);
  border-radius: 40rpx;
   margin: 20rpx 10rpx;
  margin-right: 12rpx;
  margin-left: 12rpx;
}
.profile-container {
  display: flex;
  position: relative;
  align-items: center;
  border-radius: 30rpx;
  background: RGB(32,57,52);
  height: 220rpx;
}
.avatar-placeholder1 {
  width: 180rpx;
    height: 180rpx;
  border-radius: 50%;
  position: absolute;
  top: -110rpx; 
   left: 9%;
 }
.profile-content {
  flex: 1;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-left: 490rpx;
  color: rgba(255, 255, 255, 0.4);
  font-size: 18rpx;
}
.welcome-message h1 {
  margin: 10rpx;
  margin-left: 300rpx;
  font-size: 40rpx;
  font-weight: bold;
  background: RGB(20,42,37);
}
.account-info p {
  margin: 30rpx 0;
  font-size: 30rpx;
}
.edit-icon {
  width: 25rpx;
  height: 25rpx;
  margin-right: 6rpx; /* 图片和文字的间距 */
  vertical-align: middle;
}
.edit-profile {
  margin-top: 120rpx;
  margin-bottom: 8rpx;
  padding: 2rpx 50rpx;
  background: #1a6c6c;
  border: none;
  color: #fff;
  border-radius: 30rpx;
  cursor: pointer;
  font-size: 20rpx;
  position: absolute;
  left:30rpx;
  background: rgba(26, 108, 108, 0.2);
  border: 1rpx solid rgba(128, 128, 128, 0.5);
}

/* Logs Section */
.logs {
  flex: 1;
  padding: 25rpx;
  background:RGB(20,42,37);
}
.log-item {
  display: flex;
  align-items: center;
  margin-bottom: 20rpx;
  padding: 20rpx;
  background: RGB(44,59,56);
  border-radius: 50%;
  border-radius: 25rpx;
}
.log-avatar .avatar-placeholder2 {
  width: 80rpx;
  height: 80rpx;
  background: RGB(44,59,56);
  border-radius: 50%;
  margin-right: 30rpx;
  margin-left: 30rpx;
}
.log-details p {
  margin: 10rpx 0;
  line-height: 1.7;/* 减少行高（默认通常是 1.4-1.6） */
  font-size: 20rpx;
  padding-left: 57rpx;
  opacity: 0.5; 
}
.log-number {
  margin-left: auto;
  font-size: 55rpx;
  color: #1a6c6c;
}
.view-more {
  display: block;
  margin: 0 auto;
  padding: 1rpx 16rpx;
  background: RGB(44,59,56);
  opacity: 0.7; 
  border: none;
  color: #fff;
  border-radius: 40rpx;
  font-size: 20rpx;
  cursor: pointer;
}

/* Footer Navigation */

/* 新增样式 */
.settings-box {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  padding: 16rpx 16rpx;
  background: RGB(44,59,56);
  font-size: 20rpx;
  border-radius: 40rpx;
  height: 100rpx;
margin: 0 30rpx;
}


.settings-icon {
  width: 50rpx;
    height: 50rpx;
    margin-right: 20rpx;
  
}

.settings-text {
  font-size: 30rpx; /* 文字大小 */
  color: #fff;
  white-space: nowrap; 
}

.nav-item {
  text-align: center;
  color: #fff;
}
.nav-item.active {
  color: #1a6c6c;
}
.nav-item.settings {
  margin-left: auto;
}
.icon {
  display: block;
  font-size: 24px;
}
</style>