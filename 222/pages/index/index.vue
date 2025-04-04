<template>
  <div class="container">
    <!-- 顶部区域 -->
    <header class="top-bar">
      <div class="logo-and-date">
        <div class="logo-text">聪创家</div>
        <div class="date">2025-03-03</div>
      </div>
      <div class="room-title">
        <div class="title">房间</div>
        <div class="subtitle">5个房间，共4个设备</div>
      </div>
    </header>

    <!-- 主体内容：房间列表 -->
    <main class="main-content">
      <ul class="room-list">
        <li v-for="(room, index) in rooms" :key="index" class="room-item">
          <img :src="room.image" alt="room" class="room-img" />
          <div class="room-info">
            <div class="room-name">{{ room.name }}</div>
            <div class="room-devices">共{{ room.devices }}个设备</div>
          </div>
        </li>
      </ul>
    </main>

    <!-- 底部导航栏 -->
    <nav class="bottom-nav">
      <div class="nav-item" @click="onNav('照明')">
        <!-- 替换为你的图标路径 -->
        <img src="https://via.placeholder.com/24" alt="icon" class="nav-icon" />
        <div class="nav-label">照明</div>
      </div>
      <div class="nav-item" @click="onNav('安防')">
        <img src="https://via.placeholder.com/24" alt="icon" class="nav-icon" />
        <div class="nav-label">安防</div>
      </div>

      <!-- 中间凸起的主页按钮 -->
      <div class="nav-center" @click="onNav('首页')">
        <!-- 替换为你的“首页”图标 -->
        <img src="https://via.placeholder.com/40" alt="home" class="home-icon" />
      </div>

      <div class="nav-item" @click="onNav('家电')">
        <img src="https://via.placeholder.com/24" alt="icon" class="nav-icon" />
        <div class="nav-label">家电</div>
      </div>
      <div class="nav-item" @click="onNav('成员')">
        <img src="https://via.placeholder.com/24" alt="icon" class="nav-icon" />
        <div class="nav-label">成员</div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "RoomPage",
  data() {
    return {
      rooms: [
        {
          name: "客厅",
          devices: 4,
          image: "https://via.placeholder.com/100x100?text=%E5%AE%A2%E5%8E%85"
        },
        {
          name: "厨房",
          devices: 2,
          image: "https://via.placeholder.com/100x100?text=%E5%8E%A8%E6%88%BF"
        },
        {
          name: "卧室",
          devices: 3,
          image: "https://via.placeholder.com/100x100?text=%E5%8D%A7%E5%AE%A4"
        },
        {
          name: "书房",
          devices: 3,
          image: "https://via.placeholder.com/100x100?text=%E4%B9%A6%E6%88%BF"
        },
        {
          name: "厕所",
          devices: 1,
          image: "https://via.placeholder.com/100x100?text=%E5%8E%95%E6%89%80"
        }
      ]
    };
  },
  methods: {
    onNav(item) {
      // 这里可以根据实际需要跳转路由或执行其他操作
      alert(`点击了：${item}`);
    }
  }
};
</script>

<style scoped>
/* 整体容器：背景可根据需要调整为渐变或纯色 */
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
  padding: 12px;
}
.logo-and-date {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.logo-text {
  font-size: 18px;
  font-weight: bold;
}
.date {
  font-size: 14px;
  opacity: 0.8;
}
.room-title {
  margin-top: 10px;
}
.title {
  font-size: 20px;
  font-weight: bold;
}
.subtitle {
  font-size: 14px;
  opacity: 0.8;
}

/* 主体内容 */
.main-content {
  flex: 1;
  overflow-y: auto; /* 允许房间列表滚动 */
  padding: 0 12px 12px;
}
.room-list {
  list-style: none;
  margin: 0;
  padding: 0;
}
.room-item {
  display: flex;
  align-items: center;
  background: rgba(255, 255, 255, 0.06);
  border-radius: 8px;
  margin-bottom: 10px;
  padding: 10px;
}
.room-img {
  width: 60px;
  height: 60px;
  border-radius: 6px;
  object-fit: cover;
  margin-right: 12px;
}
.room-info {
  display: flex;
  flex-direction: column;
}
.room-name {
  font-size: 16px;
  font-weight: bold;
}
.room-devices {
  font-size: 12px;
  opacity: 0.7;
}

/* 底部导航栏 */
.bottom-nav {
  position: relative;
  height: 60px;
  background: #102522;
  display: flex;
  align-items: center;
  justify-content: space-around;
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
  /* 使其凸起 */
  top: -20px;
  cursor: pointer;
}
.home-icon {
  width: 40px;
  height: 40px;
}
</style>
