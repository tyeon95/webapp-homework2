<template>
  <div class="sign-in">
    <el-input size="large" placeholder="Please input your email" v-model="email"></el-input>
    <br><br>
    <el-input size="large" placeholder="Please input your password" v-model="password" type="password"></el-input>
    <br><br>
    <el-button type="primary" @click.native="login">Sign in</el-button>
  </div>
</template>

<script>
import UsersApi from '../api/users.js'
import router from '../router'

export default {
  name: 'sign-in',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login () {
      console.log('methods.login')
      UsersApi.login(this.email, this.password, function (_response) {
        // NOTE: Posts.index is not yet implemented
        router.push({ name: 'Posts.index' })
      })
    }
  }
}
</script>

<style scoped>
</style>
