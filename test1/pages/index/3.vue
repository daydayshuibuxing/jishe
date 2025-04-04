<template>
  <div class="container">
    <!-- 顶部区域 -->
    <header class="top-bar">
      <div class="top-left">
        <div class="main-title">家电</div>
        
      </div>
      <div class="top-right">
        <div class="date">2025-03-03</div>
        <div class="tips">共4个设备</div>
      </div>
    </header>

    <!-- 主体内容：家电卡片列表 -->
    <main class="main-content">
      <ul class="device-list">
        <li
          v-for="(device, index) in devices"
          :key="index"
          class="device-item"
        >
          <div class="icon-box">
            <!-- 替换为你的图标或图片路径 -->
            <img src="/images/device1.png"  alt="icon" class="device-icon" />
          </div>
          <div class="device-info">
            <div class="device-name">{{ device.name }}</div>
			</div>
            <div class="device-meta">
              <div class="location">位置：{{ device.location }}</div>
              <div class="status">状态：{{ device.status }}</div>
            </div>
        </li>
		<!-- 添加一个加号按钮 -->
		        <li class="device-item add-device" @click="onAddDevice">
		          <div class="icon-box green-box">
		            <div class="add-sign">+</div>
					</div>
		        </li>
		
      </ul>
    </main>


    <!-- 底部导航栏 -->
    <nav class="bottom-nav">
      <div class="nav-item" @click="onNav('照明')">
        <img src="/images/灯泡.png" alt="icon" class="nav-icon" />
        <div class="nav-label">照明</div>
      </div>
      <div class="nav-item" @click="onNav('安防')">
        <img src="/images/监控3.png" alt="icon" class="nav-icon" />
        <div class="nav-label">安防</div>
      </div>

      <!-- 中间凸起的主页按钮 -->
      <div class="nav-center" @click="onNav('首页')">
        <img src="https://via.placeholder.com/40" alt="home" class="home-icon" />
      </div>

      <div class="nav-item" @click="onNav('家电')">
        <img src="/images/家.png" alt="icon" class="nav-icon" />
        <div class="">家电</div>
      </div>
      <div class="nav-item" @click="onNav('成员')">
        <img src="/images/成员1.png" alt="icon" class="nav-icon" />
        <div class="nav-label">成员</div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "AppliancePage",
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
  background: linear-gradient(135deg, #0b2925 0%, #0d3b38 100%);
  display: flex;
  flex-direction: column;
  color: #fff;
  font-family: sans-serif;
  overflow: hidden; /* 防止内部滚动时出现外层滚动条 */
}

/* 顶部区域 */
.top-bar {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  padding: 12px;
}

.top-left {
  display: flex;
  flex-direction: column;
  max-width: 70%;
}
.main-title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 6px;
}
.sub-text {
  font-size: 12px;
  opacity: 0.8;
  line-height: 1.4;
}

.top-right {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.date {
  font-size: 14px;
  margin-bottom: 4px;
}
.tips {
  font-size: 12px;
  opacity: 0.8;
}

/* 主体内容 */
.main-content {
  flex:1;
  padding: 0 12px 12px;
}

.device-list {
  ist-style: none;
    margin: 0;
    padding: 0;
}

.device-item {
  display: flex;
  align-items: center;
  background: rgba(255, 255, 255, 0.06);
  border-radius: 20px;
  margin-bottom: 10px;
  padding: 12px;
}

.icon-box {
  width: 60px;
  height: 67px;
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 60px;
}

.device-icon {
  width: 50px;
  height: 40px;
  margin-left: 20px;
}

.device-info {
  display: flex;
  flex-direction:row;
}

.device-name {
  font-size: 26px;
  font-weight: bold;
  margin-bottom: 5px;
  color: #ffffff;
   margin-left: 20px;

}

.device-meta {
  display: flex;
  gap: 6px;
  font-size: 10px;
  color: rgba(255, 255, 255, 0.7);
  opacity: 0.8;
  flex-direction:column ;
 margin-left: 50px; 
}
/* 加号按钮的样式 */
.add-device .icon-box {
  background: #3CB371;
}
.add-sign {
  font-size: 32px;
  color: #696969;
  line-height: 2;
}
/* 底部导航栏 */
.bottom-nav {
  position: fixed;  /* 改为固定定位 */
  bottom: 0;        /* 固定在底部 */
  left: 0;          /* 左侧对齐 */
  width: 100%;      /* 撑满宽度 */
  height: 60px;
  background: #102522;
  display: flex;
  border-radius: 20px;
  align-items: center;
  justify-content: space-around;
  z-index: 10;     /* 确保导航栏在最上层 */
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
  width: 24px;
  height: 24px;
  margin-bottom: 2px;
}
.nav-label {
  font-size: 12px;
  opacity: 0.9;
}

/* 中间凸起的主页按钮 */
.nav-center {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 64px;
  height: 64px;
  border-radius: 50%;
  background: #0b2925;
  border: 2px solid #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  top: -20px; /* 使其凸起 */
  cursor: pointer;
}
.home-icon {
  width: 40px;
  height: 40px;
}
</style>
