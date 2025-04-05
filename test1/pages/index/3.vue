<template>
  <view class="container multicolor-bg">
    <!-- 顶部区域 -->

    <header>
		<view>
		  <top-bar logo-url="/images/logo.png" />
		</view>
		<view class="top-bar">
			<view class="top-left">
				<view class="main-title">家电</view>

			</view>
			<view class="top-right">
				<view class="tips">共4个设备</view>
			</view>
		</view>
			
		
    </header>

    <!-- 主体内容：家电卡片列表 -->
    <main class="main-content">
      <ul class="device-list">
        <li
          v-for="(device, index) in devices"
          :key="index"
          class="device-item"
        >
          <view class="icon-box">
            <!-- 替换为你的图标或图片路径 -->
            <img src="/images/device1.png"  alt="icon" class="device-icon" />
          </view>
          <view class="device-info">
            <view class="device-name">{{ device.name }}</view>
			</view>
            <view class="device-meta">
              <view class="location">位置：{{ device.location }}</view>
              <view class="status">状态：{{ device.status }}</view>
            </view>
        </li>
		<!-- 添加一个加号按钮 -->
      </ul>
	  <li class="add-device" @click="onAddDevice">
	    <view>
	      +
	  	</view>
	  </li>
    </main>

	<view>
		<BottomBar />
		
	</view>

  </view>
</template>

<script>
import TopBar from '@/pages/bar/topbar.vue'
import BottomBar from '@/pages/bar/bottombar.vue'


export default {
  name: "AppliancePage",
  
  components: {
      TopBar,
	  BottomBar
	},
	
  data() {
    return {
      devices: [
        {
          name: "电视",
          location: "客厅",
          status: "已接电"
        },
        {
          name: "空调",
          location: "卧室",
          status: "已接电"
        },
        {
          name: "冰箱",
          location: "厨房",
          status: "已接电"
        },
        {
          name: "音响",
          location: "客厅",
          status: "已接电"
        },
      ],
    };
  },
  methods: {
    onNav(item) {
      // 这里可以根据实际需要跳转路由或执行其他操作
      alert(`点击了：${item}`);
    },
  },
};
</script>

<style scoped>
/* 整体容器：可使用渐变或纯色背景 */
.container {
  width: 100%;
  height: 100vh;
  background: linear-gradient(135deg, #081f1c 0%, #0a2c32 100%);
  
  display: flex;
  flex-direction: column;
  color: #fff;
  font-family: sans-serif;
  overflow: hidden; 
}


.top-bar {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  /* 上：24rpx, 右：32rpx, 下：24rpx, 左：32rpx */
  padding: 30rpx 32rpx 20rpx 32rpx;

}

.top-left {
  display: flex;
  flex-direction: column;
  max-width: 70%;
}
.main-title {
  font-size: 40rpx; /* 修改：20px → 40rpx */
  font-weight: bold;
  margin-bottom: 12rpx; /* 修改：6px → 12rpx */
}
.sub-text {
  font-size: 24rpx; /* 修改：12px → 24rpx */
  opacity: 0.8;
  line-height: 1.4;
}

.top-right {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.tips {
  font-size: 24rpx; /* 修改：12px → 24rpx */
  opacity: 0.8;
}

/* 主体内容 */
.main-content {
  flex:1;
  padding: 0 24rpx 24rpx; /* 修改：0 12px 12px → 0 24rpx 24rpx */
}

.device-list {
  list-style: none; /* 修复拼写错误：ist-style → list-style */
  margin: 0;
  padding: 0;
}

.device-item {
  display: flex;
  align-items: center;
  
  /* 基础背景色（建议带透明度） */
  background: rgba(255, 255, 255, 0.04);
  
  backdrop-filter: blur(40rpx);           /* 标准属性 */
  -webkit-backdrop-filter: blur(40rpx);   /* iOS/Safari 兼容 */
  
  border-radius: 40rpx;
  margin-bottom: 40rpx;
  padding: 24rpx;
  overflow: hidden; /* 防止子元素溢出破坏模糊效果 */
}

/* 伪元素增强效果（可选） */
.device-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: inherit;
  filter: blur(140rpx);
  z-index: -1;
  opacity: 0.8;
}

.icon-box {
  width: 120rpx; /* 修改：60px → 120rpx */
  height: 134rpx; /* 修改：67px → 134rpx */
  border-radius: 20rpx; /* 修改：10px → 20rpx */
  background: rgba(255, 255, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 120rpx; /* 修改：60px → 120rpx */
}

.device-icon {
  width: 100rpx; /* 修改：50px → 100rpx */
  height: 80rpx; /* 修改：40px → 80rpx */
  margin-left: 40rpx; /* 修改：20px → 40rpx */
}

.device-info {
  display: flex;
  flex-direction:row;
}

.device-name {
  font-size: 52rpx; /* 修改：26px → 52rpx */
  font-weight: bold;
  margin-bottom: 10rpx; /* 修改：5px → 10rpx */
  color: #ffffff;
  margin-left: 40rpx; /* 修改：20px → 40rpx */
}

.device-meta {
  display: flex;
  gap: 12rpx; /* 修改：6px → 12rpx */
  font-size: 20rpx; /* 修改：10px → 20rpx */
  color: rgba(255, 255, 255, 0.7);
  opacity: 0.8;
  flex-direction:column ;
  margin-left: 100rpx; /* 修改：50px → 100rpx */
}

/* 加号按钮的样式 */
.add-device{
  background: rgb(40, 230, 163);
  width: 200rpx; /* 修改：100px → 200rpx */
  height: 94rpx; /* 修改：47px → 94rpx */
  border-radius: 20rpx; /* 修改：10px → 20rpx */
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}

.add-sign {
  font-size: 64rpx; /* 修改：32px → 64rpx */
  color: #696969;
  line-height: 2;
}


</style>