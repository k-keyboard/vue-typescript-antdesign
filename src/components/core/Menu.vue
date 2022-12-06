<template>
  <a-layout-sider v-model:collapsed="collapsed" :trigger="null" collapsible>
    <div class="logo" />
    <a-button @click="collapsed = !collapsed">X</a-button>
    <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
      <a-menu-item key="1">
        <user-outlined />
        <span>nav 1</span>
      </a-menu-item>
      <a-menu-item key="2">
        <video-camera-outlined />
        <span>nav 2</span>
      </a-menu-item>
      <a-menu-item key="3">
        <upload-outlined />
        <span>nav 3</span>
      </a-menu-item>
    </a-menu>
  </a-layout-sider>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  props: ["collapsed"],
  setup(props, { emit }) {
    const selectedKeys = ref(0);
    const toggleCollapse = () => {
      emit("update:collapsed", !props.collapsed);
    };
    return {
      toggleCollapse,
      selectedKeys,
    };
  },
});
</script>
