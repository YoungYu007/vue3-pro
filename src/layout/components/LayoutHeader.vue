<script lang="ts" setup>
import { ref } from 'vue';

const activeIdx = ref('home');
const menuList = ref([
  { id: 'home', name: '主页' },
  { id: 'test', name: '测试' }
]);

const handleSelect = () => {

};
</script>

<template>
  <el-header class="layout-header">
    <!-- menu panel -->
    <el-menu
      :default-active="activeIdx"
      class="menu-panel"
      mode="horizontal"
      @select="handleSelect"
    >
      <el-menu-item
        v-for="menuItem in menuList "
        :key="menuItem.id"
        :index="menuItem.id"
      >
        {{ menuItem.name }}
      </el-menu-item>

      <el-sub-menu index="2-4">
        <template #title>item four</template>
        <el-menu-item index="2-4-1">item one</el-menu-item>
        <el-menu-item index="2-4-2">item two</el-menu-item>
        <el-menu-item index="2-4-3">item three</el-menu-item>
      </el-sub-menu>
    </el-menu>

    <!-- right panel -->
    <ul class="right-panel">
      <li class="right-item avatar">
        <el-avatar src="https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg"></el-avatar>
      </li>

      <el-dropdown class="right-item message">
        <el-badge :value="12" class="icon-wrap">
          <svg
            class="icon"
            data-v-042ca774
            height="200"
            viewBox="0 0 1024 1024"
            width="200"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M128 224v512a64 64 0 0064 64h640a64 64 0 0064-64V224H128zm0-64h768a64 64 0 0164 64v512a128 128 0 01-128 128H192A128 128 0 0164 736V224a64 64 0 0164-64z"
              fill="currentColor"
            />
            <path
              d="M904 224L656.512 506.88a192 192 0 01-289.024 0L120 224h784zm-698.944 0l210.56 240.704a128 128 0 00192.704 0L818.944 224H205.056z"
              fill="currentColor"
            />
          </svg>

          <span>消息</span>
        </el-badge>
      </el-dropdown>
    </ul>
  </el-header>
</template>

<style lang="scss" scoped>
.layout-header {
  display: flex;

  .menu-panel {
    flex: 1;
  }

  .right-panel {
    min-width: 330px;
    height: 100%;
    display: flex;
    align-items: center;

    .right-item {
      cursor: pointer;

      & + .right-item {
        margin-left: 16px;
      }

      .icon-wrap {
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      .icon {
        width: 1.5em;
        height: 1.5em;
      }
    }
  }
}
</style>
