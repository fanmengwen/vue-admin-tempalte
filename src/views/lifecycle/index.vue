<!--
 * @Author: fanmw
 * @Date: 2022-03-23 15:55:22
 * @Description:
-->
<template>
  <div class="dashboard-container">
    <h2 v-text="n"></h2>
    <h2>当前的n值是：{{ n }}</h2>
    <button @click="add">点我n+1</button>
    <button @click="bye">点我销毁vm</button>
  </div>
</template>

<script>

export default {
  name: 'Dashboard',

  data: () => {
    return {
      n: 1
    }
  },
  watch: {
    n() {
      console.log('n变了')
    }
  },

  beforeCreate() { console.log('beforeCreate') },
  created() { console.log('created') },
  beforeMount() { console.log('beforeMount') },
  mounted() {
    console.log('mounted')
    // 发送ajax请求，绑定自定义事件，启动定时器。
  },
  beforeUpdate() {
    console.log('beforeUpdate')
    // 清楚定时器，解绑事件
  },
  updated() { console.log('updated') },
  beforeDestroy() { console.log('beforeDestroy') },
  destroyed() { console.log('destroyed') },
  methods: {
    add() {
      console.log('add')
      this.n++
    },
    bye() {
      console.log('bye')
      this.$destroy()
      // 销毁后自定义事件失效，原生事件有效。
    }
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
