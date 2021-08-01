<template>
  <div class="home">
    <el-select v-model="curPage" placeholder="请选择" @change="changePage">
      <el-option
        v-for="item in options"
        :key="item.path"
        :label="item.label"
        :value="item.path">
      </el-option>
    </el-select>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  data() {
    return {
      options: [{
        path: '/baseuse',
        label: '基本用法'
      }],
      curPage: ''
    }
  },
  methods: {
    // 切换页面
    changePage() {
      this.$router.push(this.curPage)
    }
  }
}
</script>
