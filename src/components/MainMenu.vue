<template>
  <el-menu
    default-active="1"
    class="girls-frontline-menu"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b"
    :collapse="isCollapse"
    @select="handleSelect"
    router
  >
    <el-menu-item index="1" route="/">
      <i class="el-icon-date"></i>
      <span slot="title">导航一</span>
    </el-menu-item>
    <el-menu-item index="2" route="/about">
      <i class="el-icon-menu"></i>
      <span slot="title">导航二</span>
    </el-menu-item>
  </el-menu>
</template>

<script>
  export default {
    name: "main-menu",
    props: {
      isCollapse: {
        required: true
      },
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath)
      }
    }
  }
</script>

<style scoped>
  .el-menu-item {
    text-align: left;
  }
  .el-menu {
    border-right: 0;
  }

</style>