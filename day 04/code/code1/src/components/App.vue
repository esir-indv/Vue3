<template>
    <div class="app-container">
        <h1>这是 <i>App.vue</i> 根组件</h1>

        <hr/>
        <!--    <p class="next" >{{new Date() | dateFormat}}</p>-->
        <p>count值是：{{ count }}</p>
        <button @click="addCount">+1</button>
        <my-header title="信息科技中心" bgcolor="#004" color="#fff"></my-header>
    </div>
</template>

<script>

import MyHeader from './06.MyHeader/MyHeader.vue'
import MyTest from "./01.globalReg/Test.vue";

// 创建全局的过滤器
Vue.filter('dateFormat', (dateStr) => {
    const dt = new Date(dateStr)
    const y = dt.getFullYear()
    const m = padZero(dt.getMonth() + 1)
    const d = padZero(dt.getDate())
    const hh = padZero(dt.getHours())
    const mm = padZero(dt.getMinutes())
    const ss = padZero(dt.getSeconds())
    return `${y}-${m}-${d} ${hh}:${mm}:${ss}`
})

// 补零的函数
function padZero(n) {
    return n > 9 ? n : '0' + n
}

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
