<template>
  <h2>reactive的使用</h2>
  <h3>名字：{{ user.name }}</h3>
  <h3>年龄：{{ user.age }}</h3>
  <h3>媳妇：{{ user.wife }}</h3>
  <hr />
  <button @click="updateUser">更新数据</button>
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";
export default defineComponent({
  name: "App",
  setup() {
    // 把数据变成响应式的数据
    // 返回的是一个Proxy的代理对象，被代理的目标对象就是reactive中的对象
    const user = reactive({
      name: "小明",
      age: 20,
      wife: {
        name: "小红",
        age: 18,
        cars: ["奔驰", "宝马", "奥迪"]
      }
    });
    const updateUser = () => {
      user.name += "==";
      user.age++;
      user.wife.name = "小兰";
    };

    return { user, updateUser };
  }
});
</script>

<style lang="scss"></style>
