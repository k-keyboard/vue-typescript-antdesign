<template>
  <a-layout style="min-height: 100vh">
    <!-- Menu -->
    <span>{{ collapsed }}</span>
    <Menu v-model:collapsed="collapsed" />
    <a-layout>
      <!-- Header -->
      <Header />
      <!-- Content -->
      <Content />
    </a-layout>
  </a-layout>
</template>
<script lang="ts">
import { defineComponent, ref } from "vue";
import Content from "./components/core/Content.vue";
import Header from "./components/core/Header.vue";
import Menu from "./components/core/Menu.vue";
export default defineComponent({
  components: {
    Menu,
    Header,
    Content,
  },
  setup() {
    return {
      selectedKeys: ref<string[]>(["1"]),
      collapsed: ref<boolean>(false),
    };
  },
});
</script>
<style>
#components-layout-demo-custom-trigger .trigger {
  font-size: 18px;
  line-height: 64px;
  padding: 0 24px;
  cursor: pointer;
  transition: color 0.3s;
}

#components-layout-demo-custom-trigger .trigger:hover {
  color: #1890ff;
}

#components-layout-demo-custom-trigger .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.3);
  margin: 16px;
}

.site-layout .site-layout-background {
  background: #fff;
}
</style>
