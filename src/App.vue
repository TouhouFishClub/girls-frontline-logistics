<template>
  <div id="app">
    <el-container>
      <el-header>这是标题</el-header>
      <el-container>
        <el-aside :style="{width: isCollapse? '65px': '200px'}">
          <MainMenu :isCollapse="isCollapse"/>
        </el-aside>
        <el-main>
          <router-view />
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
import MainMenu from '@/components/MainMenu.vue'

export default {
  name: 'app',
  data() {
    return {
      isCollapse: true
    }
  },
  components: {
    HelloWorld,
    MainMenu
  },
  mounted() {
    this.resize()
    window.onresize = () => {
      this.resize()
    }
  },
  methods: {
    resize() {
      this.isCollapse = document.body.clientWidth < 768
    }

  }
}
</script>

<style lang="less">
* {
  margin: 0;
  padding: 0;
  border: 0;
  box-sizing: border-box;
}
html, body, #app{
  height: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.el-header{
  background-color: #000;
  color: #fff;
  line-height: 60px;
  font-size: 24px;
  font-weight: bold;
  text-align: left;
}

.el-aside {
  background-color: #545c64;
  color: #333;
  line-height: 200px;
}

.el-main {
  background-color: #E9EEF3;
  color: #333;
  text-align: center;
  line-height: 160px;
}
  .el-container.is-vertical {
    display: flex;
    height: 100%;
  }
  .el-container.is-vertical .el-container{
    flex-grow: 1;
  }
</style>
