<template>
  <a-config-provider
    :theme="{ token: { colorPrimary: '#0f9b8e', borderRadius: 10, fontSize: 14 } }"
  >
  <div id="app">
    <a-layout style="min-height: 100vh; background: #f4f8f7">
      <a-layout-header class="app-header">
        <div class="header-content">
          <div class="logo">
            <span class="logo-icon">✨</span>
            <span class="logo-text">TripFlow</span>
          </div>
          <div class="header-subtitle">你的智能出行规划师</div>
        </div>
      </a-layout-header>
      <a-layout-content style="padding: 40px 24px; max-width: 1400px; margin: 0 auto; width: 100%">
        <router-view />
      </a-layout-content>
      <a-layout-footer style="text-align: center; background: linear-gradient(135deg, #0f9b8e 0%, #0b5d6b 100%); color: white; padding: 24px">
        <div style="margin-bottom: 8px">TripFlow © 2025</div>
        <div style="font-size: 12px; opacity: 0.9">打造每一次完美的旅程</div>
      </a-layout-footer>
    </a-layout>
  </div>
  </a-config-provider>
</template>

<script setup lang="ts">
</script>

<style>
#app {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial,
    'Noto Sans', sans-serif;
}

.app-header {
  background: linear-gradient(135deg, #0f9b8e 0%, #0b5d6b 100%) !important;
  padding: 16px 50px !important;
  box-shadow: 0 2px 12px rgba(15, 155, 142, 0.15);
  position: sticky;
  top: 0;
  z-index: 100;
}

.header-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  display: flex;
  align-items: center;
  gap: 12px;
  color: white;
}

.logo-icon {
  font-size: 32px;
}

.logo-text {
  font-size: 26px;
  font-weight: bold;
  letter-spacing: 1px;
}

.header-subtitle {
  color: rgba(255, 255, 255, 0.9);
  font-size: 12px;
  font-weight: 500;
  letter-spacing: 0.5px;
}
</style>

