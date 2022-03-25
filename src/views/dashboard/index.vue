<!--
 * @Author: fanmw
 * @Date: 2022-03-23 15:55:22
 * @Description:
-->
<template>
  <div class="dashboard-container">
    <!-- <div class="dashboard-text">name: {{ name }}</div> -->
    <!-- <button @click="updateMei">更新马冬梅的信息</button>
    <input v-model="keyword">
    <button @click="sortType = 0">升序</button>
    <button @click="sortType = 1">降序</button>
    <ul>
      <li v-for="(val,index) of filPersons" :key="val.id">
        {{ val.name }} -- {{ index }}
      </li>
    </ul> -->
    <h2>{{ name }}</h2>
    <h2>当前的n值是：<span v-text="n"></span> </h2>
    <!-- <h2>放大10倍后的n值是：<span v-big-number="n"></span> </h2> -->
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  data: () => {
    return {
      n: 1,
      userInfo: {
        account: '',
        password: '',
        age: 18,
        sex: 'female',
        hobby: [],
        city: 'beijing',
        other: '',
        agree: ''
      }
    }
  },
  computed: {
    ...mapGetters([
      'name'
    ]),
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
