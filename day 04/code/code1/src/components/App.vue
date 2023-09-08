<template>
  <div class="app-container">
      <h1>这是 <i>App.vue</i> 根组件</h1>

    <hr>
    <hr />
    <h3>姓名 --- {{ username }}</h3>
    <hr />
    <p>count值是：{{ count }}</p>
    <button @click="addCount">+1</button>

    <my-header title="信息科技中心" bgcolor="#000" color="#fff"></my-header>
    <MyTest></MyTest>

  </div>
</template>

<script>
import MyHeader from './06.MyHeader/MyHeader.vue'
import MyTest from "./01.globalReg/Test.vue";

export default {
  name: 'MyApp',
  data() {
    return {
        username: 'zs',
        count: 0,
    }
},
  methods: {
    addCount() {
        this.count++
    },
},
  components: {
    MyTest,
    MyHeader,
  },
}
</script>

<style lang="less" scoped>
.app-container {
  margin-top: 85px;
}

h1 {
    color: #1be16a;
    i {
        color: rgba(255, 204, 0, 0.87);
    }
}
</style>
