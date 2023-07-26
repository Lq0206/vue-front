<!--
 * @Author: lqi 575920678@qq.com
 * @Date: 2023-07-26 14:12:27
 * @LastEditors: lqi 575920678@qq.com
 * @LastEditTime: 2023-07-26 15:30:15
 * @FilePath: /CICD/vue-front/src/App.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
<ul>
  <li v-for="(item, idx) in users" :key='idx'>{{item.name}}</li>
</ul>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data() {
    return {
      users: []
    }
  },
  mounted() {
    axios.get('http://localhost:8001/api/user').then(res => {
      this.users = res.data
    })
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
