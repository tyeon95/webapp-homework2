<template>
  <div class="new-post">
    <label>Name</label>
    <el-input placeholder="Please input post name" v-model="post.name"></el-input>
    <br><br>
    <label>Content</label>
    <el-input type="textarea" :rows="4" placeholder="Please input" v-model="post.content"></el-input>
    <br><br>
    <el-button type="primary" @click.native="createPost">Save<i class="el-icon-upload2"</i></el-button>
  </div>
</template>

<script>
import PostsApi from '../../api/posts.js'
import router from '../../router'

export default {
  name: 'new-post',
  data () {
    return {
      post: {
        name: '',
        content: ''
      }
    }
  },
  methods: {
    createPost () {
      PostsApi.createPost(this.post,
        function (_post) {
          router.push({ name: 'Posts.index' })
        }
      )
    }
  }
}
</script>

<style scoped>

</style>
