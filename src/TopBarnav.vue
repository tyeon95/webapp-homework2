<template lang="html">
  <div class="left-sidenav">
    <el-menu theme="dark" :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <el-menu-item @click.native="getAllPosts" index="1"><i class="el-icon-menu"></i>Home</el-menu-item>
      <el-menu-item @click.native="newPost" index="2"><i class="el-icon-edit"></i>New</el-menu-item>
      <el-menu-item @click.native="logout" index="3"><i class="el-icon-close"></i>Log out</el-menu-item>
    </el-menu>
    <br>
  </div>
</template>

<script>
import UsersApi from './api/users.js'
import router from './router'

export default {
  methods: {
    toggleLeftSidenav () {
      this.$refs.leftSidenav.toggle()
    },
    logout () {
      console.log('methods.logout')
      UsersApi.logout(function (_response) {
      })
    },
    getAllPosts () {
      router.push({ name: 'Posts.index' })
    },
    newPost () {
      console.log('methods.newPost')
      router.push({ name: 'Posts.new' })
    }
  }
}
</script>

<style lang="css">
</style>
