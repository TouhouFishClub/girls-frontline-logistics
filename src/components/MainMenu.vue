<template>
  <el-menu
    default-active="1"
    class="el-menu-vertical-demo"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b"
    :collapse="isCollapse"
  >
    <el-menu-item index="1">
      <i class="el-icon-date"></i>
      <span slot="title">後勤查詢</span>
    </el-menu-item>
    <el-menu-item index="2">
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