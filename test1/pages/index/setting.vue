<template>
  

    <!-- Logo Section -->
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
    <view class="settings-container">
    <!-- Title -->
    <h1 class="title">设置</h1>

    <!-- Settings Options -->
    <view class="options">
      <view class="option">
        <img src="/static/images/语音2.svg" alt="麦克风图标" class="icon-image" />
        <span class="text">语音设置</span>
      </view>
      <view class="option">
         <img src="/static/images/061_信件.svg" alt="建议图标" class="icon-image" />
        <span class="text">反馈与建议</span>
      </view>
      <view class="option">
        <img src="/static/images/退出.svg" alt="退出图标" class="icon-image" />
        <span class="text">退出登录</span>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: "Settings",
};
</script>

<style scoped>
/* General Styles */
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(
      165deg, 
      #0f2027 20%, 
      #203a43 50%, 
      #2c5364 100%
    );
	background-size: cover; /* 确保背景覆盖整个容器 */
	  background-attachment: fixed; /* 背景随页面固定 */
  color: white;
}

/* Container */
.settings-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 28rpx;
  height: 100vh;
  box-sizing: border-box;
}

/* Header */
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
/* Title */
.title {
  font-size: 24px;
  margin: 3px 0;
text-align: left;
align-self: flex-start;
margin-left: 10px; 
}

/* Options */
.options {
  width: 100%;
}

.option {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  margin: 10px 0;
  padding: 15px 20px;
  cursor: pointer;
  transition: background 0.3s;

}


.option:hover {
  background: rgba(255, 255, 255, 0.2);
}
.icon-image{
	width: 30px; /* 设置图片宽度 */
	  height: 30px; /* 设置图片高度 */
	  margin-right: 8px; /* 图片与文本之间的间距 */
}

.icon {
  font-size: 20px;
   font-weight: bold;
}

.text {
  font-size: 16px;
}
</style>