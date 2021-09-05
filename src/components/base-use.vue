<template>
  <div class="base-use">
    <h2>基础用法</h2>
    <div class="container">
      <canvas id="canvas" width="500" height="500" class="canvas">
        您的浏览器暂不支持canvas
        <pre>
          1. 当没有设置width和heigh时，canvas会初始化宽度为300像素和高度为300像素。
          2. 如果绘制出来的图像是扭曲的，可以尝试用width和height属性为canvas明确规定宽高，而不是使用CSS。
        </pre>
      </canvas>
    </div>
  </div>
</template>

<script>
export default {
  name: 'base-use',
  data() {
    return{
      ctx: null, // canvas渲染上下文
    }
  },
  mounted() {
    // 页面加载完成，初始化canvas
    this.initCanvas();
  },
  methods: {
    // canvas初始化，获取canvas
    initCanvas() {
      let canvas = document.getElementById('canvas');
      if(canvas.getContext) {
        this.ctx = canvas.getContext('2d');
      }else {
        alert('您的浏览器暂不支持canvas')
      }
    },
  }
}
</script>

<style scoped lang="scss">
h2{
  padding: 20px 0;
}
.canvas{
  background: #eee;
}
</style>
