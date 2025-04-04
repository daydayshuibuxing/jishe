<template>
  <div class="p-6 bg-gray-100 min-h-screen">
    <h1 class="text-3xl font-bold mb-8 text-gray-800">房间设备统计</h1>
    
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <!-- 客厅 -->
      <div class="bg-white rounded-xl p-6 shadow-lg transition-transform hover:scale-105">
        <div class="flex items-center mb-4">
          <div class="w-3 h-8 bg-blue-500 rounded-full mr-3"></div>
          <h2 class="text-xl font-semibold text-gray-700">客厅</h2>
        </div>
        <div class="flex items-center text-gray-600">
          <svg class="w-5 h-5 mr-2 text-blue-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>
          </svg>
          <span class="text-2xl font-bold text-blue-600">4</span>
          <span class="ml-2">个设备</span>
        </div>
      </div>

      <!-- 厨房 -->
      <div class="bg-white rounded-xl p-6 shadow-lg transition-transform hover:scale-105">
        <div class="flex items-center mb-4">
          <div class="w-3 h-8 bg-green-500 rounded-full mr-3"></div>
          <h2 class="text-xl font-semibold text-gray-700">厨房</h2>
        </div>
        <div class="flex items-center text-gray-600">
          <svg class="w-5 h-5 mr-2 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"/>
          </svg>
          <span class="text-2xl font-bold text-green-600">2</span>
          <span class="ml-2">个设备</span>
        </div>
      </div>

      <!-- 其他房间模板（卧室、书房、厕所） -->
      <!-- 复制上述模板修改颜色和数值即可 -->
      <!-- 颜色建议：卧室用紫色、书房用黄色、厕所用橘色 -->
    </div>
  </div>
</template>

<script setup>
// 响应式数据
const rooms = [
  { name: '客厅', count: 4, color: 'blue' },
  { name: '厨房', count: 2, color: 'green' },
  { name: '卧室', count: 3, color: 'purple' },
  { name: '书房', count: 3, color: 'yellow' },
  { name: '厕所', count: 3, color: 'orange' }
]
</script>

<style>
/* 自定义动画 */
.transition-transform {
  transition: transform 0.3s ease;
}
</style>