<template>
  <view class="container">
    <!-- 天气信息卡片 -->
    <view class="weather-card">
      <text class="weather-title">晴转小雨</text>
      <view class="weather-info">
        <text class="info-item">18℃</text>
        <text class="info-divider">|</text>
        <text class="info-item">45%</text>
        <text class="info-divider">|</text>
        <text class="info-item">7级</text>
      </view>
    </view>

    <!-- 功能按钮区域 -->
	
    <view class="button-group">
		.weather-location {
		    color: rgba(255,255,255,0.8);  // 半透明白色
		    font-size: 30rpx;             // 略小于标题字号
		    display: block;
		    margin-bottom: 12rpx;         // 与标题间距
		  }

      <view class="function-button primary" @click="handleOpenLights">
        <text class="button-text">回家一键开灯</text>
        <text class="button-hotkey">Shortcut: 双击电源键</text>
      </view>

      <view class="function-button warning" @click="handleCloseLights">
        <text class="button-text">离家一键关灯</text>
        <text class="button-hotkey">Shortcut: 三击电源键</text>
      </view>

      <view class="function-button danger" @click="handleEmergencyCutoff">
        <text class="button-text">遇险情一键断电</text>
        <text class="button-hotkey">Shortcut: 长按5秒</text>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  methods: {
    handleOpenLights() {
      uni.showToast({ title: '已开启全屋照明', icon: 'success' })
    },
    handleCloseLights() {
      uni.showModal({
        title: '确认操作',
        content: '确定要关闭所有灯光吗？',
        success: (res) => {
          if (res.confirm) {
            uni.showToast({ title: '灯光已全部关闭' })
          }
        }
      })
    },
    handleEmergencyCutoff() {
      uni.vibrateLong({})
      uni.showActionSheet({
        title: '紧急断电确认',
        itemList: ['立即断电', '取消'],
        success: (res) => {
          if (res.tapIndex === 0) {
            uni.showToast({ title: '已执行紧急断电', icon: 'none' })
          }
        }
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  background-color: #0a0a0a;
  min-height: 100vh;
  padding: 40rpx;
}

.weather-card {
  background: #1a1a1a;
  border-radius: 24rpx;
  padding: 32rpx;
  margin-bottom: 48rpx;
  box-shadow: 0 8rpx 24rpx rgba(0,0,0,0.3);

  .weather-title {
    color: #fff;
    font-size: 44rpx;
    font-weight: bold;
    display: block;
    margin-bottom: 24rpx;
  }

  .weather-info {
    display: flex;
    align-items: center;
    
    .info-item {
      color: #00ff88;
      font-size: 36rpx;
      font-family: DIN Alternate;
    }

    .info-divider {
      color: #666;
      margin: 0 24rpx;
    }
  }
}

.button-group {
  display: grid;
  gap: 32rpx;

  .function-button {
    border-radius: 16rpx;
    padding: 36rpx;
    transition: all 0.3s;
    
    &.primary {
      background: linear-gradient(135deg, #007AFF, #0044ff);
      border: 1px solid rgba(0,122,255,0.5);
    }

    &.warning {
      background: linear-gradient(135deg, #ff9500, #ff5500);
      border: 1px solid rgba(255,149,0,0.5);
    }

    &.danger {
      background: linear-gradient(135deg, #ff3b30, #ff0d00);
      border: 1px solid rgba(255,59,48,0.5);
    }

    &:active {
      transform: scale(0.98);
      opacity: 0.9;
    }

    .button-text {
      color: #fff;
      font-size: 36rpx;
      font-weight: 500;
      display: block;
      margin-bottom: 16rpx;
    }

    .button-hotkey {
      color: rgba(255,255,255,0.8);
      font-size: 24rpx;
      opacity: 0.8;
    }
  }
}
</style>