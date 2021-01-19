<template>
  <h2>setup和ref的基本使用</h2>
  <h3>{{ count }}</h3>
  <button @click="updateCount">更新数据</button>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "App",
  // 需求： 点击按钮数据变化
  // vue2的实现
  /*data: () => ({
    count: 0
  }),
  methods: {
    updateCount() {
      this.count++;
    }
  }*/
  // vue3的实现
  // setup是组合api的入口函数
  setup() {
    // 这里的count是一个ref对象
    // ref一般用来定义基本类型的响应式数据
    const count = ref(0);
    function updateCount() {
      // 对象不能直接进行++操作
      count.value++;
    }
    return {
      count,
      updateCount
    };
  }
});
</script>

<style lang="scss"></style>
